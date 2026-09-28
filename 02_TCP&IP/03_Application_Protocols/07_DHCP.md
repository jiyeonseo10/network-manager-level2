# DHCP

네트워크관리사 2급 TCP/IP 파트의 **DHCP(Dynamic Host Configuration Protocol)** 내용을 정리한다.

---

## 1. DHCP 개요

DHCP는 **Dynamic Host Configuration Protocol**의 약자이다.

네트워크에 처음 연결될 때 다음 정보를 동적으로 설정한다.

- IP 주소
- 서브넷 마스크
- 게이트웨이 주소

```text
DHCP
→ Dynamic Host Configuration Protocol
→ IP 주소 동적 할당
→ IP / Subnet Mask / Gateway 자동 설정
```

---

## 2. DHCP 기능

DHCP 서버는 자신이 관리하는 주소 목록에서 접속한 컴퓨터 시스템에 IP 주소를 할당한다.

책 기준 특징:

- 기업 내 IP 주소를 중앙에서 관리
- DHCP로 할당한 IP 주소를 일정 시간 동안만 사용하도록 함
- 관리하는 IP 주소보다 많은 컴퓨터가 접속할 경우 임대 DHCP를 사용하여 일정 시간 동안 IP 주소를 사용하게 함

```text
DHCP Server
→ IP 주소 중앙 관리
→ Client에 IP 할당
→ 일정 시간 동안 임대
```

---

## 3. Lease

DHCP에서 할당받은 IP 주소는 일정 시간 동안 사용할 수 있다.

```text
Lease
→ 일정 시간 동안 IP 사용
```

즉,

```text
DHCP
→ IP 주소를 빌려줌
→ 임대 기간 존재
```

---

## 4. DHCP 동작 순서

DHCP 동작 순서는 다음과 같다.

```text
Discover
→ Offer
→ Request
→ Ack
```

앞글자를 이용하면:

```text
DORA
```

---

## 5. DHCP Discover

클라이언트가 DHCP 서버를 찾는 단계이다.

```text
DHCP Discover
→ Client가 보냄
→ Broadcast
→ DHCP Server 검색
```

---

## 6. DHCP Offer

DHCP 서버가 클라이언트에게 할당 가능한 IP 주소를 제안하는 단계이다.

책에서는 자신의 IP를 알려주고 PC에 임의의 IP 주소를 할당해 줄 수 있다는 메시지를 전달한다고 설명한다.

```text
DHCP Offer
→ Server가 보냄
→ 할당 가능한 IP 제안
→ Broadcast
```

---

## 7. DHCP Request

클라이언트가 IP 주소를 임대하기 위해 DHCP 서버에 요청하는 단계이다.

```text
DHCP Request
→ Client가 보냄
→ IP 주소 임대 요청
→ Broadcast
```

---

## 8. DHCP Ack

DHCP 서버가 클라이언트에게 최종적으로 임대 정보를 전달하는 단계이다.

책 기준:

- 임대용 IP 주소 전달
- 임대 기간 전달
- Broadcast 또는 Unicast 방식 사용 가능

```text
DHCP Ack
→ Server가 보냄
→ IP 주소 확정
→ 임대 기간 전달
```

Flag 값:

```text
Flag = 1
→ Broadcast

Flag = 0
→ Unicast
```

---

## 9. DHCP 전체 흐름

```text
Client
→ DHCP Discover
→ DHCP Server 검색

Server
→ DHCP Offer
→ IP 주소 제안

Client
→ DHCP Request
→ IP 주소 임대 요청

Server
→ DHCP Ack
→ IP 주소와 임대 기간 전달
```

---

## 10. 시험 직전 암기

```text
DHCP
→ Dynamic Host Configuration Protocol
→ IP 주소 동적 할당
→ IP / Subnet Mask / Gateway 자동 설정

DHCP Server
→ IP 주소 중앙 관리

Lease
→ 일정 시간 동안 IP 사용

DORA

D
→ Discover
→ Client
→ Broadcast

O
→ Offer
→ Server
→ IP 제안
→ Broadcast

R
→ Request
→ Client
→ IP 임대 요청
→ Broadcast

A
→ Ack
→ Server
→ IP 주소 + 임대 기간 전달

Flag = 1
→ Broadcast

Flag = 0
→ Unicast
```
