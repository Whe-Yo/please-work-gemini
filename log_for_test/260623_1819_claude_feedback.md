# Feedback — 260623_1819 / claude

> 환경: Claude Desktop "Cowork"에서 please-work 패밀리 점검 중. 대상: please-work-gemini (범용·런타임 비종속 지향 하네스).

---

## [FRICTION-1] "런타임 비종속" 주장 대비 — Claude Desktop(Cowork)에서 설치·피드백 플로우 붕괴

### 유형
friction

### 요약
gemini 하네스는 "어떤 에이전트·런타임에도 즉시 탑재" "설치 환경/런타임에 비종속"을 표방한다. 그러나 Claude Desktop(Cowork) 런타임에선 사용자 폴더가 **삭제제한 마운트**(create OK / unlink EPERM)로 노출돼 git 기반 setup/feedback 플로우가 깨진다(`.git/index.lock` 잔존 → 클론 wedge). README의 2층 모델은 강제층(Hooks/권한)만 런타임 종속으로 보는데, "파일시스템 제약" 차원이 빠져 있다.

### 무슨 일이
- 하려던 것: 본 클론 상태 점검 + feedback md 커밋.
- 일어난 것: 점검용 `git status`가 `.git/index.lock` 생성, unlink EPERM(삭제제한)으로 커밋 차단. (Cowork 삭제권한 승인 후 해소.)
- 기대한 것: "비종속" 약속대로 표준 git 플로우가 동작.

### 환경
- 에이전트: claude (Cowork / Claude Desktop)
- OS: macOS host / Linux 샌드박스, virtiofs류 마운트(create OK / delete EPERM)
- git 2.34.1

### 재현
1. Cowork에서 클론 연결 → `git status` → `.git/index.lock` 잔존, `rm` 불가.
2. (상세·권장 대응은 please-work-claude `260623_1819` FRICTION-1 참조.)

### 관련 스킬·규칙
- README "하네스의 두 층": 지시층(범용)/강제층(런타임 종속) 외에 **파일시스템·권한 제약 어댑터** 차원 추가 고려.
- `skills/setup`·`skills/feedback`: 삭제제한 런타임 감지·분기 부재.

### 권장 대응
- 2층 모델에 "런타임 파일시스템 제약" 각주 추가.
- setup이 클론 마운트의 쓰기/삭제 가능성을 사전 점검하고, 불가 시 feedback 6절(md 출력) 폴백으로 자동 분기.
