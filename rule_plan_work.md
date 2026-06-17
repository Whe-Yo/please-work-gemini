# RPW — please-work-harness

## Rule

### Always do
- 작업 유형에 맞게 페르소나를 조정한다 (코드·구현 → 아키텍트, 조사·분석 → 분석가, 논문·편집 → 학술 편집자)
- 이해 > 계획 > 실행 > 검증 > 보고 순서로 작업한다
- 단순 답변이 아닌 주요 작업 완료 후 antithesis를 실행한다
- 모든 소통은 한국어로, 첫 문장은 결과로 시작한다
- 날짜는 YYMMDD_HHMM 형식으로 표기한다

### Ask first
- 스킬 파일 삭제·전면 교체 전
- 아키텍처 범위 밖 변경 시
- 파괴적 git 명령 실행 전 (force push, reset --hard 등)

### Never do
- 검증 안 된 결과를 완료로 보고
- antithesis 검토 프롬프트에 이전 대화 컨텍스트 포함
- 채팅창에 YAML·JSON 등 구조화 데이터 출력

---

## Plan

목표: 2층 구조 명문화 + signal density + antithesis 로그 버그 반영

- [x] Harnessing_Agent → please-work-harness 디렉토리·참조·GitHub 원격명 리네임
- [x] agents_chat.md 프로젝트 내 이동 + gitignore
- [x] README 2층 모델(지시 층/강제 층) 명문화, 낡은 RPW·n회 서술 교정
- [x] AGENTS.md signal density 패스 + WHY 병기 + 9절 치명적 금지 신설
- [x] RPW 템플릿 WHY·Never do 구체화
- [x] antithesis 로그 채택 4건 반영(#2·#4·#5·#6), #3은 스냅샷화로 무효 명시
- [ ] Claude 어댑터 동기화(~/.claude) + 신규 인스턴스 실행 검증 → 커밋/푸시
- 제미나이 3대 과제 판정: ① Metrics 블록·③ archive 압축 = 기각(스냅샷 충돌). ② Policy Gate = 범용 스킬 신설 대신 강제 층 어댑터로 흡수.

---

## Work

GitHub 원격 저장소명까지 please-work-harness로 리네임 완료, 로컬 remote URL 동기화됨. 2층 구조 명문화 + signal density 패스 + antithesis 버그 4건 반영 완료. 남은 것: Claude 어댑터 동기화와 신규 인스턴스 실행 검증 후 커밋/푸시. 제미나이(안티그래비티)와 agents_chat.md로 교차 협업 중.
