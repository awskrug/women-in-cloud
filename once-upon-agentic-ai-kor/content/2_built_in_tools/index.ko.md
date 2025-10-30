---
title: "⚔️ 챕터 2: 모험가의 무기고 - 내장 도구 사용"
weight: 20
---

![Header Image](/static/images/header_2.png)

_"현명한 모험가는 적절한 장비 없이는 모험을 떠나지 않습니다..."_

무기고에 오신 것을 환영합니다, 코딩 용사여! 이 챕터에서는 AI 에이전트에 강력한 내장 마법 도구를 장비하는 방법을 배우게 됩니다. 어떤 모험가도 맨손으로 드래곤에 맞서지 않듯이, 어떤 에이전트도 적절한 도구 없이는 복잡한 퀘스트에 도전해서는 안 됩니다.

## 🎯 퀘스트 목표

도구는 에이전트의 능력을 확장하는 주요 메커니즘으로, 단순한 텍스트 생성을 넘어선 작업을 수행할 수 있게 합니다. 도구는 에이전트가 외부 시스템과 상호작용하고, 데이터에 접근하며, 환경을 조작할 수 있게 합니다. `http_request` 도구를 마스터하여 기본 에이전트를 웹에 정통한 정보 수집가로 변환하세요. `2_built_in_tools/agent_with_built_in_tools.py` 파일을 완료하여 웹 콘텐츠를 가져오고 분석할 수 있는 에이전트를 생성할 것입니다.

## 🏺 고대 무기고: 내장 도구

Strands는 즉시 사용할 수 있는 전설적인 유물들로 미리 마법이 부여되어 있습니다. 다음은 몇 가지 예입니다:

- **🌐 `http_request`**: 먼 영역에서 콘텐츠를 가져올 수 있는 신비로운 웹 위버
- **⏰ `current_time`**: 현재 날짜와 시간을 보여주는 시계
- **🧮 `calculator`**: 수학적 마법을 위한 마법이 부여된 주판
- **📁 `file_read`/`file_write`**: 양피지를 읽고 쓰기 위한 마법 두루마리
- **🐍 `python_repl`**: Python 주문을 시전하기 위한 코드 실행실
- **🌐 `browser`**: 복잡한 상호작용을 위한 자동화된 웹 네비게이터

[문서에서 완전한 무기고 보기 →](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/tools/community-tools-package/)

## 📜 신성한 단계

### 1단계: 웹 위버 소환 🌐
**TODO**: `http_request` 내장 도구 가져오기

`http_request` 도구는 디지털 영역의 광대한 정보 네트워크로의 관문입니다. 웹 페이지를 가져오고, API를 호출하며, 먼 서버에서 데이터를 검색할 수 있습니다. `strands_tools` 라이브러리에서 도구를 가져오는 방법의 [예제](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/tools/community-tools-package/#human-in-the-loop-with-handoff_to_user)가 있습니다.

### 2단계: 에이전트 무장 🗡️
**TODO**: 에이전트의 무기고에 `http_request` 도구 추가

에이전트에 웹 위버를 장비하여 초기 지식을 넘어서 인터넷에서 새로운 정보를 가져올 수 있게 하세요. [여기](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/tools/community-tools-package/#human-in-the-loop-with-handoff_to_user) 문서에서 에이전트에 도구를 전달하는 방법의 예제를 보여줍니다.

## 🔧 향상된 에이전트 테스트

두 TODO를 완료한 후 스크립트를 실행하세요:

```bash
python agent_with_built_in_tools.py
```

에이전트가 다음과 같이 작동하는 것을 지켜보세요:
1. D&D 창조자에 대한 퀘스트를 받습니다
2. `http_request` 도구를 사용하기로 자동으로 결정합니다
3. 위키피디아 페이지 콘텐츠를 가져옵니다
4. HTML을 분석하여 역사적 정보를 찾습니다
5. D&D의 전설적인 디자이너들의 이름을 여러분에게 보고합니다

에이전트가 제공한 답변이 정확한지 [여기](https://en.wikipedia.org/wiki/Dungeons_%26_Dragons)에서 확인할 수 있습니다.

## 🌟 보너스 퀘스트: 비전 코덱스 챌린지

더 고급 모험을 준비하셨나요? `2_built_in_tools/bonus_quest.py`에 있는 이 전설적인 챌린지를 시도해보세요:

**피보나치 두루마리 퀘스트**: `python_repl`과 `file_write` 도구로 장비된 에이전트를 생성하여 다음을 수행할 수 있게 하세요:
1. 피보나치 수열 코드를 포함한 마법 두루마리(Python 파일) 생성
2. 그 힘을 시연하기 위해 주문 실행
3. 수학적 아름다움의 시각적 표현 생성

**⚠️ 중요: 대화형 도구를 위한 디버그 로그 활성화!**

이 보너스 퀘스트를 시도하기 전에 도구 동의 프롬프트를 보기 위해 `DEBUG` 로깅을 **반드시** 활성화해야 합니다. `python_repl`과 `file_write` 도구는 실행 전에 여러분의 허가를 요청하며, 이를 수락하려면 터미널에서 이러한 프롬프트를 볼 수 있어야 합니다. [로깅 활성화 문서](https://strandsagents.com/latest/documentation/docs/user-guide/observability-evaluation/logs/#configuring-logging)가 있습니다.

**보게 될 것**: 에이전트가 파일을 생성하거나 코드를 실행하려고 할 때 다음과 같은 프롬프트를 볼 수 있습니다:
```
DEBUG | strands.tools | Tool 'file_write' requires consent. Do you want to allow this action? (y/n):
```

마법 작업을 진행하도록 도구를 허용하려면 `y`를 입력하고 Enter를 누르기만 하면 됩니다!

프로젝트 루트에 피보나치 두루마리가 성공적으로 생성되었는지 확인하세요.

## 🛡️ 안전 마법

**도구 동의 프롬프트**: 기본적으로 특정 강력한 도구들(`file_write`와 `python_repl` 같은)은 실행 전에 여러분의 허가를 요청합니다. 이 보호 장치는 잠재적으로 시스템을 변경하는 작업에 대한 제어를 유지하도록 보장합니다.

**테스트용 우회** (주의해서 사용):
```bash
export BYPASS_TOOL_CONSENT=true
```

## 🎉 퀘스트 완료!

축하합니다, 도구 마스터! 에이전트를 웹 액세스의 힘으로 성공적으로 무장시켰습니다. 디지털 동반자가 이제 훈련 데이터를 넘어서 광대한 디지털 영역에서 실시간 정보를 가져올 수 있습니다.

**마스터한 내용:**
- ✅ 내장 도구 가져오기 및 구성
- ✅ 에이전트가 언제 도구를 사용할지 자율적으로 선택하는 방법 이해
- ✅ 웹 콘텐츠 가져오기 및 정보 추출
- ✅ 에이전트 자율성과 사용자 제어 사이의 균형

**획득한 전리품:**
- 🌐 웹 스크래핑 기능
- 📊 실시간 정보 액세스
- 🔧 더 복잡한 도구 조합을 위한 기반

**다음 모험**: 챕터 3으로 여행하여 자신만의 맞춤 마법 도구를 제작하고 서사시적인 D&D 모험을 위한 전설적인 주사위 굴리기 도구를 만드는 방법을 배우세요!

---

_"에이전트에게 하나를 알려주면 그 순간만 알 뿐이지만, 도구를 주면 평생 새로운 사실을 찾아낼 수 있습니다!"_ ⚔️✨
