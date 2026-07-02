# Please-Work Gemini

Gemini(Gemini CLI·Antigravity 등 AGENTS.md 표준을 읽는 에이전트)를 위한 하네스. 규칙·스킬·MCP 명세를 주입해 사고·검증·보고 절차를 일관되게 만든다. please-work 가족에서 **Cohort(손) 규율**을 담당한다.

> 가족: [claude](https://github.com/Whe-Yo/please-work-claude)(Claude 하네스) · **gemini**(Gemini/Cohort 하네스) · [clemini](https://github.com/Whe-Yo/please-work-clemini)(Claude×Gemini 오케스트레이션 — Magos가 Cohort에 하달)

> [!CAUTION]
> **이 저장소는 도구함이다. 도구함 안에서 작업하지 않는다.**
> 에이전트는 여기서 재료를 읽고 복사해 자기 환경에 주입한다. 프로젝트 작업의 일환으로 이 저장소를 수정·기록·설정하지 않는다.
> 예외는 [`log_for_test/`](log_for_test/) 하나 — `feedback` 절차로만 md를 추가한다. 나머지 경로는 성역이다.

## [ 핵심 세 축 ]

- **적응형 하네싱** — 고정 묶음이 아니라 프로젝트에 맞는 스킬만 골라 장착한다. `setup`이 [`SKILL_INDEX.md`](skills/SKILL_INDEX.md)를 읽고 선택 장착하고, `manage`가 갱신한다.
- **RPW (Rule · Plan · Work)** — 세션이 바뀌어도 끊기지 않는 현재 상태 스냅샷. 덮어쓰는 문서이고 히스토리는 git이 담당한다. 템플릿: [`rules/rule_plan_work_template.md`](rules/rule_plan_work_template.md). 에피그래프: *"Knowledge is power, guard it well."*
- **N회 안티테제** — 이전 대화를 모르는 독립 인스턴스가 RPW + 검토 대상만 받아 반론 검토한다. 최소 1회.

## [ 두 층 — 효력의 경계 ]

| 층 | 구성 | 효력 |
|---|---|---|
| **지시 층** | AGENTS.md · 스킬 · RPW | 소프트 — 대체로 따름 |
| **강제 층** | 런타임의 권한·정책 설정 (예: Antigravity permissions) | 하드 — 단 **사용자가 런타임에서 설정해야 유효** |

- 지시 층이 가치의 대부분을 짊어진다. 에이전트가 규칙을 읽고 대체로 따르되, 가끔 미끄러진다.
- Gemini 계열 런타임은 Claude Code Hooks 같은 훅 층을 이 저장소가 동봉하지 못한다. 치명 항목(.env 보안·파괴적 git)은 지시 층에 명시하고, 하드 강제는 런타임 권한 설정으로 사용자가 건다(미설정 시 소프트만 유효).
- clemini와 함께 쓰면 격리(Forge)·검토 게이트(Sanction)가 구조적 안전층을 추가한다.

## [ 구성 요소 ]

- [`rules/AGENTS.md`](rules/AGENTS.md) — 행동 원칙. 에이전트 룰 파일에 주입.
- [`skills/`](skills/) — 스킬 12종. 목록은 [`SKILL_INDEX.md`](skills/SKILL_INDEX.md).
- [`mcp/mcp_template.json`](mcp/mcp_template.json) — MCP 서버 명세(context7, sequential-thinking, exa, memory).

## [ 적용 ]

1. [`rules/AGENTS.md`](rules/AGENTS.md)를 에이전트가 **자동 로드하는** 룰 파일에 건다. 파일명이 틀리면 조용히 미적용된다 — 기본은 `AGENTS.md` 표준, Gemini CLI는 `GEMINI.md`.
2. 에이전트에게 `setup` 스킬을 실행하도록 지시한다 — 룰 주입, 스킬 선택·장착, 상태 파일 초기화까지 처리한다.
3. RPW는 프로젝트별로 그 루트에 생성된다.

## [ 피드백 로그 ]

실사용 마찰·검토 기록은 [`log_for_test/`](log_for_test/)에 남긴다(`YYMMDD_HHMM_{에이전트}.md`). 버전 이력은 [CHANGELOG.md](CHANGELOG.md).

---

# Please-Work Gemini (English)

A harness for Gemini (Gemini CLI, Antigravity, and other agents that read the AGENTS.md standard). It injects rules, skills, and MCP specs so that reasoning, verification, and reporting stay consistent. Within the please-work family this repository carries the **Cohort (hands) discipline**.

> Family: [claude](https://github.com/Whe-Yo/please-work-claude) (Claude harness) · **gemini** (Gemini/Cohort harness) · [clemini](https://github.com/Whe-Yo/please-work-clemini) (Claude×Gemini orchestration — the Magos commands the Cohort)

> [!CAUTION]
> **This repository is a toolbox. Do not work inside the toolbox.**
> Agents read and copy materials from here into their own environment. Modifying this repository as part of project work is prohibited.
> The single exception is [`log_for_test/`](log_for_test/) — md files are added only through the `feedback` procedure. Everything else is a sanctuary.

## [ Three Pillars ]

- **Adaptive harnessing** — not a fixed bundle; `setup` reads [`SKILL_INDEX.md`](skills/SKILL_INDEX.md) and installs only what the project needs; `manage` keeps it updated.
- **RPW (Rule · Plan · Work)** — a current-state snapshot that survives session boundaries. Overwritten in place; history belongs to git. Template: [`rules/rule_plan_work_template.md`](rules/rule_plan_work_template.md). Epigraph: *"Knowledge is power, guard it well."*
- **N-times antithesis** — an independent instance with no knowledge of the prior conversation receives only the RPW and the review target, and argues against it. At least once.

## [ Two Layers of Enforcement ]

| Layer | Made of | Force |
|---|---|---|
| **Instruction** | AGENTS.md · skills · RPW | Soft — mostly followed |
| **Enforcement** | Runtime permission/policy settings (e.g. Antigravity permissions) | Hard — but **only if the user configures it in the runtime** |

- The instruction layer carries most of the value. Agents read the rules and mostly follow them — with occasional slips.
- Gemini-family runtimes have no hook layer this repository can bundle (unlike Claude Code Hooks). Critical items (.env security, destructive git) are stated in the instruction layer; hard enforcement is configured by the user in the runtime (soft-only until then).
- Used together with clemini, the Forge (isolation) and Sanction (review gate) add a structural safety layer.

## [ Components ]

- [`rules/AGENTS.md`](rules/AGENTS.md) — behavioral principles, injected into the agent's rules file.
- [`skills/`](skills/) — 12 skills; see [`SKILL_INDEX.md`](skills/SKILL_INDEX.md).
- [`mcp/mcp_template.json`](mcp/mcp_template.json) — MCP server specs (context7, sequential-thinking, exa, memory).

## [ Setup ]

1. Hook [`rules/AGENTS.md`](rules/AGENTS.md) into a rules file the agent **auto-loads**. A wrong filename fails silently — the default is the `AGENTS.md` standard; Gemini CLI reads `GEMINI.md`.
2. Tell the agent to run the `setup` skill — rule injection, skill selection and installation, and state-file initialization.
3. The RPW document is created per project, at its root.

## [ Feedback Log ]

Real-use friction and review records go to [`log_for_test/`](log_for_test/) (`YYMMDD_HHMM_{agent}.md`). Version history: [CHANGELOG.md](CHANGELOG.md).
