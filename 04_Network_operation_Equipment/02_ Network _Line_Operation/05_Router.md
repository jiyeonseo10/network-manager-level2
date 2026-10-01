# Router / route 명령어

## 1. Router 개요

Router는 Internetworking 장비로,
네트워크에서 IP 주소를 읽어 경로를 결정하는 장비이다.

```text
Router
→ Internetworking 장비
→ IP Address 확인
→ 경로 결정
```

또한 LAN과 LAN을 연결하고 TCP/IP Protocol을 지원한다.

```text
LAN ↔ LAN 연결
→ TCP/IP Protocol 지원
```

---

## 2. Router 동작 계층

Router는 OSI 7계층 중 Network Layer에서 동작한다.

```text
Router
→ Network Layer
→ IP Address 기반
```

---

## 3. Routing Table 유지

Router는 주기적인 Routing Broadcast를 이용하여
최신 Routing Table을 유지한다.

```text
Routing Broadcast
→ Routing Table 최신 상태 유지
```

---

## 4. 경로 결정

Router는 Packet의 IP Address를 읽어 경로를 결정한다.

```text
Packet의 IP Address 확인
→ Routing 경로 결정
```

---

## 5. Filtering

Router는 특정 IP에서 유입되거나
특정 IP로 전송되는 Packet을 Filtering할 수 있다.

```text
Filtering
→ 특정 IP의 Packet 제어
```

---

## 6. Forwarding

Router는 입력 Interface로 들어온 Packet을
출력 Interface로 전달하는 Forwarding을 수행한다.

```text
Forwarding
→ Input Interface
→ Output Interface
```

또한 Broadcast를 차단할 수 있다.

```text
Router
→ Broadcast 차단 가능
```

---

# 7. route 명령어

Windows에서는 `route` 명령어를 사용하여
Routing Table을 관리할 수 있다.

```text
route
→ Routing Table 관리
```

가능한 작업:

```text
추가
변경
삭제
출력
```

Routing 정보는 IPv4와 IPv6로 나뉘어 관리된다.

---

## 8. IPv4 Routing Table 확인

```bash
route PRINT -4
```

```text
-4
→ IPv4 Routing Table
```

---

## 9. IPv6 Routing Table 확인

```bash
route PRINT -6
```

```text
-6
→ IPv6 Routing Table
```

---

## 10. Routing 정보 추가

```bash
route ADD
```

Routing 정보를 추가할 때 교재에서 제시한 정보:

```text
IP Address
Subnet Mask
Gateway Address
Metric
```

핵심:

```text
route ADD
→ Routing 정보 추가
```

---

## 11. Routing 정보 삭제

```bash
route DELETE
```

```text
route DELETE
→ 등록된 Routing 정보 삭제
```

---

## 12. Routing 정보 변경

```bash
route CHANGE
```

```text
route CHANGE
→ Routing 정보 변경
```

---

# 시험 직전 암기

```text
Router
→ Network Layer
→ IP Address
→ 경로 결정
```

```text
Router 기능
→ Routing Table 유지
→ Filtering
→ Forwarding
→ Broadcast 차단
```

```text
route PRINT -4
→ IPv4 Routing Table
```

```text
route PRINT -6
→ IPv6 Routing Table
```

```text
route ADD
→ 추가

route DELETE
→ 삭제

route CHANGE
→ 변경
```

## 자주 헷갈리는 부분

```text
Bridge
→ Data Link Layer
→ MAC Address

Router
→ Network Layer
→ IP Address
```

```text
Filtering
→ 특정 IP Packet 제어

Forwarding
→ 입력 Interface의 Packet을 출력 Interface로 전달
```
