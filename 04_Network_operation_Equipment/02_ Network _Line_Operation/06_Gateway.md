# Gateway

## 1. Gateway 개요

Gateway는 서로 다른 Network 간의 상호 연결을 위해 사용하는 Network 장비이다.

```text
Gateway
→ 서로 다른 Network 연결
```

또한 서로 다른 Protocol 간 변환을 수행하여
Protocol이 달라도 통신할 수 있도록 한다.

```text
서로 다른 Protocol
→ Gateway가 변환
→ 통신 가능
```

---

## 2. Message 변환

Gateway는 서로 다른 Network에서 사용하는 Message Format을 변환할 수 있다.

교재 예:

```text
ASCII Code
→ EBCDIC Code
```

핵심:

```text
Gateway
→ Message Format 변환
```

---

## 3. Protocol 변환

Gateway는 서로 다른 종류의 Protocol을 상호 변환할 수 있다.

교재 예:

```text
TCP/IP
↔ ATM
```

핵심:

```text
Gateway
→ Protocol 변환
```

---

## 4. Address 변환

Gateway는 서로 다른 Address 체계를 변환할 수 있다.

교재 예:

```text
IPv4
↔ IPv6
```

핵심:

```text
Gateway
→ Address 변환
```

---

## 5. Firewall

Gateway는 서로 다른 Network를 연결하면서
Packet Filtering과 같은 Firewall 역할을 수행할 수 있다.

```text
Gateway
→ Firewall
→ Packet Filtering
```

---

## 6. Proxy Server

Proxy Server는 중계기 역할을 수행한다.

```text
Proxy Server
→ 중계 역할
→ Proxy Server를 통해 다른 Network에 접근
```

---

# Gateway 주요 기능

```text
1. Message 변환
   ASCII ↔ EBCDIC

2. Protocol 변환
   TCP/IP ↔ ATM

3. Address 변환
   IPv4 ↔ IPv6

4. Firewall
   Packet Filtering

5. Proxy Server
   중계 역할
```

---

# Router와 Gateway 비교

```text
Router
→ IP Address를 읽고 경로 결정
```

```text
Gateway
→ 서로 다른 Network 연결
→ Message / Protocol / Address 변환
```

---

# 시험 직전 암기

```text
Gateway
→ 서로 다른 Network 연결
→ 서로 다른 Protocol 간 변환
```

```text
Message 변환
→ ASCII ↔ EBCDIC
```

```text
Protocol 변환
→ TCP/IP ↔ ATM
```

```text
Address 변환
→ IPv4 ↔ IPv6
```

```text
Firewall
→ Packet Filtering
```

```text
Proxy Server
→ 중계 역할
```

## 자주 헷갈리는 부분

```text
Router
→ 경로 결정

Gateway
→ 서로 다른 환경 사이 변환
```

```text
Message
→ ASCII ↔ EBCDIC

Protocol
→ TCP/IP ↔ ATM

Address
→ IPv4 ↔ IPv6
```
