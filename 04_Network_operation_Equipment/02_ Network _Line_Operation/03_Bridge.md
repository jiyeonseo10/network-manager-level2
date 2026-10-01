# Bridge

## 1. Bridge 개요

Bridge는 두 개의 LAN을 연결하는 장치이다.

```text
Bridge
→ 두 개의 LAN 연결
→ 송수신 통신량 관리
```

Bridge는 데이터 링크 계층에서 동작하며,
송신 및 수신되는 Frame을 검사한다.

```text
Bridge
→ Data Link Layer
→ Frame 검사
```

---

## 2. Bridge 특징

Bridge는 Network 범위를 확장할 때 사용한다.

```text
Network 범위 확장
```

또한 서로 다른 물리적 Network를 연결할 수 있다.

예:

```text
Ethernet
↔ Token Ring
```

즉:

```text
서로 다른 물리적 Network 연결 가능
```

---

## 3. 많은 Computer 연결

Bridge를 사용하면 Network에 많은 Computer를 연결할 수 있다.

```text
Bridge
→ 여러 LAN 연결
→ 더 많은 Computer 연결 가능
```

---

## 4. Network 병목현상 감소

Bridge는 Network 병목현상을 감소시키는 역할을 한다.

```text
Bridge
→ Network 병목현상 감소
```

---

## 5. MAC Address 사용

Bridge는 Hardware 주소인 MAC Address를 기준으로 관리된다.

```text
Bridge
→ MAC Address 사용
```

핵심 연결:

```text
Bridge
→ Data Link Layer
→ MAC Address
```

---

## 6. Forwarding

Bridge는 입력 신호를 출력으로 전달하는 Forwarding 기능을 수행한다.

```text
Forwarding
→ 입력 신호를 출력으로 전달
```

---

## 7. Filtering

Bridge는 목적지 MAC Address를 읽고 Filtering을 수행한다.

```text
Destination MAC Address 확인
→ 전달 여부 판단
```

즉:

```text
Filtering
→ 목적지 MAC Address 기준
```

---

# 시험 직전 암기

```text
Bridge
→ 두 LAN 연결
→ Data Link Layer
→ Frame 검사
→ MAC Address 사용
```

```text
Bridge 특징
→ Network 범위 확장
→ 서로 다른 물리적 Network 연결
→ 많은 Computer 연결
→ 병목현상 감소
```

```text
Forwarding
→ 입력 신호를 출력으로 전달
```

```text
Filtering
→ 목적지 MAC Address 확인
→ 전달 여부 결정
```

## 자주 헷갈리는 부분

```text
Repeater
→ Physical Layer
→ 신호 증폭 / 재생

Bridge
→ Data Link Layer
→ Frame 검사
→ MAC Address 사용
```

```text
Forwarding
→ 전달

Filtering
→ 목적지 MAC Address 확인 후 전달 여부 판단
```
