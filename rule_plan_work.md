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

목표: please-work-harness 리네임 마무리 및 다음 개선 방향 결정

- [x] Harnessing_Agent → please-work-harness 디렉토리·참조 리네임
- [x] agents_chat.md gitignore 추가
- [ ] 제미나이 제안 3대 과제 검토 (Loop Metrics / Policy Gate / Context 압축) — 사용자 승인 대기
- [ ] antithesis 로그(260616_1637) 채택 5건 반영 여부 결정

---

## Work

Harnessing_Agent를 please-work-harness로 리네임 완료 (로컬 디렉토리 + 내부 참조). GitHub 원격 저장소명은 아직 Harnessing_Agent. 제미나이(안티그래비티)와 교차 협업 중 — agents_chat.md로 소통. 제미나이의 3대 개선 과제 중 일부(컨텍스트 압축)는 RPW 스냅샷화로 이미 부분 해결됨.
