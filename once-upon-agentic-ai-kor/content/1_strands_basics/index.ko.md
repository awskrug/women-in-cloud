---
title: "🧙‍♂️ 챕터 1: 에이전트 소환의 기술"
weight: 10
---

![Header Image](/static/images/header_1.png)


Strands의 신비로운 기술에 대한 첫 번째 수업에 오신 것을 환영합니다! 이 기초 챕터에서는 여러분의 첫 번째 AI 에이전트 동반자를 소환하는 방법을 배우게 됩니다 - 코드의 영역을 통해 여러분의 가이드 역할을 할 디지털 동료입니다.

## 🎯 퀘스트 목표

`1_strands_basics/simple_agent.py` 파일을 완료하여 에이전트 생성의 기본 의식을 마스터하세요. 빈 TODO 주석을 모험을 위한 살아 숨쉬는 AI 동반자로 변환할 것입니다!


## 📜 신성한 단계

### 1단계: 보이지 않는 것을 보는 시야 활성화 👁️
**TODO**: 에이전트가 무엇을 생각하는지 볼 수 있도록 디버그 로깅 추가

에이전트를 소환하기 전에, 에이전트의 마음을 들여다볼 수 있는 신비로운 시야를 활성화하는 것이 현명합니다. [디버그 로깅](https://strandsagents.com/latest/documentation/docs/user-guide/observability-evaluation/logs/#configuring-logging)은 디지털 동반자의 숨겨진 작동 방식을 드러냅니다.

다양한 로그 레벨이 있습니다: `DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL`. 로그 레벨을 조정하여 배후에서 일어나는 일을 볼 수 있습니다. 터미널을 로그로 넘치게 하지 않으면서 잠재적 문제를 파악하기 위해 `WARNING`을 권장합니다.

### 2단계: 디지털 동반자 제작 🤖
**TODO**: 다음 [시스템 프롬프트](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/agents/prompts/)로 에이전트 생성: `"You are a game master for a Dungeon & Dragon game"`

시스템 프롬프트는 에이전트의 캐릭터 시트입니다 - 에이전트의 성격, 지식, 행동을 정의합니다. 디지털 동료의 배경 스토리를 작성하는 것이라고 생각하세요.

기본적으로 Strands는 Amazon Bedrock의 Claude 4.0을 호출합니다.

### 3단계: 창조물 깨우기 🌟
**TODO**: `"Hi, I am an adventurer ready for adventure!"`와 같은 기본 주문으로 에이전트 소환

창조물에 생명을 불어넣을 시간입니다! 이 첫 번째 상호작용은 소환 의식이 성공했는지 테스트할 것입니다. 수행 방법의 예제는 문서의 [첫 번째 예제](https://strandsagents.com/latest/documentation/docs/)를 참고하세요.


## 🎲 창조물 테스트

모든 TODO를 완료한 후 스크립트를 실행하세요:

```bash
python simple_agent.py
```

성공하면, 새로 소환된 게임 마스터가 열정적으로 응답하며, 아마도 서사시적인 D&D 모험을 위한 장면을 설정할 것입니다!

## 🎉 퀘스트 완료!

축하합니다! 첫 번째 AI 에이전트를 성공적으로 소환했습니다. 디지털 게임 마스터가 이제 플레이어들을 서사시적인 모험으로 안내할 준비가 되었습니다.

**학습한 내용:**
- ✅ 에이전트의 내부 작동을 보기 위해 디버그 로깅을 활성화하는 방법
- ✅ Strands를 사용하여 첫 번째 AI 에이전트를 생성하는 방법
- ✅ 에이전트 행동을 형성하는 데 있어 시스템 프롬프트의 중요성
- ✅ 기본 에이전트 상호작용 및 테스트 패턴

**다음 모험**: 챕터 2로 가서 에이전트에 마법 도구와 능력을 장비하는 방법을 배우세요!

---

_"마법사는 늦지도 않고, 이르지도 않습니다. 그는 정확히 의도한 때에 도착합니다... 잘 구성된 에이전트처럼!"_ 🧙‍♂️✨
