# Hub

## 1. Hub 개요

Hub는 여러 개의 시스템을 연결할 때 각 Port별로 Cable을 연결하여 사용할 수 있는 물리 계층 장치이다.

```text
Hub
→ 여러 시스템 연결
→ 여러 Port 사용
→ 물리 계층 장치
```

---

## 2. Hub 특징

Hub는 분배 장치의 역할을 한다.

```text
여러 Port에서 신호 입력
→ 다시 여러 Port로 신호 송출
```

기본적으로 물리 계층에서 동작한다.

```text
Hub
→ Physical Layer
```

교재에서는 Hub 장치의 특성에 따라 데이터 링크 계층 및 네트워크 계층에서도 동작할 수 있다고 설명한다.

---

## 3. 장애 발생 시

Hub 자체에 장애가 발생하면:

```text
해당 Hub에 연결된 System
→ 통신 불가
```

하지만 하나의 System에 장애가 발생한다고 해서:

```text
전체 Network 장애
→ 발생하지 않음
```

정리:

```text
Hub 장애
→ 연결된 System 전체 영향

System 1대 장애
→ 전체 Network 장애 X
```

---

## 4. Hub의 기능

```text
Network 상태 Monitoring 가능
```

또한 Repeater 기능을 가지고 있다.

```text
Hub
→ Repeater 기능 포함
→ Digital 신호 증폭 역할
```

---

## 5. Port Trunk

Port Trunk는 여러 개의 Port를 묶어 하나의 회선처럼 사용하는 방식이다.

```text
Port Trunk
→ 여러 Port를 하나의 회선처럼 사용
→ Network Traffic 해소
```

---

# 6. Hub 종류

```text
Dummy Hub
Intelligent Hub
Switching Hub
```

---

## 7. Dummy Hub

Dummy Hub는 가장 단순한 형태의 Hub이다.

```text
Dummy Hub
→ System과 Network 장치 연결
→ Repeater 구조
```

교재 예:

```text
10Mbps Hub에 5대 연결
→ 5대의 System이 대역폭을 나누어 사용
```

따라서:

```text
연결 System 수 증가
→ 성능 저하
```

핵심:

```text
Dummy Hub
→ 단순 연결
→ 대역폭 공유
→ 연결 장치 증가 시 성능 저하
```

---

## 8. Intelligent Hub

Intelligent Hub는 Network 관리 기능이 추가된 Hub이다.

```text
Intelligent Hub
→ SNMP Protocol 사용
→ Network 관리 기능 제공
```

또한:

```text
Port별 Network 연결 상태 점검 가능
```

핵심:

```text
Intelligent Hub
→ SNMP
→ Network 관리
```

---

## 9. Switching Hub

Switching Hub는 Switching 기능이 추가된 Hub이다.

```text
Switching Hub
→ Switching 기능
→ Network 효율 향상
```

또한 Repeater가 내장되어 있다.

```text
Switching Hub
→ Repeater 내장
```

가장 중요한 특징:

```text
여러 Port에서 입력
→ 특정 Port로만 Data 전송 가능
```

---

# 10. Hub 종류 비교

| 종류 | 특징 |
|---|---|
| Dummy Hub | 단순 연결, 대역폭 공유, Repeater 구조 |
| Intelligent Hub | SNMP 사용, Network 관리 |
| Switching Hub | Switching 기능, 특정 Port 전송 가능 |

---

# 시험 직전 암기

```text
Hub
→ 물리 계층
→ 여러 System 연결
→ 분배 장치
```

```text
Hub 장애
→ 연결된 System 통신 불가

System 1대 장애
→ 전체 Network 장애 X
```

```text
Hub
→ Repeater 기능
→ Digital 신호 증폭
```

```text
Port Trunk
→ 여러 Port를 하나의 회선처럼 사용
→ Network Traffic 해소
```

```text
Dummy Hub
→ 단순
→ 대역폭 공유
→ System 증가 시 성능 저하
```

```text
Intelligent Hub
→ SNMP
→ Network 관리
```

```text
Switching Hub
→ Switching 기능
→ 특정 Port로 Data 전송
```

## 자주 헷갈리는 부분

```text
Dummy Hub
→ 대역폭 공유

Intelligent Hub
→ SNMP

Switching Hub
→ 특정 Port 전송
```

```text
Repeater
→ 신호 증폭/재생

Hub
→ Repeater 기능 포함 가능
```
