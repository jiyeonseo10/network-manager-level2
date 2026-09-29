# 인터넷 계층(Internet Layer)

## 1. 인터넷 계층 개요

인터넷 계층은 송신자의 IP 주소와 수신자의 IP 주소를 이용하여 목적지까지의 경로를 결정하고 Packet을 전달하는 계층이다.

```text
Internet Layer
→ IP 주소 사용
→ Routing
→ Packet 전달
→ Logical Addressing
```

관련 프로토콜:

```text
IP
ICMP
IGMP
RIP
OSPF
BGP
```

- IGMP → Multicast
- RIP / OSPF / BGP → Routing

---

## 2. 인터넷 계층의 기능

```text
Routing
→ 경로 설정

Point-to-Point
→ Packet 전달

Logical Addressing
→ 논리 주소 지정

Address Transformation
→ 주소 변환
```

---

## 3. Datagram

전송 계층의 데이터에 IP Header를 붙이면 Datagram이라고 한다.

```text
Message
+ TCP 또는 UDP Header
→ Segment

Segment
+ IP Header
→ Datagram
```

---

## 4. IP(Internet Protocol)

IP 프로토콜은 송신자와 수신자의 IP 주소를 가지고 목적지까지의 경로를 결정한다.

```text
IPv4
→ 32bit

IPv6
→ 128bit
```

---

## 5. IP Header

### Version

```text
Version
→ IPv4 / IPv6 구분
```

### Header Length

```text
Header Length
→ Header 전체 길이
```

### Type of Service

```text
Type of Service
→ 서비스 유형
```

### Total Length

```text
Total Length
→ IP Datagram 전체 Byte 수
```

### Identification

```text
Identification
→ Datagram 식별
```

### Flags & Fragment Offset

```text
Flags & Fragment Offset
→ 단편화 정보
```

### TTL

TTL은 **Time To Live**이다.

```text
TTL
→ Router 통과 가능 횟수
→ Router 하나 통과할 때마다 1 감소
→ 0이 되면 Packet 폐기
```

목적:

```text
Packet이 Network를 무한히 돌아다니는 것을 방지
```

### Protocol

```text
Protocol
→ 상위 Protocol 종류 표시
→ TCP / UDP / ICMP
```

### Header Checksum

```text
Header Checksum
→ IP Header 무결성 검사
```

---

## 6. IP 단편화(Fragmentation)

MTU보다 큰 Packet은 여러 조각으로 분할된다.

```text
MTU
→ Maximum Transmission Unit
→ 한 번에 통과할 수 있는 Packet 최대 크기
```

```text
Packet > MTU
→ Fragmentation
→ 여러 Datagram으로 분할
```

수신 측:

```text
Fragment
→ Reassembly
→ 원래 Packet 복원
```

단편화 관련 정보:

```text
Flags
Fragment Offset
```

Ethernet 예:

```text
MTU = 1500
```

---

## 7. IPv4 주소 구조

IPv4는 32bit이다.

```text
IP Address
= Network ID + Host ID
```

- Network ID → Network 식별
- Host ID → 해당 Network 내부의 Host 식별

---

## 8. IP Class

```text
Class A
→ 시작 bit 0

Class B
→ 시작 bit 10

Class C
→ 시작 bit 110

Class D
→ 1110
→ Multicast

Class E
→ 1111
→ Reserved
```

---

## 9. Subnet Mask

Subnetting은 하나의 Network를 여러 개의 논리적인 Subnet으로 나누는 것이다.

```text
Subnetting
→ 하나의 Network
→ 여러 Subnet으로 분할
```

Class C 기본 Subnet Mask:

```text
255.255.255.0
```

2bit 사용:

```text
11000000
→ 192

255.255.255.192
```

3bit 사용:

```text
11100000
→ 224

255.255.255.224
```

예:

```text
필요 Subnet = 6개

2² = 4
→ 부족

2³ = 8
→ 가능

Subnet Mask
→ 255.255.255.224
```

---

## 10. CIDR

CIDR은 **Classless Inter-Domain Routing**이다.

```text
/n
→ 앞의 n bit가 Network 부분
```

예:

```text
200.10.10.100/24
→ 255.255.255.0
```

---

## 11. Routing

Routing은 데이터를 출발지에서 목적지까지 전달하기 위한 경로를 결정하는 것이다.

```text
Routing
→ 경로 결정

Forwarding
→ 결정된 경로로 Packet 전달
```

라우터는 Routing Table을 이용한다.

---

## 12. Static Routing

```text
Static Routing
→ 관리자가 직접 경로 설정
→ 경로 고정
→ 수동 갱신
```

특징:

- 실시간 자동 변경 X
- Network 변화가 적을 때 적합
- Router의 처리 부담 감소

---

## 13. Dynamic Routing

```text
Dynamic Routing
→ 자동 경로 설정
→ Network 변화에 대응
→ Routing Algorithm 사용
```

Router 간 Routing 정보를 자동으로 교환한다.

---

## 14. IGP와 EGP

### IGP

```text
IGP
→ Internal Gateway Routing Protocol
→ 동일 그룹 내부
→ 기업 또는 ISP 내부
```

### EGP

```text
EGP
→ Exterior Gateway Routing Protocol
→ 서로 다른 그룹 간
```

---

## 15. Distance Vector

Distance Vector는 거리 정보를 이용하여 경로를 결정한다.

```text
Distance Vector
→ 거리 기준
→ Hop Count / TTL
```

알고리즘:

```text
Bellman-Ford
```

대표 프로토콜:

```text
RIP
IGRP
EIGRP
BGP
```

동작:

```text
Routing 정보
→ 인접 Router에 주기적으로 전달
→ Routing Table 갱신
```

단점:

```text
Routing Loop 가능
Network Traffic 증가 가능
```

---

## 16. Link State

Link State는 Network 상태를 종합하여 Cost를 계산하고 최적 경로를 결정한다.

```text
Link State
→ Link Cost
→ 대역폭 / 지연 등 고려
```

알고리즘:

```text
Dijkstra
```

대표 프로토콜:

```text
OSPF
IS-IS
```

동작:

```text
Link 상태 변화 발생
→ 인접 Router에 정보 전달
→ 최적 경로 재계산
```

---

## 17. Distance Vector vs Link State

| 구분 | Distance Vector | Link State |
|---|---|---|
| 알고리즘 | Bellman-Ford | Dijkstra |
| 기준 | 거리 / Hop Count | Link Cost |
| 정보 전달 | 주기적 | 변화 발생 시 |
| 대표 프로토콜 | RIP, IGRP, EIGRP, BGP | OSPF, IS-IS |
| 단점 | Routing Loop 가능 | CPU / Memory 사용 증가 |

---

## 18. BGP

BGP는 **Border Gateway Protocol**이다.

```text
BGP
→ 서로 다른 AS 사이의 Routing
```

```text
AS
→ Autonomous System
→ 자율 시스템
```

---

## 시험 직전 암기

```text
Internet Layer
→ Routing
→ IP 주소 사용
→ Datagram 전달

Datagram
→ Segment + IP Header

IPv4
→ 32bit

IPv6
→ 128bit

TTL
→ Router 통과 시 1 감소
→ 0이면 폐기

MTU
→ Maximum Transmission Unit

Packet > MTU
→ Fragmentation

Fragment
→ Reassembly

Class D
→ Multicast

Class E
→ Reserved

/24
→ 255.255.255.0

Static Routing
→ 수동

Dynamic Routing
→ 자동

IGP
→ 내부

EGP
→ 외부

Distance Vector
→ Bellman-Ford
→ Hop Count
→ RIP / IGRP / EIGRP / BGP

Link State
→ Dijkstra
→ Cost
→ OSPF / IS-IS

BGP
→ AS ↔ AS
```
