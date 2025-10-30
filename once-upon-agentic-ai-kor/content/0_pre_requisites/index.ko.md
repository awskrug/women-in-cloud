---
title: "🐉 챕터 0: 예상치 못한 모험"
weight: 1
---

![Header Image](/static/images/header_0.jpeg)

## Strands란 무엇인가요?

[Strands](https://strandsagents.com/latest/)는 AI 에이전트와 멀티 에이전트 시스템의 생성을 단순화하도록 설계된 오픈 소스 Python SDK입니다. 개발자 경험을 염두에 두고 구축된 Strands는 다양한 도구, API, 서비스와 상호작용할 수 있는 정교한 AI 애플리케이션을 구축하기 위한 직관적인 프레임워크를 제공합니다.

### Strands의 특별한 점은 무엇인가요?

- **에이전트 우선 설계**: 추론하고, 계획하고, 복잡한 작업을 실행할 수 있는 지능형 에이전트 생성
- **도구 통합**: 에이전트를 외부 API, 데이터베이스, 서비스에 원활하게 연결
- **멀티 에이전트 오케스트레이션**: 여러 에이전트가 협력하여 복잡한 문제를 해결하는 시스템 구축
- **모델 유연성**: Amazon Bedrock, OpenAI 등을 포함한 다양한 LLM 제공업체 지원
- **프로덕션 준비**: 내장된 오류 처리, 로깅, 모니터링 기능

### 학습할 내용

이 워크숍에서는 간단한 챗봇부터 복잡한 멀티 에이전트 시스템까지 모든 것을 구축하기 위해 Strands의 힘을 활용하는 방법을 발견하게 됩니다. 기초부터 시작하여 점진적으로 고급 패턴과 통합으로 나아갈 것입니다.

여정을 시작할 준비가 되셨나요? 개발 환경을 설정해보겠습니다!

## 성역 설정 (설치)

**1단계: 마법적 환경 생성**

```bash
# 워크숍 저장소 클론
git clone https://github.com/aws-samples/sample-once-upon-agentic-ai.git
cd sample-once-upon-agentic-ai
```

**2단계: 필요한 마법 설치**

[uv를 가지고 있지 않다면 설치하세요](https://docs.astral.sh/uv/getting-started/installation/#standalone-installer)

```bash
# 모든 워크숍 종속성을 설치하고 환경 동기화
uv sync
```

venv는 자동으로 활성화되어야 하지만 그렇지 않은 경우 다음 명령을 실행하세요:

```bash
source .venv/bin/activate  # macOS/Linux에서
# 또는
.venv\Scripts\activate     # Windows에서
```

**3단계: 모델 제공업체 구성 (선택사항)**

기본적으로 Strands는 Claude 4.0 sonnet을 사용합니다. [모델](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/model-providers/amazon-bedrock/)을 변경하려면 프로젝트 루트에 `.env` 파일을 생성하고 MODEL_ID 변수를 선호하는 모델로 설정하세요.

```bash
MODEL_ID=us.anthropic.claude-sonnet-4-20250514-v1:0
```

선택한 제공업체에 대한 적절한 자격 증명이 구성되어 있는지 확인하세요. 설정 지침은 [Strands 문서](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/model-providers/amazon-bedrock/)를 확인하세요.

## AWS

AWS 이벤트에서 이 워크숍을 실행하는 경우, AWS 계정이 제공됩니다.

시작하려면 AWS 콘솔로 이동하세요. Amazon Bedrock 콘솔로 이동하고 왼쪽 메뉴에서 **Model access**를 클릭하세요:

![Header Image](/static/images/modelAccess.png)

Model access 화면에서 오른쪽 상단의 **"Enable specific models"** 버튼을 클릭하세요:

![Header Image](/static/images/enableSpecificModel.png)


모델 액세스 화면에서 **다음 모델만** 선택하고 **"Next"** 버튼을 클릭하세요:

**Anthropic**
* Claude 3.5 Haiku
* Claude 3.5 Sonnet
* Claude 3.7 Sonnet
* Claude 4.0 Sonnet
* Nova 1.0
* _...그리고 시도해보고 싶은 다른 모델들_

"Review and submit" 화면이 나타나면 선택한 모델을 검토하고, 약관을 검토한 후 Submit을 클릭하세요:

![Header Image](/static/images/modelSubmit.png)
