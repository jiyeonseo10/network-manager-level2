# SNMP

네트워크관리사 2급 TCP/IP 파트의 **SNMP(Simple Network Management Protocol)** 내용을 정리한다.

---

## 1. SNMP 개요

SNMP는 **Simple Network Management Protocol**의 약자이다.

운영 중인 네트워크의 안정성과 효율성을 높이기 위해 다음 정보를 실시간으로 수집하고 분석하는 네트워크 관리 시스템에서 사용된다.

- 구성 정보
- 장애 정보
- 통계 정보
- 상태 정보

```text
SNMP
→ Simple Network Management Protocol
→ 네트워크 관리 프로토콜
→ 구성 / 장애 / 통계 / 상태 정보 수집
```

---

## 2. NMS

NMS는 **Network Management System**이다.

SNMP 프로토콜을 이용하여 네트워크 정보를 수집한다.

```text
NMS
→ Network Management System
→ SNMP를 사용하여 네트워크 정보 수집
```

---

## 3. SNMP 동작 구조

SNMP는 Manager와 Agent 구조로 동작한다.

```text
Manager
↔
Agent
```

### Manager

네트워크를 관리하는 쪽이다.

```text
Manager
→ Management Application
→ 관리 명령 전송
```

### Agent

관리 대상 장비 측에서 동작한다.

```text
Agent
→ 관리 대상 장비
→ MIB 정보를 보유
```

---

## 4. MIB

MIB는 **Management Information Base**이다.

SNMP에서 모니터링해야 하는 객체(Object)의 정보를 가지고 있다.

책 그림에서는 계층형 구조로 나타난다.

```text
MIB
→ Management Information Base
→ 모니터링할 Object 정보
→ 계층형 구조
```

---

## 5. Get

Get은 장비의 관리 정보를 읽는 명령이다.

예:

- 장비 상태
- 가동 시간

```text
Get
→ 관리 정보 읽기
→ 상태 / 가동 시간 확인
```

---

## 6. Get-Next

Get-Next는 정보가 계층 구조를 가지므로 해당 트리보다 하위 계층의 정보를 읽는 명령이다.

```text
Get-Next
→ 다음 정보 조회
→ 계층 구조의 하위 정보 읽기
```

---

## 7. Set

Set은 장비의 MIB를 조작하여 장비를 제어하는 명령이다.

책에서는 다음 용도로 설명한다.

- 초기화
- 장비 재구성

```text
Set
→ MIB 조작
→ 장비 제어
→ 초기화 / 재구성
```

---

## 8. Trap

Trap은 Agent가 관리자에게 보고하는 Event이다.

책에서는 다음과 같이 설명한다.

- 경고
- 고장 통지
- 미리 설정된 유형의 보고서 생성

```text
Trap
→ Agent가 Manager에게 보고
→ Event
→ 경고 / 고장 통지
```

---

## 9. SNMP 명령 비교

| 명령 | 기능 |
|---|---|
| Get | 장비의 관리 정보 읽기 |
| Get-Next | 다음 하위 정보 읽기 |
| Set | MIB 조작 및 장비 제어 |
| Trap | Agent가 관리자에게 Event 보고 |

```text
Get
→ 읽기

Get-Next
→ 다음 읽기

Set
→ 변경 / 제어

Trap
→ 보고 / 경고
```

---

## 10. 시험 직전 암기

```text
SNMP
→ Simple Network Management Protocol
→ 네트워크 관리

NMS
→ Network Management System
→ SNMP로 네트워크 정보 수집

Manager
→ 관리하는 쪽

Agent
→ 관리 대상 장비

MIB
→ Management Information Base
→ 모니터링할 Object 정보
→ 계층형 구조

Get
→ 관리 정보 읽기

Get-Next
→ 다음 하위 정보 읽기

Set
→ MIB 조작
→ 장비 제어

Trap
→ Agent가 관리자에게 보고
→ 경고 / 고장 통지
```
