---
title: "🏰 챕터 5: 대연합 - 에이전트 간 마스터리"
weight: 50
---

![Header Image](/static/images/header_5.png)

_"위대한 퀘스트는 혼자서 완수되지 않습니다. 가장 강력한 영웅들도 동맹이 필요합니다..."_

여정의 가장 서사시적인 챕터에 오신 것을 환영합니다, 코딩 용사여! 지금까지 에이전트에 도구를 주는 방법을 보았습니다. 이제 여러 에이전트가 각자의 도구 세트와 함께 협력하도록 할 시간입니다. 여기서 [에이전트 간(A2A)](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/multi-agent/agent-to-agent/)을 사용한 **에이전트 오케스트레이션**의 고대 기술을 배우게 됩니다 - 여러 전문 AI 동반자들이 완벽한 조화로 작동하도록 지휘하는 것입니다. 각 에이전트가 고유한 전문성을 가져와 진정으로 몰입감 있는 모험을 만드는 전설적인 D&D 게임 마스터 시스템을 단조할 것입니다.

## 🎯 퀘스트 목표

궁극의 D&D 경험을 운영하기 위해 함께 작동하는 세 명의 전문 에이전트 동맹인 **대연합**을 구축하세요:

- **🧙‍♂️ 규칙의 현자**: D&D 지식과 메커니즘의 현명한 수호자
- **⚔️ 캐릭터 기록자**: 영웅, 스탯, 전설적 이야기의 마스터
- **👑 대 오케스트레이터**: 모든 모험을 조정하는 최고 게임 마스터

## 🏰 전설의 아키텍처

```
        🧙‍♂️ 규칙의 현자    ⚔️ 캐릭터 기록자    🎲 주사위 오라클
           (포트 8000)        (포트 8001)      (포트 8080)
                │                  │                │
                └──────────────────┼────────────────┘
                                   │
                        👑 대 오케스트레이터
                             (포트 8009)
                           [마스터의 왕좌]
```

## 🗡️ 동맹의 힘

여러분의 **대연합**은 전설적인 능력을 갖게 됩니다:
- **📚 고대 지혜**: 모든 D&D 규칙과 메커니즘에 즉시 접근
- **👥 영웅 제작**: 전설적인 캐릭터 시트 생성 및 관리
- **🎲 운명 조작**: 주사위 굴리기 및 운명 결정
- **🎭 서사시적 스토리텔링**: 완벽한 조정으로 다층 모험 오케스트레이션

## 📚 전제 조건

이전 챕터를 완료하고 다음을 이해했는지 확인하세요:
- 기본 Strands 에이전트
- `@tool` 데코레이터를 사용한 도구 생성
- MCP 통합

## 🧙‍♂️ 1부: 규칙의 현자 깨우기

현자가 깨어나기 전에 먼저 전설적인 **지식 금고**를 단조해야 합니다! 고대 D&D 기본 규칙을 마법적 텍스트 조각으로 변환하고 신성한 `utils/dnd_knowledge_base/` ChromaDB에 저장해야 합니다. 이 마법이 부여된 저장소에는 모험가들이 제기할 수 있는 모든 규칙 질문에 답하는 데 필요한 모든 지혜가 포함될 것입니다.

### 🏛️ 지식 금고 생성의 신성한 의식

**⚠️ 중요한 퀘스트**: 진행하기 전에 이 의식을 완료해야 하며, 그렇지 않으면 현자가 무력하게 남을 것입니다!

#### 🔍 1단계: 고대 서적 찾기
공식 Wizards of the Coast 아카이브에서 **D&D 기본 규칙 2018 PDF**를 찾으세요:
- 신성한 [규칙서](https://media.wizards.com/2018/dnd/downloads/DnD_BasicRules_2018.pdf) 다운로드
- **중요**: 파일명이 정확히 `DnD_BasicRules_2018.pdf`여야 합니다

#### 📚 2단계: 서적을 신성한 방에 배치
PDF를 목적지 위치로 이동:
- `DnD_BasicRules_2018.pdf`를 `5_a2a_integration/utils/` 폴더에 배치
- 서적이 `create_knowledge_base.py` 스크립트와 함께 있어야 합니다

#### 🔮 3단계: 변환 의식 수행
PDF를 검색 가능한 지식으로 변환하는 고대 주문을 시전:
```bash
python create_knowledge_base.py
```
**⚠️ 중요**: `utils` 방 내에서 이 주문을 시전해야 하며, 그렇지 않으면 의식이 실패합니다!

지식 금고가 성공적으로 단조되었는지 확인:
- `5_a2a_integration/utils/dnd_knowledge_base/` 폴더가 존재하는지 확인
- 그 안에 `chroma.sqlite3`과 다른 신비한 파일들이 있는지 확인
- 콘솔에 "Knowledge base creation complete!"가 표시되어야 합니다

### 의식 작업:

#### 📚 TODO 1: 지혜 도관 단조
`agents/rules_agent/rules_agent.py`에서 신성한 `query_dnd_rules` 함수 완료:

```python
agent = Agent(
    # TODO: 다음으로 에이전트 구성:
    # - model: 선택사항
    # - tools: query_dnd_rules 도구를 포함한 목록
    # - name: "Rules Agent"
    description= DESCRIPTION,
    system_prompt= SYSTEM_PROMPT
)
```
[여기](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/multi-agent/agent-to-agent/#creating-an-a2a-server) 문서의 예제를 확인하세요

#### 🏰 TODO 2: 현자의 탑 건설
신비로운 통신 첨탑 구축

```python
# TODO: 다음으로 A2AServer 인스턴스 생성:
# - agent: 위에서 생성한 에이전트 인스턴스
# - port: 8000 (규칙 에이전트 포트)
a2a_server = None
```
[여기](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/multi-agent/agent-to-agent/#creating-an-a2a-server) 문서의 예제를 확인하세요

#### 🌟 TODO 3: 탑 문 열기
깨어남 의식 완료:

```python
if __name__ == "__main__":
    # TODO: A2A 서버 시작
    pass
```
[여기](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/multi-agent/agent-to-agent/#creating-an-a2a-server) 문서의 예제를 확인하세요

성공하면 현자가 포트 8000의 탑에서 고대 지식을 손끝에 두고 준비할 것입니다!

## ⚔️ 2부: 캐릭터 기록자 깨우기

**캐릭터 기록자**를 보세요 - 영웅적 이야기와 전설적 통계의 마스터! 이 에이전트는 세 가지 강력한 유물을 휘두릅니다 (연구를 위해 이미 단조됨):

- **🏗️ `create_character`**: 완전한 배경 스토리와 능력을 가진 새로운 영웅 탄생
- **🔍 `find_character_by_name`**: 이름으로 영역 전체에서 영웅 찾기
- **📜 `list_all_characters`**: 연대기에 있는 모든 영웅 공개

**이 전설적인 도구들을 연구**하여 데이터클래스, 데이터베이스, 복잡한 캐릭터 관리와 함께 고급 패턴을 이해하세요!

### 의식 작업:

#### ⚔️ TODO 1: 캐릭터 기록자 소환
`agents/character_agent/character_agent.py`에서 기록자를 그들의 운명에 묶기:

```python
agent = Agent(
    # TODO: 다음으로 캐릭터 에이전트 구성:
    # - model: 선택사항
    # - tools: 도구 목록
    # - name: "Character Creator Agent"
    description= DESCRIPTION,
    system_prompt= SYSTEM_PROMPT
)
```

[여기](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/multi-agent/agent-to-agent/#creating-an-a2a-server) 문서의 예제를 확인하세요

#### 🏰 TODO 2: 영웅의 전당 건설
```python
# TODO: 다음으로 A2AServer 인스턴스 생성:
# - agent: 위에서 생성한 에이전트 인스턴스
# - port: 8001 (캐릭터 에이전트 포트)
a2a_server = None
```
[여기](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/multi-agent/agent-to-agent/#creating-an-a2a-server) 문서의 예제를 확인하세요

#### 🌟 TODO 3: 전당 문 열기
```python
if __name__ == "__main__":
    # TODO: A2A 서버 시작
    pass
```
[여기](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/multi-agent/agent-to-agent/#creating-an-a2a-server) 문서의 예제를 확인하세요

포트 8001에서 영웅의 전당이 열리는 것을 지켜보세요. 새로운 전설을 단조할 준비가 되었습니다!

## 👑 3부: 대 오케스트레이터 즉위

**대 오케스트레이터**를 보세요 - 전체 동맹을 지휘하는 최고 게임 마스터! 이 전설적인 존재는 모든 에이전트를 조정하고, 서사시적 내러티브를 엮으며, 모험가들이 여러분의 영역에 들어가는 데 사용하는 신비로운 API 게이트웨이를 제공합니다.

**오케스트레이터의 신성한 힘:**
- **🌐 에이전트 통신**: A2A 마법을 통해 동맹 지휘
- **🎲 운명 통합**: 운명 굴리기를 위한 MCP 주사위 오라클 채널링
- **🎭 서사시적 스토리텔링**: 여러 에이전트의 응답을 위대한 내러티브로 엮기
- **⚡ 번개 응답**: 신성한 FastAPI 포털을 통한 즉시 액세스 제공

### 최고 의식 작업:

#### 🎲 TODO 1: 주사위 오라클 채널링

```python
# TODO: 주사위 굴리기 서비스를 위한 MCP 클라이언트 생성
# streamablehttp_client("http://localhost:8080/mcp")를 반환하는 람다로 MCPClient 초기화
mcp_dice_client = None
```
힌트: 막히면 챕터 4를 다시 보세요 😉

#### 🤖 TODO 2: A2A 클라이언트 생성
`ask_agent` 함수에서:
```python
# TODO: A2AClientToolProvider와 알려진 에이전트 URL 목록을 전달하여 A2A 클라이언트 생성
```
[여기](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/multi-agent/agent-to-agent/#installation_1) 문서의 예제를 확인하세요


#### 🛠️ TODO 3: MCP 도구 가져오기
```python
# TODO: MCP 도구 가져오기
```

#### TODO 4: 게임마스터 에이전트 생성
```python
# TODO: A2A와 MCP 도구 모두로 게임마스터 에이전트 생성
agent = Agent(
    # model=선택사항,
    # tools= A2A와 MCP 도구 목록,
    system_prompt=SYSTEM_PROMPT
)
```

대 오케스트레이터가 왕좌에 오르고 서사시적인 모험을 지휘할 준비가 될 것입니다!

## ⚔️ 4부: 대연합 깨어남 의식

### 🏰 완전한 동맹 소환:

4개의 다른 터미널을 열고 다음 명령 실행
(경고: 아래와 같이 각 폴더의 루트에서 모든 에이전트를 실행해야 합니다)

**🎲 주사위 오라클 깨우기** (신성한 터미널 0):
```bash
cd 4_mcp_integration
python dice_roll_mcp_server.py
```
*대 오케스트레이터는 챕터 4의 신비한 주사위 힘이 필요합니다!*

**🧙‍♂️ 규칙의 현자 깨우기** (신성한 터미널 1):
```bash
cd 5_a2a_integration/agents/rules_agent
python rules_agent.py
```

**⚔️ 영웅의 전당 열기** (신성한 터미널 2):
```bash
cd 5_a2a_integration/agents/character_agent
python character_agent.py
```

**👑 마스터의 왕좌 오르기** (신성한 터미널 3):
```bash
cd 5_a2a_integration/agents/gamemaster_orchestrator
python gamemaster_orchestrator.py
```

### 🎭 서사시적 모험 테스트:

신비한 `test/test.http` 두루마리를 통해 요청을 채널링하거나 다음 주문을 사용하세요:

```bash
# 📚 고대 지혜 상담
curl -X POST http://0.0.0.0:8009/inquire \
  -H "Content-Type: application/json" \
  -d '{"question": "What are the rules for dexterity checks?"}'

# ⚔️ 새로운 영웅 제작
curl -X POST http://0.0.0.0:8009/inquire \
  -H "Content-Type: application/json" \
  -d '{"question": "Create a character named Thorin, a Dwarf Fighter with strength 16, dexterity 12, constitution 15"}'

# 🔍 영웅 지식 찾기
curl -X POST http://0.0.0.0:8009/inquire \
  -H "Content-Type: application/json" \
  -d '{"question": "What is Thorin'\''s constitution?"}'

# 🎲 주사위 오라클 호출
curl -X POST http://0.0.0.0:8009/inquire \
  -H "Content-Type: application/json" \
  -d '{"question": "Roll a d20 for initiative!"}'
```

**🎲 마법이 펼쳐지는 것을 지켜보세요:**
1. 대 오케스트레이터가 여러분의 퀘스트를 받습니다
2. 적절한 동맹 구성원을 자동으로 발견하고 상담합니다
3. 현자가 고대 규칙 지혜를 제공합니다
4. 기록자가 영웅적 운명을 관리합니다
5. 모든 응답이 서사시적 내러티브로 엮어집니다!

## 🎯 학습 목표

이 챕터를 완료하면 다음을 이해하게 됩니다:

- **멀티 에이전트 아키텍처**: 전문 에이전트로 시스템 설계하는 방법
- **A2A 통신**: 에이전트 간 메시징 및 발견
- **서비스 오케스트레이션**: 여러 서비스 조정
- **지식 베이스 통합**: 정보 검색을 위한 벡터 데이터베이스 사용
- **MCP 프로토콜**: 외부 도구 및 서비스 통합
- **분산 시스템**: 복원력 있고 확장 가능한 에이전트 네트워크 구축

## 🏆 보너스 챌린지

1. **새 에이전트 추가**: 전투 메커니즘을 위한 전투 에이전트 생성
2. **발견 향상**: 동적 에이전트 발견 구현
3. **지속성 추가**: 게임 세션 및 캐릭터 진행 저장
4. **모험 생성**: 다단계 퀘스트 워크플로우 구축
5. **인증 추가**: API 엔드포인트 보안

## 🎉 축하합니다!

완전한 멀티 에이전트 D&D 시스템을 구축했습니다! 이 아키텍처 패턴은 복잡한 문제를 해결하기 위해 전문 에이전트들이 함께 작동해야 하는 많은 도메인에 적용할 수 있습니다.

여러분의 시스템은 프로덕션 규모의 AI 애플리케이션을 구축하는 데 필수적인 분산 AI 시스템, 마이크로서비스 아키텍처, 에이전트 오케스트레이션의 핵심 개념을 보여줍니다.

다음 모험을 준비하셨나요? 솔루션 폴더의 고급 패턴을 확인해보세요! 🚀
