# RIP / OSPF / ICMP

## 1. RIP(Routing Information Protocol)

RIP는 대표적인 거리 벡터(Distance Vector) 기반 라우팅 프로토콜이다.

```text
RIP
→ Distance Vector
→ Hop Count 사용
→ 거쳐 가는 Router 수가 적은 경로 선택
```

### RIP 핵심 특징

```text
Hop Count
→ 경로를 결정하기 위한 거리 값

16 Hop 이상
→ 도달 불가능
→ Packet 폐기

30초마다
→ Broadcasting을 통해 Routing Table 관리

180초 동안 새로운 Routing 정보가 수신되지 않으면
→ 해당 경로를 이상 상태로 간주
```

RIP는 수신된 목적지의 거리 값과 현재 거리 값을 비교하여 더 작은 값을 기준으로 Routing Table을 변경한다.

### RIP의 한계

```text
Routing 정보 변경 시
→ 모든 망에 적용

따라서
→ 큰 규모 Network에는 적합하지 않음
```

---

## 2. Routing Table 확인

Windows에서 Routing Table은 다음 명령으로 확인할 수 있다.

```text
netstat -r
```

또는

```text
route PRINT
```

---

## 3. OSPF(Open Shortest Path First)

OSPF는 대규모 Network에서 사용하는 Link State 방식의 Routing Protocol이다.

```text
OSPF
→ Link State
→ 대규모 Network
→ 최단 경로 계산
```

OSPF는 다음 정보를 종합적으로 고려한다.

```text
대역폭
지연
처리량
신뢰성
```

그리고 Link의 Cost에 따라 최단 경로를 결정한다.

### 알고리즘

```text
Dijkstra
→ 최단 경로 계산
```

---

## 4. OSPF 동작 원리

```text
Link 상태 정보 사용
→ Network 상태 판단

Network를 Area로 구분

Link 변화 감지
→ 변경된 Link 정보만 즉시 전달
→ Routing Table을 빠르게 갱신
```

즉,

```text
RIP
→ 주기적으로 Routing 정보 전달

OSPF
→ 변화가 발생했을 때 변경 정보 전달
```

---

## 5. OSPF Router 계위

### ABR

```text
ABR
→ Area Border Router
→ Area와 Backbone 연결
```

### ASBR

```text
ASBR
→ Autonomous System Boundary Router
→ 다른 AS의 Router와 경로 정보 교환
```

### IR

```text
IR
→ Internal Router
→ Area에 접속한 Router
```

### BR

```text
BR
→ Backbone Router
→ Backbone에 접속한 Router
```

---

## 6. RIP와 OSPF 비교

| 구분 | RIP | OSPF |
|---|---|---|
| 방식 | Distance Vector | Link State |
| 경로 기준 | Hop Count | Cost |
| 알고리즘 | 거리 벡터 방식 | Dijkstra |
| 정보 전달 | 주기적 | 변화 발생 시 |
| 규모 | 비교적 소규모 | 대규모 |
| 특징 | 단순 | 빠른 Routing Table 갱신 |

핵심:

```text
RIP
→ Distance Vector
→ Hop Count
→ 30초
→ 16 Hop 이상 도달 불가

OSPF
→ Link State
→ Cost
→ Dijkstra
→ Area
→ 대규모 Network
```

---

# 7. ICMP(Internet Control Message Protocol)

ICMP는 TCP/IP에서 오류를 제어하고 Network 상태를 확인하기 위한 Protocol이다.

```text
ICMP
→ IP Packet 처리 중 문제 보고
→ Host / Router 상태 확인
→ 두 Host 간 Error 처리
→ 통신 정상 여부 확인
```

교재에서는 Router가 특정 목적지까지 Datagram을 보내는 데 더 좋은 경로가 있으면 근원지 Host에게 이를 알려줄 수 있다고 설명한다.

---

## 8. ICMP 주요 기능

```text
IP Packet 처리 도중 발견된 문제 보고

다른 Host로부터 특정 정보 획득

TCP/IP에서 두 Host 간 Error 처리

통신이 정상적으로 이루어지는지 확인
```

---

## 9. ICMP Message 구조

ICMP Message의 주요 항목:

```text
Type
Code
Checksum
Identifier
Sequence Number
Optional Data
```

### Type

```text
ICMP Message의 종류 표시
```

### Code

```text
Type과 같이 사용
→ 세부적인 유형 표시
```

### Checksum

```text
IP Datagram Checksum
```

---

## 10. ICMP Message 종류

### Type 3

```text
Destination Unreachable
→ Router가 목적지를 찾지 못할 경우 전송
```

### Type 4

```text
Source Quench
→ Packet을 너무 빨리 보내 Network에 무리를 주는 Host를 제한
```

### Type 5

```text
Redirection
→ Packet Routing 경로 수정
```

### Type 8 또는 10

```text
Echo Request / Reply
→ Host 존재 확인
```

### Type 11

```text
Time Exceeded
→ 시간이 초과되었거나 Packet이 폐기된 경우
```

### Type 12

```text
Parameter Problem
→ IP Header Field에 잘못된 정보가 있음을 알림
```

### Type 13 또는 14

```text
Timestamp Request / Reply
→ 시간에 대한 정보 추가
```

---

## 11. TTL(Time To Live)

ICMP에서는 TTL과 관련된 동작이 중요하다.

```text
TTL
→ Router를 통과할 때마다 1씩 감소
```

```text
TTL = 0
→ Packet 자동 폐기
→ ICMP Time Exceeded 전송
```

따라서:

```text
TTL 0
→ ICMP Type 11
```

---

## 시험 직전 암기

```text
RIP
→ Distance Vector
→ Hop Count
→ 16 Hop 이상 도달 불가
→ 30초마다 Broadcast
→ 180초 미수신 시 이상 경로
→ 대규모 망에는 부적합

Routing Table 확인
→ netstat -r
→ route PRINT

OSPF
→ Link State
→ Cost
→ Dijkstra
→ Area 사용
→ 변화된 정보만 즉시 전달
→ 대규모 Network

ABR
→ Area와 Backbone 연결

ASBR
→ 다른 AS와 경로 정보 교환

IR
→ Area 내부 Router

BR
→ Backbone Router

ICMP
→ Error 제어
→ Network 상태 확인

Type 3
→ Destination Unreachable

Type 5
→ Redirection

Type 8/10
→ Echo Request / Reply

Type 11
→ Time Exceeded

Type 12
→ Parameter Problem

TTL
→ Router 통과 시 1 감소
→ 0이면 Packet 폐기
```
