# Changelog

이 프로젝트의 주요 변경을 기록한다. 형식은 [Keep a Changelog](https://keepachangelog.com/)를 따르고, 버전은 [SemVer](https://semver.org/)를 지향한다. 프로토타입 단계이므로 0.x.

업데이트 확인(`manage`의 일일 점검)은 이 파일과 git 태그를 기준점으로 삼을 수 있다.

## [Unreleased]

## [0.2.1] - 260702
### Fixed
- **AGENTS.md 정체성 정정(코호트 감사 260702)**: 헤더 "Universal Agent Global Rules"(분리 전 잔재) → "Gemini Agent Global Rules (Cohort)", 대상 서술·강제 수단(런타임 권한·정책)도 정렬. 10절 폭주 차단의 실패 횟수 기준 이중 서술을 4절 참조로 제거.

## [0.2.0] - 260702
### Added
- **능동 피드백 규칙**: `rules/AGENTS.md` 6절에 "하네스 실사용 중 버그·마찰·개선점 발견 시 사용자 지시 없이도 `feedback` 스킬로 `log_for_test/`에 즉시 기록" 능동 지침 추가. WHY: 다른 세션이 침묵하면 같은 결함이 반복 — 하네스는 실사용 마찰을 모아야 개선된다.
- **RPW 에피그래프**: "Knowledge is power, guard it well" — 템플릿에 명문화.
### Changed
- **README 전면 재작성(260702)**: 분리 전 "범용 하네스" 정체성이 그대로 남아 있던 것을 **Gemini/Cohort 하네스**로 정정(가족 3레포 참조, Cohort 규율 명시). 스타일 통일 — `[ 제목 ]` 섹션, 담백한 서술, 한국어 본문 + 영어 미러. 강제 층 서술을 "위반 불가"에서 "런타임 권한 설정으로 사용자가 걸어야 유효(미설정 시 소프트만)"로 정직하게 정정.
### Fixed
- **SKILL_INDEX feedback 설명 정정**(피드백 260623_1819 DOC-1): "GitHub 이슈로 보고" → "`log_for_test/`에 md 기록·커밋", 트리거 "피드백 남겨"로 정렬.
- **삭제제한 마운트 대응**(피드백 260623_1819): `feedback` 스킬 6절에 잔존 `.git/index.lock` 제거 후 md 출력 폴백 절차 추가.

## [0.1.0] - 260617
프로토타입 첫 버전. 핵심 3축(적응형 하네싱 / RPW / N회 안티테제) + 2층 구조 정립.

### Added
- **3축 정체성**: 적응형 하네싱, RPW(현재 상태 스냅샷), N회 안티테제 검토.
- **2층 구조 명문화**: 지시 층(범용·소프트) + 강제 층(런타임 종속·하드). README에 효력 그라데이션 문서화.
- 스킬 11종: `boost`, `worklog`, `plan`, `verify`, `review`, `antithesis`, `peer`, `paper`, `setup`, `manage`, `resource`.
- `resource` 스킬: 무거운 작업 착수 전 호스트 리소스 라이브 조회(저장 없음, 호스트별 분기).
- `setup`의 상태 파일 초기화(`~/.agents/harnessing_state.json`: repoPath·skillsDir).
- `manage`의 일일 업데이트 확인(boost에서 자동 트리거) + skillsDir 기반 경로 조회.
- AGENTS.md 9절 "절대 금지"(치명적·강제 층 대상), 강제 층 예시로 `.env` Read 차단(권한 deny).
- `ROADMAP.md`: 보류 기능(리소스 예약 원장) 설계 기록.

### Changed
- `RULES.md` → `AGENTS.md` 리네임 (2026 업계 표준 대응).
- RPW를 히스토리 로그에서 "현재 상태 스냅샷"(Rule/Plan/Work)으로 단순화. 3-tier(Always/Ask first/Never do) + WHY 병기.
- AGENTS.md signal density 패스: generic 규칙 압축, 각 규칙에 WHY.
- antithesis 적용 범위 확장(코드·문서·조사·설계), 최소 1회 하한.
- 날짜 형식 `YYMMDD_HHMM`로 통일.

### Removed
- 에이전트 종속 설치 스크립트·전용 설정, 에이전트별 적용 가이드(→ `setup` 위임).
- RPW의 Decision Log·Work Log·AntiPatterns 누적 구조(→ git 히스토리/커밋 메시지).
