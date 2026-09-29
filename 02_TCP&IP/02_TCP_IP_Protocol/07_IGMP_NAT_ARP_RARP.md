# 데이터 전송 방식 / IGMP / NAT / ARP / RARP

## 1. 데이터 전송 방식

### Unicast

```text
Unicast
→ 1 : 1 전송
→ 한 송신자에서 한 수신자로 전송
```

---

### Broadcast

```text
Broadcast
→ 1 : N 전송
→ 동일한 Subnet의 모든 수신자에게 전송
```

---

### Multicast

```text
Multicast
→ M : N 전송
→ 하나 이상의 송신자가 특정 그룹의 수신자에게 전송
```

---

### Anycast

IPv6에서 새롭게 등장한 방식이다.

```text
Anycast
→ 같은 그룹에 등록된 Node 중
→ 최단 경로의 Node 하나에게만 전송
```

교재에서는 IPv6에는 Broadcast가 없어졌다고 설명한다.

```text
IPv6
→ Broadcast 없음
```

---

# 2. IGMP

IGMP는 Multicast 그룹에 등록된 사용자를 관리하는 Protocol이다.

```text
IGMP
→ Multicast 그룹 관리
```

### IGMP 특징

```text
Multicast에 참여하는 수신자 정보 제공

1 : N 방식으로
→ Multicast 그룹에 Message 전송

Host와 Router 사이에서 TTL 제공

시작 Host가 수신 받을 목적지 Host에게 Message 전송
```

---

## 3. IGMP Message 구조

IGMP Message는 8Byte로 구성된다.

주요 필드:

```text
Version
Type
Checksum
Group ID
```

### Version

```text
IGMP Protocol의 Version 표시
→ 교재에서는 Version 2
```

### Type

```text
Type 1
→ 보고

Type 2
→ 질의
```

### Group ID

```text
보고 Message의 경우
→ Host가 신규 가입하려는 Multicast Service의 Group ID
```

---

# 4. NAT

NAT는 **Network Address Translation**이다.

```text
NAT
→ 사설 IP
→ Routing 가능한 공인 IP로 변환
```

---

## 5. NAT 장점

```text
공인 IP 부족 문제 해결

내부에서는 사설 IP
외부에서는 공인 IP 사용

내부망을 사설망으로 구성
→ 보안성 향상

ISP 변경 시
→ 내부 IP 변경 최소화
```

---

# 6. NAT 종류

## Normal NAT

```text
Normal NAT
→ N개의 사설 IP
→ 한 개의 공인 IP로 변환
```

---

## Reverse NAT(Static)

```text
Reverse NAT
→ 외부에서 내부 Network로 접근할 때 사용

→ 1 : 1 Mapping
→ Static Mapping
```

---

## Redirect NAT

```text
Redirect NAT
→ 목적지 주소를 재지정할 때 사용
```

---

## Exclude NAT

```text
Exclude NAT
→ 특정 목적지에 접속할 경우
→ 설정된 NAT를 적용하지 않도록 함
```

---

# 7. Dynamic NAT

Dynamic NAT는 내부의 사설 IP를 미리 정해진 공인 IP 중 하나에 동적으로 매핑한다.

```text
Private IP
→ Public IP Pool 중 하나와 Mapping
```

특징:

```text
사용 가능한 Public IP가 있으면
→ Private IP를 동적으로 연결

Public IP를 모두 사용 중이면
→ 남은 Private IP는 Public IP 사용 불가
```

---

# 8. Static NAT

Static NAT는 관리자가 특정 사설 IP와 특정 공인 IP를 미리 지정하는 방식이다.

```text
Private IP
↔ Public IP

1 : 1 고정 Mapping
```

---

# 9. PAT

PAT는 Port 번호를 이용하여 하나의 공인 IP를 여러 사설 IP가 함께 사용하는 방식이다.

```text
PAT
→ Public IP 1개
+ 서로 다른 Port 번호
→ 여러 Private IP가 외부 통신 가능
```

예:

```text
192.168.10.1 : 1111
192.168.10.2 : 2222
192.168.10.3 : 3333
192.168.10.4 : 4444

→ 200.100.10.2 하나 사용
```

핵심:

```text
NAT
→ IP 주소 변환

PAT
→ IP 주소 + Port 번호 사용
```

---

# 10. ARP

ARP는 IP 주소를 물리적인 Hardware 주소인 MAC 주소로 변환하는 Protocol이다.

```text
ARP
→ IP → MAC
```

즉:

```text
Logical Address
→ Physical Address
```

---

## 11. ARP 동작

```text
ARP Request
→ 해당 IP 주소를 가진 Host를 찾음

ARP Reply
→ 해당 Host가 자신의 MAC 주소로 응답
```

### ARP Request

```text
Broadcast
```

### ARP Reply

해당 Host가 응답한다.

---

# 12. ARP Cache Table

ARP Request와 ARP Reply를 통해 확인한 IP와 MAC 주소의 관계는 ARP Cache Table에 저장한다.

```text
ARP Cache Table
→ IP 주소와 MAC 주소의 Mapping Table
```

---

# 13. ARP Operation Code

```text
1 → ARP Request
2 → ARP Reply
3 → RARP Request
4 → RARP Reply
5 → DRARP Request
6 → DRARP Reply
7 → DRARP Error
8 → InARP Request
9 → InARP Reply
```

시험 핵심:

```text
1
→ ARP Request

2
→ ARP Reply
```

---

# 14. ARP 명령어

Linux:

```bash
arp
```

Windows:

```bash
arp -a
```

용도:

```text
IP 주소와 MAC 주소 Mapping 확인
```

---

# 15. RARP

RARP는 물리적 주소인 MAC 주소를 기반으로 논리적 주소인 IP 주소를 알아오는 Protocol이다.

```text
RARP
→ MAC → IP
```

교재에서는 Diskless Host에서 사용하는 방식으로 설명한다.

```text
Diskless Host
→ 자신의 MAC 주소를 Server에 전달
→ IP 주소를 받아 사용
```

---

## 16. RARP 동작

```text
RARP Request
→ Broadcast

RARP Response
→ Unicast
```

RARP Server는:

```text
MAC 주소
→ IP 주소로 Mapping
```

한다.

---

# 시험 직전 암기

```text
Unicast
→ 1 : 1

Broadcast
→ 1 : N
→ 동일 Subnet 전체

Multicast
→ 특정 Group

Anycast
→ Group 중 최단 경로 Node 하나
→ IPv6에서 사용

IPv6
→ Broadcast 없음
```

```text
IGMP
→ Multicast 그룹 관리

IGMP Message
→ 8Byte

Type 1
→ 보고

Type 2
→ 질의
```

```text
NAT
→ Private IP → Public IP

Static NAT
→ 1 : 1 고정 Mapping

Dynamic NAT
→ Public IP Pool에서 동적 Mapping

PAT
→ Public IP 1개
+ Port 번호
→ 여러 Private IP 사용
```

```text
ARP
→ IP → MAC

ARP Request
→ Broadcast

ARP Reply
→ 해당 Host 응답

ARP Opcode 1
→ Request

ARP Opcode 2
→ Reply
```

```text
RARP
→ MAC → IP

RARP Request
→ Broadcast

RARP Response
→ Unicast
```

## 자주 헷갈리는 것

```text
ARP
→ IP → MAC

RARP
→ MAC → IP
```

```text
Broadcast
→ 동일 Subnet 전체

Multicast
→ 특정 Group만
```

```text
Static NAT
→ 고정 1:1

Dynamic NAT
→ 공인 IP Pool 사용

PAT
→ Port 번호까지 이용
```
