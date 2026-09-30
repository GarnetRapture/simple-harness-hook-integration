<div align="center">
<img src="bg.png" alt="harn" width="100%">

# harn

*모든 AI 모델을 하나의 문서 계약에 고정하는 프로젝트 하네스 — 단일 AI, 단일 IDE, WSL 없음.*

*Markdown과 MCP 설정 파일 하나: 컨벤션 코어, 강제 행동 계약, 스킬, 모델별 시스템 프롬프트.*

![status](https://img.shields.io/badge/status-template-informational?style=flat-square)
![license](https://img.shields.io/badge/license-attribution--redistribution-blue?style=flat-square)
![lang](https://img.shields.io/badge/lang-en%20%7C%20ko-lightgrey?style=flat-square)
![format](https://img.shields.io/badge/format-Markdown-black?style=flat-square&logo=markdown&logoColor=white)

![conventions](https://img.shields.io/badge/conventions-C00--C20-success?style=flat-square)
![AGENTS](https://img.shields.io/badge/AGENTS-sections_0--7-blueviolet?style=flat-square)
![skills](https://img.shields.io/badge/skills-2-9cf?style=flat-square)
![runtime](https://img.shields.io/badge/runtime-single_AI_%C2%B7_one_IDE_%C2%B7_no_WSL-orange?style=flat-square)

![Claude](https://img.shields.io/badge/Claude-6E56CF?style=flat-square)
![Copilot](https://img.shields.io/badge/Copilot-181717?style=flat-square)
![Codex](https://img.shields.io/badge/Codex-412991?style=flat-square)
![Qwen](https://img.shields.io/badge/Qwen-615CED?style=flat-square)

[English](README.md) · [한국어](README.ko.md)

[![CONVENTIONS](https://img.shields.io/badge/DOCS-conventions-6E56CF?style=flat-square)](conventions.md)
[![AGENT RULES](https://img.shields.io/badge/DOCS-agent_rules-4D4D4D?style=flat-square)](AGENTS.md)
[![WORK LOG](https://img.shields.io/badge/DOCS-work_log-2E7D32?style=flat-square)](ai-tracking.md)
[![SESSION AUDIT](https://img.shields.io/badge/DOCS-session_audit-B45309?style=flat-square)](session-audit.md)
[![SKILLS](https://img.shields.io/badge/DOCS-skills-2563EB?style=flat-square)](skills/project-conventions/SKILL.md)
[![LICENSE](https://img.shields.io/badge/DOCS-license-111827?style=flat-square)](LICENSE)

</div>

---

## 이것은 무엇인가

`harn`은 프로젝트 하네스 템플릿이다. Claude·Codex·Qwen·Copilot 등 어떤 AI 모델이든 하나의 문서 계약에 고정시켜, 모델의 행동이 모델 자신의 습관이 아니라 프로젝트 컨벤션을 따르도록 만든다.

하네스는 문서와 설정뿐이다. Markdown과 MCP 설정 파일 하나로 이루어지며, 빌드도 런타임도 의존성도 없다. 모든 규칙은 소유 문서 하나에 있고, 나머지 파일은 그 문서를 가리킨다.

`harn`은 프로젝트가 아니라 템플릿이다. 프로젝트 사실(이름·경로·명령·구조·자산·도구)은 `{{...}}` 자리표시자로 비워 두었다. 규범 문장과 조항 구조는 그대로 보존한다. 그것이 이 하네스의 정체성이다.

## 아키텍처

단일 AI, 단일 IDE, WSL 없음.

이 하네스는 네이티브 호스트의 하나의 IDE(VS Code 또는 동급의 단일 편집기) 안에서 하나의 AI 모델이 작업하는 것을 전제한다. WSL, 컨테이너, 두 번째 셸, 분산된 에이전트 군집을 가정하지 않는다. 모델은 파일을 직접 편집하고, 호스트의 네이티브 셸에서 명령을 실행하며, 실제 도구 출력에서 증거를 얻는다.

권위는 한 방향으로만 흐른다:

```
사용자 지시 → 컨벤션 → AGENTS → 스킬 → 실행 → 증거
```

하위는 상위를 재정의·축소·유예하거나 예외를 만들지 못한다. 사용자는 최종 상급자이자 유일한 결정권자다. 모델은 실행자이며, 토큰량·비용·작업량·소요 시간·컨텍스트 길이·난이도를 이유로 지시를 거절·축소·유예할 권한이 없다.

공유 개념은 정확히 하나의 소유자를 가진다:

| 개념 | 소유자 |
| --- | --- |
| 권위·방향·정의·확정 결정 | `conventions.md` |
| 상시 행동과 절차 | `AGENTS.md` |
| 세부 절차 | `skills/` |
| 모델별 프롬프트 | `instructions/` |
| 완주한 세션 기록 | `ai-tracking.md` |
| 위반·미완료 기록 | `session-audit.md` |
| 도구 등록 | `config.toml` |

## 문서

| 파일 | 무엇인가 | 언어 | 소유 |
| --- | --- | --- | --- |
| `conventions.md` | 프로젝트의 절대 정의 문서이자 하네스의 핵심 코어. 권위·방향, 단일 기준, 확정 결정, 아키텍처와 소유자, 역할 그룹 분담, 실행·연산·플랫폼 아키텍처, 프로덕션 트러블슈팅 로그, 구조·의존 방향, 저수준 경로 계약, 명명 규칙, 실행 환경, 근거·수용 기준, FIX와 예외 정의, 작업 프로세스 유형별 정의, 추론·검증 방법, 작업 수명주기·GOAL·트래킹, 변경 금지, 도구 사용 계약, 버전·자료 보존, 강제 수단과 한계, 데이터 카탈로그·스키마를 소유한다. 조항 C00~C20. | 한국어 | C01 |
| `AGENTS.md` | `conventions.md`를 이행하는 강제 AI 행동 계약. 0절 하드 규칙, 1절 방향, 2절 운영 절차, 3절 권위와 문서 소유, 4절 행동별 증거, 5절 명시 금지와 경계, 6절 검증된 실패 금지(S01~S20), 7절 실패·교정·완주 불변식. | 영어 | C01, AGENTS §3 |
| `skills/project-conventions/SKILL.md` | AGENTS 2절을 세부화하는 공통 워크플로. 권위 게이트, 공유 결정 철학, 순서 작업 주기(G1~G10), 육하 명제, 변경 판단 절차(D1~D7), FIX와 도구 복구, 유형별 적용, 상태·이력·전달. 새 권위·예외·중단 조건을 만들지 않는다. | 영어 | C01 |
| `skills/external-record-cli/SKILL.md` | 선택 사항. 외부 기록 시스템(위키·이슈 트래커·호스팅 데이터베이스)을 하네스에 묶는다. C12 외부 기록 행의 명령 표면과 읽기/쓰기 경계, 하네스별 MCP 등록을 소유한다. 외부 기록 시스템이 없는 프로젝트는 이 파일을 삭제한다. | 영어 | C01, C12 |
| `instructions/model-system-prompt.md` | 모델별 시스템 프롬프트. 모든 문장이 `conventions.md` 또는 `AGENTS.md` 조항을 대괄호 참조와 함께 옮긴 문장이며, 모델마다 한 파일씩 복제한다. 독립 규칙을 두지 않는다. | 영어 | C01 |
| `ai-tracking.md` | 완주한 세션 GOAL 요약. 요구마다 대상·방법·결과·검증·미검증 경계를 한 줄로 적고, 조항별 대조 결과와 저장소 커밋 흐름을 담는다. GOAL 완주 후에만 쓴다. | 한국어 | C14, C15 |
| `session-audit.md` | 문서로만 존재하는 규칙의 위반 증거, 반복 금지 행동 행 M01~M27, 세션을 넘기는 미완료 지시 TODO 행. | 한국어 | C15, C16 |
| `config.toml` | Codex용 MCP 서버 등록(`.codex/config.toml`). 도구별 승인 모드를 가진 런타임 관찰 서버와 선택적 외부 기록 서버. 등록은 권한이 아니며 C12 도구 계약이 우선한다. | 설정 | C12 |
| `LICENSE` | 라이선스 조항. 자유로운 사용·수정·재배포를 허용하되, 저작권 고지·저작권자·라이선스 전문을 유지한다는 단일 조건을 둔다. 이를 제거한 재배포는 무단이며 금지된다. | 영어 | C11 |
| `README.md` · `README.ko.md` | 소개·아키텍처·소유 문서 안내. 같은 내용의 두 언어 판. | 영어 / 한국어 | C01 |
| `bg.png` | 두 README 판이 쓰는 배너 이미지. | 이미지 | — |

## 하네스가 보존하는 것

자리표시자를 채워도 아래는 바꾸지 않는다. 이것이 이 하네스의 정체성이다.

| 원리 | 소유 조항 |
| --- | --- |
| 권위는 한 방향이다: 사용자 지시 → 컨벤션 → AGENTS → 스킬 → 실행 → 증거 | C00 |
| 사용자는 최종 상급자이자 유일한 결정권자, AI는 실행자다. 토큰·비용·시간·난이도를 이유로 지시를 거절·축소·유예할 권한이 없다 | C00 |
| 세션에 입력한 지시 전체가 그 세션의 GOAL이며 반드시 이행하는 계약이다 | C00, C15 |
| 근거가 확정된 추론만 행동의 근거로 쓴다. 빠진 연결은 추측으로 메우지 않고 그 사실을 얻는 행동을 먼저 한다 | C00, C09 |
| 값은 패턴·매핑·매칭 규칙으로 도출하지 않는다. 항목마다 명시적으로 정의한다 | C00 |
| 모든 수정은 변경 판단 절차 7단계(①~⑦)를 모두 채운 뒤에만 이행한다 | C14 |
| 검증은 양방향이다. 정방향은 누락 0, 역방향은 창작 0을 증명한다 | C14 |
| 모든 행동에는 누가·무엇을·언제·어디서·왜·어떻게가 식별되는 1:1 직접 명제가 필요하다 | C09 |
| 실패는 원인 소유자를 고치는 FIX로 처리한다. 실패를 숨기는 가드·기본값·폴백·재시도를 금지한다 | C06 |
| 모든 경고와 오류는 크리티컬이다. 미사용·미정의·단절은 삭제가 아니라 연결 누락으로 추적한다 | C06, C13 |
| 문서는 행동을 보장하지 않는다. 보장에 가까운 수단은 기계적 강제뿐이다 | C16 |
| 완주 전에는 트래킹·워크로그·핸드오프를 쓰지 않는다. 완주 후 요약을 쓰고 즉시 조항별로 대조한다 | C15 |
| 사용자에게 보이는 모든 문장은 {{USER_LANGUAGE}}이며 어투는 {{RESPONSE_TONE}}로 고정한다 | C15 |
| 실제로 발생한 실패 모드를 S행으로 닫고, 그 증거를 세션 감사가 소유한다 | AGENTS 6절 |

## 자리표시자

`{{...}}`는 프로젝트 값으로 바꾼다. 아래 표는 그룹별 목록이다. 표에 없는 자리표시자도 이름이 곧 의미이므로 같은 방식으로 채운다.

### 3.1 프로젝트 정체성

| 자리표시자 | 의미 | 예시 |
| --- | --- | --- |
| `{{PROJECT_NAME}}` | 프로젝트 식별자(짧은 이름) | `evt` |
| `{{PROJECT_PURPOSE}}` | 한 줄 목적 | 게임 엔진·네이티브 클라이언트 |
| `{{PROJECT_STACK}}` | 스택 요약 | C++26·xmake·TypeScript·SolidJS |
| `{{PROJECT_ROOT}}` | 저장소 루트 절대 경로 | `D:\26_project\ev_three` |
| `{{MODEL_NAME}}` | 모델 지침 대상 모델 | `GPT-6 Astra` |
| `{{DECISION_DATE}}` | 확정 결정 근거 날짜 | `2026-09-24 지시` |

### 3.2 문서 경로

| 자리표시자 | 의미 | 예시 |
| --- | --- | --- |
| `{{CONVENTIONS_PATH}}` | 컨벤션 문서 경로 | `docs/conventions.md` |
| `{{AGENTS_PATH}}` | AGENTS 경로 | `AGENTS.md` |
| `{{TRACKING_PATH}}` | 트래킹 경로 | `docs/ai-tracking.md` |
| `{{AUDIT_PATH}}` | 세션 감사 경로 | `docs/claude-session-audit.md` |
| `{{README_PATH}}` | README 경로 | `README.md` |
| `{{SKILL_ROOT}}` | 스킬 루트 | `.codex/skills` |
| `{{SKILL_TO_ROOT}}` | 스킬 디렉터리에서 프로젝트 루트까지의 상대 경로 | `../../../` |
| `{{INSTRUCTION_ROOT}}` | 모델 지침 루트 | `.codex/instructions` |
| `{{INSTRUCTION_TO_ROOT}}` | 지침 디렉터리에서 프로젝트 루트까지의 상대 경로 | `../../` |
| `{{HOOK_PATH}}` | 프로젝트 훅 경로 | `.claude/hooks` |
| `{{MEMORY_PATH}}` | 모델 프로젝트 메모리 경로 | 모델 전용 메모리 폴더 |

### 3.3 언어·어투

| 자리표시자 | 의미 | 예시 |
| --- | --- | --- |
| `{{CONVENTIONS_LANGUAGE}}` | 컨벤션 언어 | `한국어` |
| `{{AGENTS_LANGUAGE}}` | AGENTS 언어 | `영어` |
| `{{SKILL_LANGUAGE}}` | 스킬·지침 언어 | `영어` |
| `{{README_LANGUAGE}}` | README 언어 | `영어·한국어` |
| `{{USER_LANGUAGE}}` | 사용자에게 보이는 문장 언어 | `한국어` |
| `{{RESPONSE_TONE}}` | 응답 어투 | `정중한 존댓말` |
| `{{JOURNAL_TIMEZONE}}` | 일지 시각 기준 | `KST` |

### 3.4 구조·경로

| 자리표시자 | 의미 | 예시 |
| --- | --- | --- |
| `{{SOURCE_ROOT}}` | 자체 소스 루트 | `src` |
| `{{LOWLEVEL_ROOT}}` | 저수준 소스 루트 | `native/src` |
| `{{PRODUCER_ROOT}}` | 생산 도구 루트 | `tools` |
| `{{CONSUMER_ROOT}}` | 소비 코드 루트 | `src`·`native` |
| `{{MANAGED_ASSET_ROOT}}` | 관리 자산 루트 | `data` |
| `{{SOURCE_OF_TRUTH}}` | 원천 | `research/unity-bundles` |
| `{{GENERATED_ROOT}}` | 생성물 루트 | `dist`·`Release` |
| `{{TEMP_ROOT}}` | 임시 산출물 루트 | `tmp-codex` |
| `{{MANIFEST_PATH}}` | 버전 원천 | `package.json` |
| `{{CATALOG_PATH}}` | 카탈로그 | `data/catalog.tsv` |
| `{{SCHEMA_PATH}}` | 스키마 | `data/schema.json` |
| `{{DOMAIN_LIST}}` | 도메인 목록 | `type, constant, logic, …` |
| `{{DOMAIN_1}}`·`{{DOMAIN_2}}` | 도메인 이름 | `logic` |
| `{{DOMAIN_1_CLASSES}}`·`{{DOMAIN_2_CLASSES}}` | 도메인별 class 폴더 | `catalog, combat, engine` |
| `{{DOMAIN_1_ALLOWED}}`·`{{DOMAIN_2_ALLOWED}}` | 허용 의존 도메인 | `type, constant, logic` |
| `{{DOMAIN_RULE_OWNER}}` | 형식 검사 소유자 | 검사기 파일 경로 |
| `{{LOWLEVEL_LANGUAGE}}` | 저수준 언어 | `C++26` |
| `{{LOWLEVEL_FILE_CONVENTION}}` | 저수준 파일 규칙 | 타입마다 `.hpp`·`.cpp` 쌍 |
| `{{AREA_1}}`·`{{AREA_2}}` | 저수준 영역 | `gpu` |
| `{{AREA_1_FEATURES}}`·`{{AREA_2_FEATURES}}` | 하위 기능 폴더 | `d3d12, vulkan` |
| `{{AREA_1_RESPONSIBILITY}}`·`{{AREA_2_RESPONSIBILITY}}` | 책임 | 장치·자원·스왑체인 |
| `{{BUILD_TARGETS}}` | 빌드 대상 | 실행 파일·라이브러리 목록 |
| `{{MAPPING_TARGET_KINDS}}` | 수동 지정 대상 종류 | 정령·스킨·몬스터·보스 |
| `{{TARGET_KIND_LIST}}` | 전수 대상 종류 목록 | 위와 같은 종류 목록 |
| `{{ROLE_GROUP_LIST}}` | 역할 그룹 목록 | 캐릭터·이펙트·맵·공용 |
| `{{ROLE_GROUP_1}}`~`{{ROLE_GROUP_3}}` | 역할 그룹 이름 | 캐릭터 렌더 |
| `{{ROLE_GROUP_1_PATHS}}`~`{{ROLE_GROUP_3_PATHS}}` | 그룹 소유 경로 | 경로 목록 |
| `{{ROLE_GROUP_1_RULE}}`~`{{ROLE_GROUP_3_RULE}}` | 그룹 변경 규칙 | 지목 지시로만 변경 |
| `{{ROLE_GROUP_COMMON_PATHS}}` | 공용 그룹 경로 | 공용 경로 목록 |
| `{{CROSS_1}}`·`{{CROSS_1_CALLER}}`·`{{CROSS_1_OWNER}}`·`{{CROSS_1_CONTRACT}}` | 교차 소비 | 그룹 간 호출 계약 |
| `{{BOUNDARY_1_NAME}}`~`{{BOUNDARY_3_NAME}}` | 아키텍처 경계 이름 | 게임·씬 의미 |
| `{{BOUNDARY_1_OWNER}}`~`{{BOUNDARY_3_OWNER}}` | 경계 소유자·계약 | 소유 경로 |
| `{{SERVING_OWNER}}` | 데이터 서빙 소유자 | 서빙 모듈 |
| `{{SHARED_DATA_1}}`·`{{SHARED_DATA_2}}` | 공유 데이터 | 드로우 목록 |
| `{{SHARED_DATA_1_OWNER}}`·`{{SHARED_DATA_2_OWNER}}` | 계약 소유자 | 소유 파일 |
| `{{SHARED_DATA_1_BOUNDARY}}`·`{{SHARED_DATA_2_BOUNDARY}}` | 일치해야 하는 경계 | 헤더·항목·수명 |
| `{{ASSET_DOMAIN_LIST}}` | 자산 도메인 목록 | `models, effect, scene, …` |
| `{{ASSET_DOMAIN_1}}`·`{{ASSET_DOMAIN_2}}` | 자산 도메인 | `models` |
| `{{ASSET_DOMAIN_1_CATALOG}}`·`{{ASSET_DOMAIN_2_CATALOG}}` | 도메인 카탈로그 파일 | `characterCatalog.json` |
| `{{ASSET_DOMAIN_1_UNIT}}`·`{{ASSET_DOMAIN_2_UNIT}}` | 항목 단위 | 정령 |
| `{{ASSET_DOMAIN_1_FIELDS}}`·`{{ASSET_DOMAIN_2_FIELDS}}` | 명시할 스키마·필드 | 필드 목록 |
| `{{PATTERN_1}}`·`{{PATTERN_1_SHAPE}}`·`{{PATTERN_1_COUNT}}`·`{{PATTERN_1_PRODUCER}}`·`{{PATTERN_1_CONSUMER}}`·`{{PATTERN_1_FIELDS}}` | 자산 패턴 행 | 패턴·모양·수·생산·소비·필드 |
| `{{SCHEMA_RECORD_OWNER}}` | 스키마 선언 소유자 | 선언 스크립트 |

### 3.5 명령·도구

| 자리표시자 | 의미 | 예시 |
| --- | --- | --- |
| `{{SHELL}}` | 셸 | `Windows PowerShell` |
| `{{CHECK_COMMAND}}` | 정적 검사 | `npm run c` |
| `{{BUILD_COMMAND}}` | 빌드 | `npm run build:native` |
| `{{RELEASE_BUILD_COMMAND}}` | 배포 빌드 | `npm run build:release` |
| `{{CATALOG_COMMAND}}` | 카탈로그 게이트 | `npm run data:catalog` |
| `{{VERIFY_COMMAND}}` | 자산 검증 | `npm run data:verify` |
| `{{VERSION_COMMAND}}` | 버전 변경 | `npm run version:set` |
| `{{DEV_COMMAND}}` | 개발 실행 | `npm run dev` |
| `{{PROD_COMMAND}}` | 프로덕션 실행 | `npm run prod` |
| `{{TIME_TOOL}}` | 시각 도구 | 시각 확인 스크립트 |
| `{{SCRIPT_RUNTIME}}` | 스크립트 런타임 | Python 실행 파일 경로 |
| `{{RUNTIME_TOOL}}` | 런타임 관찰 도구 | Runtime Lab |
| `{{RUNTIME_STATUS_TOOL}}`·`{{RUNTIME_START_TOOL}}`·`{{RUNTIME_STOP_TOOL}}`·`{{RUNTIME_OBSERVE_TOOL}}`·`{{RUNTIME_DEBUG_TOOL}}` | 관찰 세션 도구 | `ev_runtime_*` |
| `{{RUNTIME_SERVER_NAME}}`·`{{RUNTIME_SERVER_ENTRY}}` | 관찰 MCP 서버 | 서버 이름·진입점 |
| `{{RE_TOOL}}` | 역공학 도구 | `IDA Pro 9.4` |
| `{{INDEX_TOOL}}` | 원본 색인 도구 | 색인 스크립트 |
| `{{EXTERNAL_RECORD_TOOL}}` | 외부 기록 CLI | `ntn` |
| `{{EXTERNAL_RECORD_SERVER_NAME}}`·`{{EXTERNAL_RECORD_MCP_ENDPOINT}}`·`{{EXTERNAL_RECORD_AUTH}}`·`{{EXTERNAL_RECORD_TOOL_PREFIX}}` | 외부 기록 MCP | 서버·인증·접두 |
| `{{EXTERNAL_RECORD_RANGE_ROOT}}`·`{{EXTERNAL_RECORD_READ_TOOLS}}`·`{{EXTERNAL_RECORD_WORKER_PATH}}`·`{{EXTERNAL_RECORD_DATABASE}}` | 외부 기록 범위·워커 | 범위 루트·읽기 도구·워커·DB |
| `{{CMD_1}}`·`{{CMD_1_PURPOSE}}`·`{{CMD_1_NOTES}}`·`{{CMD_2}}`·`{{CMD_2_PURPOSE}}`·`{{CMD_2_NOTES}}` | 외부 기록 명령 | 명령·용도·비고 |

### 3.6 검사·강제

| 자리표시자 | 의미 | 예시 |
| --- | --- | --- |
| `{{CHECKED_LANGUAGE_1}}`·`{{CHECKED_LANGUAGE_2}}` | 정적 검사 대상 언어 | `TS`·`GLSL` |
| `{{BUILT_LANGUAGE_1}}`·`{{BUILT_LANGUAGE_2}}` | 빌드 검사 대상 언어 | `HLSL`·`C++` |
| `{{CHECK_SCOPE}}` | 정적 검사 범위 | 검사 항목 목록 |
| `{{CHECK_GAPS}}` | 정적 검사 공백 | 검사하지 않는 항목 |
| `{{COMMIT_HOOK_SCOPE}}` | 커밋 훅 범위 | 대용량 파일 차단 |
| `{{PERMISSION_SCOPE}}`·`{{PERMISSION_LEVEL}}` | 하네스 권한 설정 | 범위·강제 수준 |
| `{{RUNTIME_GUARD}}` | 런타임 가드 | 카탈로그 검증 |
| `{{INLINE_STYLE_SCOPE}}`·`{{INLINE_STYLE_ALLOWED}}`·`{{INLINE_STYLE_CHECKED}}` | 인라인 스타일 금지 | 범위·허용·검사 |
| `{{INLINE_TYPE_SCOPE}}`·`{{INLINE_TYPE_ALLOWED}}`·`{{INLINE_TYPE_CHECKED}}` | 인라인 타입 금지 | 범위·허용·검사 |
| `{{TYPE_ESCAPE_SCOPE}}`·`{{TYPE_ESCAPE_ALLOWED}}`·`{{TYPE_ESCAPE_CHECKED}}` | 타입 우회 금지 | 범위·허용·검사 |
| `{{COMMENT_SCOPE}}`·`{{COMMENT_CHECKED}}` | 주석 금지 | 범위·검사 |

### 3.7 제품·프로세스·명명

| 자리표시자 | 의미 | 예시 |
| --- | --- | --- |
| `{{PROCESS_1}}`·`{{PROCESS_1_ENTRY}}`·`{{PROCESS_1_BOUNDARY}}` | 제품 프로세스 | 런처·게임 |
| `{{PROCESS_2}}`·`{{PROCESS_2_ENTRY}}`·`{{PROCESS_2_BOUNDARY}}` | 제품 프로세스 | 두 번째 진입점 |
| `{{DEV_BOUNDARY}}`·`{{PROD_BOUNDARY}}`·`{{RUNTIME_BOUNDARY}}` | 실행 경계 | 경계 설명 |
| `{{DELIVERY_PIPELINE}}`·`{{DELIVERY_BOUNDARY}}` | 배포 파이프라인 | 단계·경계 |
| `{{COMMAND_SOURCE}}` | 명령 정의 원천 | `package.json` |
| `{{LOG_OWNER}}`·`{{LOG_LOCATION}}` | 트러블슈팅 로그 | 소유자·위치 |
| `{{LAYER_OWNERSHIP}}`·`{{PRODUCT_DEFINITION}}`·`{{PERFORMANCE_DEFINITION}}`·`{{DELIVERY_DEFINITION}}`·`{{RENDER_COMPUTE_PLATFORM_DEFINITION}}` | 확정 결정 | 결정 내용 |
| `{{RUNTIME_ARCHITECTURE_INTRO}}`·`{{EXECUTION_LINE_DEFINITION}}`·`{{HARDWARE_INTERFACE_DEFINITION}}`·`{{COMPUTE_LINE_DEFINITION}}`·`{{SELECTION_DEFINITION}}`·`{{PRESET_VALIDATION_DEFINITION}}`·`{{PLATFORM_LAYER_DEFINITION}}` | 실행·연산·플랫폼 | 계층 정의 |
| `{{VERSION_FORMAT}}` | 버전 형식 | `V<major>.<minor>.<patch>` |
| `{{LANG_1}}`·`{{LANG_1_FUNCTION_CASE}}`·`{{LANG_1_FILE_RULE}}`·`{{LANG_1_TYPE_CASE}}`·`{{LANG_1_TYPE_FILE_RULE}}` | 언어 1 명명 규칙 | TS |
| `{{COMPONENT_CASE}}` | 컴포넌트 명명 | `PascalCase` |
| `{{LANG_2}}`·`{{LANG_2_FUNCTION_CASE}}`·`{{LANG_2_FILE_RULE}}` | 언어 2 명명 규칙 | C++ |
| `{{SHADER_FUNCTION_CASE}}` | 셰이더 함수 명명 | `lowerCamelCase` |

### 3.8 기록

| 자리표시자 | 의미 | 예시 |
| --- | --- | --- |
| `{{AUDIT_SESSION_RANGE}}`·`{{AUDIT_METHOD}}`·`{{AUDIT_RESULT}}` | 감사 근거 | 대상·방법·결과 |
| `{{M01_BEHAVIOR}}`·`{{M01_EVIDENCE}}`·`{{M02_BEHAVIOR}}`·`{{M02_EVIDENCE}}`·`{{M03_BEHAVIOR}}`·`{{M03_EVIDENCE}}` | 반복 금지 행동 | 행동·증거 |
| `{{TODO_ID}}`·`{{TODO_SOURCE}}`·`{{TODO_STATE}}`·`{{TODO_REMAINING}}`·`{{TODO_ACCEPTANCE}}` | 미완료 TODO 행 | ID·원문·상태·남은 작업·완료 조건 |
| `{{COMMIT_HASH}}`·`{{COMMIT_TIME}}`·`{{COMMIT_MESSAGE}}`·`{{COMMIT_SUMMARY}}` | 커밋 흐름 행 | 해시·일시·메시지·요약 |

## 적용 순서

1. **파일 배치.** 이 디렉터리의 파일을 대상 프로젝트의 같은 상대 위치로 옮긴다. `conventions.md`는 `{{CONVENTIONS_PATH}}` 위치로, 스킬은 `{{SKILL_ROOT}}` 아래로, 모델 지침은 `{{INSTRUCTION_ROOT}}` 아래로 둔다.
2. **정체성·언어 채우기.** 3.1과 3.3을 먼저 채운다. 언어 계약이 정해져야 나머지 문서의 언어가 정해진다.
3. **경로·명령 채우기.** 3.2와 3.5를 채운다. 문서 간 링크가 이 값으로 연결된다.
4. **구조 채우기.** 3.4를 채운다. C02·C03·C04·C10·C17·C18·C19의 예시 표를 프로젝트 사실로 교체한다.
5. **검사·강제 채우기.** 3.6을 채운다. C16의 강제 수단 표는 실제 설정·검사기 파일 기준으로만 적는다.
6. **기록 초기화.** `ai-tracking.md`와 `session-audit.md`의 예시 행을 지우고 빈 상태로 시작한다. S행·M행은 실제 실패가 발생할 때 추가한다.
7. **하네스 진입점 연결.** 각 하네스(Claude·Qwen·Codex·Copilot)의 진입 파일이 AGENTS와 공통 스킬만 가리키게 한다. 진입 파일에 독립 규칙을 두지 않는다.
8. **대조.** 채운 뒤 `conventions.md` ↔ `AGENTS.md` ↔ 스킬 ↔ 모델 지침을 조항 번호로 대조해 충돌 0을 확인한다. 링크·앵커가 실제 파일을 가리키는지 확인한다.

## 유지 규칙

- 컨벤션 조항을 바꾸면 같은 작업에서 AGENTS·스킬·모델 지침을 대조해 충돌을 없앤다(C01).
- 같은 규칙의 독립 복사본을 만들지 않는다. AGENTS와 스킬은 조항 번호를 붙여 옮긴 문장이며 독립 규칙이 아니다.
- 문서로만 존재하는 규칙은 세션 감사의 위반 증거와 함께 관리하고, 같은 위반이 반복되면 기계적 강제 수단으로 옮긴다(C16).
- 이 템플릿 자체를 수정할 때는 자리표시자 이름을 바꾸지 않는다. 이름이 곧 계약이다.

## 라이선스

`harn`은 **harn Attribution-Redistribution License 1.0**으로 배포된다. 소스든 다른 형태든 자유롭게 사용·수정·재배포할 수 있으나, 저작권 고지·저작권자·라이선스 전문을 유지한다는 단일 조건을 따른다. 이를 제거·변경·은닉한 재배포는 무단이며 금지된다. [LICENSE](LICENSE)를 참고한다.
