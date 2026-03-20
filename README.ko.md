# AI Utilization System

개인 AI 활용 시스템을 위한 레퍼런스 레포지토리입니다.

이 문서는 블로그 글을 이미 읽고 온 사람을 기준으로 작성했습니다. 즉, 여기서는 개념 설명을 반복하기보다 이 레포가 무엇을 제공하는지, 어디부터 보면 되는지, 어떻게 가져다 쓰면 되는지에 집중합니다.

## 이 레포에 들어 있는 것

- 시스템 구조를 설명하는 아키텍처 문서
- 최소 환경 구성을 위한 세팅 가이드
- 실제 운영 흐름을 잡기 위한 워크플로우 문서
- Drive에 바로 옮겨 쓸 수 있는 `AI_OS` 폴더 템플릿
- `librarian_memory` 예시 파일
- CLI 기반 환경을 재현하기 위한 최소 Docker 구성

이 레포는 앱이 아닙니다.

완성된 자동화 프레임워크도 아닙니다.

이 레포의 목적은 개인 AI 작업 시스템을 만들기 위한 기준 구조를 제공하는 것입니다.

## 이 README의 전제

이 문서는 이미 다음 내용을 이해하고 있다는 전제로 작성되어 있습니다.

- 공유 메모리는 특정 AI 도구 안이 아니라 바깥에 있어야 한다
- 각 도구는 역할이 분리되어야 한다
- 컨텍스트는 세션이 끝나도 유지되어야 한다

개념과 동기부터 다시 보고 싶다면 블로그 글을 먼저 읽고, 그다음 이 레포로 돌아오면 됩니다.

## 어디부터 보면 되나

1. [`docs/architecture.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/architecture.md)에서 전체 구조를 먼저 봅니다.
2. [`docs/setup.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/setup.md)에서 최소 세팅 순서를 확인합니다.
3. [`template/AI_OS`](/C:/Users/smkge/Develop/ai-utilization-system/template/AI_OS)를 자신의 Drive 작업 공간으로 복사합니다.
4. [`examples/`](/C:/Users/smkge/Develop/ai-utilization-system/examples)를 참고해 첫 `librarian_memory` 파일을 만듭니다.
5. 재현 가능한 환경이 필요하면 [`docker/README.md`](/C:/Users/smkge/Develop/ai-utilization-system/docker/README.md)부터 시작합니다.

## 레포 구성

### [`docs/`](/C:/Users/smkge/Develop/ai-utilization-system/docs)

이 시스템의 핵심 설명 문서들입니다.

- [`docs/architecture.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/architecture.md): 시스템 구조, 메모리 모델, 제어 원칙
- [`docs/setup.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/setup.md): 기본 환경과 권장 세팅 순서
- [`docs/workflows.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/workflows.md): 학습, 연구, 문서 작성, 개발에 대한 예시 워크플로우
- [`docs/philosophy.md`](/C:/Users/smkge/Develop/ai-utilization-system/docs/philosophy.md): 설계 철학과 운영 원칙

### [`template/AI_OS/`](/C:/Users/smkge/Develop/ai-utilization-system/template/AI_OS)

공유 메모리 레이어를 시작하기 위한 기본 폴더 구조입니다.

포함 내용:

- `University/`
- `Projects/`
- `Librarian/`
- 과목/프로젝트용 `librarian_memory/` 예시 파일

이 구조는 그대로 고정해서 쓰는 스키마가 아니라, 시작점을 제공하는 템플릿으로 보면 됩니다.

### [`examples/`](/C:/Users/smkge/Develop/ai-utilization-system/examples)

다음 파일들의 간단한 예시가 들어 있습니다.

- `current_task.md`
- `brief.md`
- `handoff.md`

즉, 로컬 작업 컨텍스트를 어떤 식으로 유지할지 감 잡기 위한 샘플입니다.

### [`docker/`](/C:/Users/smkge/Develop/ai-utilization-system/docker)

다음 도구들을 기준으로 한 최소 재현 환경입니다.

- `gcloud`
- `gws`
- Gemini CLI
- Node.js
- Python

호스트 환경에 바로 깔기보다, 먼저 깔끔한 기준 환경에서 시작하고 싶을 때 쓰면 됩니다.

## 추천 사용 방식

이 레포는 아래 순서로 사용하는 것이 좋습니다.

1. 문서를 읽고 운영 구조를 이해합니다.
2. 템플릿을 자신의 작업 공간에 복사합니다.
3. 자신의 환경과 작업 방식에 맞게 구조를 조정합니다.

중요한 것은 이 레포 자체가 아닙니다.

이 레포를 바탕으로 만들어질 당신의 실제 작업 시스템입니다.

## 가장 작게 시작하는 방법

가능한 한 작게 시작하려면 이 정도면 충분합니다.

1. `AI_OS/`를 만든다
2. `University/`, `Projects/`, `Librarian/`를 만든다
3. 실제 작업용 `librarian_memory/` 하나를 만든다
4. Gemini CLI와 `gws`를 설치한다
5. 실제 파일 하나를 시스템에 넣어본다

이 정도면 아키텍처가 실제로 작동하는지 검증할 수 있습니다.

## 운영 원칙

다음 위치는 기본적으로 AI가 관리하는 메모리라고 보는 편이 맞습니다.

- `Librarian/`
- `*/librarian_memory/`

사용자는 의도를 표현하고,

메모리 관리자는 그 의도를 반영해 파일을 유지하는 방식이 권장됩니다.

## 이 레포의 범위

이 레포는 일부러 다음 것들을 제공하지 않습니다.

- 모든 사람에게 맞는 단일 표준
- 완성형 제품 UI
- 전체 워크플로우 자동화
- 모두에게 동일한 고정 도구 조합

대신, 각자 자신의 환경에 맞게 가져가서 바꿀 수 있는 명확한 출발 구조를 제공합니다.

## 관련 링크

- Repository: [smkgenesis/ai-utilization-system](https://github.com/smkgenesis/ai-utilization-system)
