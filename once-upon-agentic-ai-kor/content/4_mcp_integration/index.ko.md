---
title: "🌐 챕터 4: 차원 포털 - MCP 통합 (모델 컨텍스트 프로토콜)"
weight: 40
---

![Header Image](/static/images/header_4.png)

_"먼 영역으로의 포털 열기..."_

차원 연결의 비전 기술에 오신 것을 환영합니다, 용감한 여행자여! 이 챕터에서는 [모델 컨텍스트 프로토콜(MCP)](https://strandsagents.com/latest/documentation/docs/user-guide/concepts/tools/mcp-tools/)의 신비로운 기술을 배우게 됩니다 - 에이전트가 외부 서비스에 연결하고 먼 영역의 힘을 호출할 수 있게 하는 마법입니다.

## 🎯 퀘스트 목표

두 구성 요소 시스템을 생성하여 MCP 포털의 기술을 마스터하세요:
1. **MCP 서버** (`4_mcp_integration/dice_roll_mcp_server.py`) - 주사위 굴리기 서비스를 노출
2. **MCP 클라이언트** (`4_mcp_integration/gamemaster_mcp_client.py`) - 서버에 연결하고 그 도구를 사용

## 🔮 MCP 철학

모델 컨텍스트 프로토콜은 도구를 에이전트로부터 분리할 수 있게 합니다:
- **🏰 MCP 서버**: 표준화된 프로토콜을 통해 전문 도구 노출
- **🧙‍♂️ MCP 클라이언트**: 서버에 연결하여 그 도구 사용
- **🌉 이점**: 재사용성, 확장성, 관심사 분리

## 📜 1부: MCP 서버 단조 (`dice_roll_mcp_server.py`)

### 1단계: 필요한 모듈 시전 📚
**TODO**: `mcp.server`에서 `FastMCP` 가져오기

MCP 서버를 생성하려면 `FastMCP` 클래스를 가져와야 합니다. `random`과 `logging` 모듈은 이미 가져와져 있습니다. [문서](https://strandsagents.com/latest/documentation/docs/examples/python/mcp_calculator/#first-create-a-simple-mcp-server)를 확인하세요.

### 2단계: MCP 서버 생성 🏰
**TODO**: 포트 8080에서 "D&D Dice Roll Service"라는 이름으로 MCP 서버 생성

지정된 `name`과 `port` 8080으로 `FastMCP` 인스턴스를 생성하세요. [문서](https://strandsagents.com/latest/documentation/docs/examples/python/mcp_calculator/#first-create-a-simple-mcp-server)를 확인하세요.

### 3단계: 서버 실행 🚀
**TODO**: MCP 서버 실행

main에서 이 [예제](https://strandsagents.com/latest/documentation/docs/examples/python/mcp_calculator/#first-create-a-simple-mcp-server)처럼 `streamable-http`로 정의된 전송으로 MCP 서버를 시작하는 줄을 추가하세요.
`@mcp.tool()` 데코레이터는 이미 구현되어 있습니다!


## 📜 2부: MCP 클라이언트 생성 (`gamemaster_mcp_client.py`)

이 부분은 [문서](https://strandsagents.com/latest/documentation/docs/examples/python/mcp_calculator/#first-create-a-simple-mcp-server)의 이 예제를 참조하세요.

### 1단계: 연결 도구 가져오기 🔗
**TODO**: `Agent`, `MCPClient`, `streamablehttp_client` 가져오기

### 2단계: 차원 연결 설정 🌉
**TODO**: "http://localhost:8080/mcp"에 연결하는 streamable http MCPClient 생성

주사위 서버에 연결하는 MCPClient 인스턴스를 생성하세요. `streamablehttp_client("http://localhost:8080/mcp")`를 반환하는 람다 함수를 사용하세요.

### 3단계: 컨텍스트 매니저 사용 🔒
**TODO**: `MCPClient`를 컨텍스트 매니저(with 문)에서 사용

적절한 연결 관리를 보장하기 위해 `MCPClient`를 사용하는 `with` 문으로 에이전트 코드를 감싸세요.

### 4단계: 사용 가능한 도구 가져오기
**TODO**: `list_tools_sync()`를 사용하여 MCP 서버에서 사용 가능한 도구 가져오기

`MCPClient`에서 `list_tools_sync()` 메서드를 호출하여 서버에서 사용 가능한 도구를 검색하세요.
print 문을 사용하려면 목록을 `mcp_tools`라는 변수에 넣으세요.

### 5단계: 에이전트에 도구 추가 🤖
**TODO**: MCP 도구를 게임마스터 에이전트에 추가

## 🎲 MCP 시스템 테스트

### 1단계: 서버 실행
```bash
python dice_roll_mcp_server.py
```
"Starting D&D Dice Roll MCP Server on port 8080..."이 보여야 합니다.

### 2단계: 클라이언트 실행 (다른 터미널에서)
```bash
python gamemaster_mcp_client.py
```

### 3단계: 주사위 굴리기 테스트
다음 명령을 시도해보세요:
- "Roll a d20"
- "Roll a d6"
- "Roll a d100"
- "Roll 4d6 for ability scores"

## 🌟 MCP 아키텍처의 이점

**🔄 재사용성**: 주사위 서버는 여러 클라이언트에서 사용할 수 있습니다
**📈 확장성**: 서버에 새 도구를 쉽게 추가할 수 있습니다
**🛡️ 격리**: 서비스가 분리되고 독립적입니다
**🔧 유지보수**: 다른 서비스에 영향을 주지 않고 하나의 서비스를 업데이트할 수 있습니다

## 🎉 퀘스트 완료!

축하합니다, 포털 마스터! 모델 컨텍스트 프로토콜의 신비로운 기술을 마스터했습니다. 시스템이 이제 다음을 수행할 수 있습니다:

**마스터한 내용:**
- ✅ 도구를 노출하는 MCP 서버 생성
- ✅ 원격 서비스에 MCP 클라이언트 연결
- ✅ Strands 에이전트에 MCP 도구 통합
- ✅ 에이전트 시스템을 위한 분산 아키텍처

**획득한 전리품:**
- 🌐 MCP 주사위 굴리기 서버
- 🧙‍♂️ 운명의 여신과 함께하는 MCP 클라이언트
- 🔗 분산 아키텍처 기술
- 🎲 중앙화되고 재사용 가능한 주사위 시스템

**다음 모험**: 챕터 5로 가서 에이전트 간(A2A) 통신을 발견하고 전문 에이전트 팀을 오케스트레이션하는 방법을 배우세요!

---

_"잘 열린 포털은 천 개의 로컬 도구보다 가치가 있습니다!"_ 🌐✨
