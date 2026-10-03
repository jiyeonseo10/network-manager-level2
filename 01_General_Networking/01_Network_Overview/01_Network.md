# Network 개요 / 거리 기반 Network / Data Transfer

## 1. Network 개요

Network는 송신자의 Message를 수신자에게 전달하는 과정이다.

```text
Network
→ 송신자의 Message를 수신자에게 전달
→ 정확하고 빠르게 정보 전달
```

연결 형태에 따라:

```text
유선 Network
무선 Network
```

로 구분할 수 있다.

---

# 2. 거리 기반 Network 종류

```text
PAN
LAN
MAN
WAN
```

거리 순서:

```text
PAN < LAN < MAN < WAN
```

---

## 3. PAN

PAN은 Personal Area Network이다.

```text
PAN
→ 약 5m 이내
→ 인접지역 간 통신
→ 짧은 거리
```

무선 PAN은:

```text
WPAN
→ Wireless Personal Area Network
```

Bluetooth는 교재에서 최대 약 10m 정도의 신호 전송이 가능하다고 설명한다.

```text
Bluetooth
→ WPAN
```

---

## 4. LAN

LAN은 Local Area Network이다.

```text
LAN
→ 근거리 Network
→ 약 50m
→ 제한된 지역
```

교재에서 제시한 특징:

```text
Client/Server
Peer-to-Peer
```

또한:

```text
WAN보다 빠른 통신 속도
```

를 가진다.

---

## 5. MAN

MAN은 Metropolitan Area Network이다.

```text
MAN
→ LAN과 WAN의 중간 형태
→ 약 20~30km
```

지원하는 데이터:

```text
Data
음성
영상
```

전송 매체:

```text
동축 Cable
광 Cable
```

---

## 6. DQDB

DQDB는 Distributed Queue Dual Bus이다.

```text
DQDB
→ IEEE 802.6
→ MAN Network용 Protocol
```

구조:

```text
2개의 Bus 사용
→ 이중 Bus 구조
```

Packet:

```text
53Byte 고정 길이
```

핵심:

```text
DQDB
→ MAN
→ IEEE 802.6
→ 2개의 Bus
→ 53Byte
```

---

## 7. WAN

WAN은 Wide Area Network이다.

```text
WAN
→ 광역 Network
→ 서로 관련 있는 LAN 사이 연결
```

특징:

```text
LAN보다 선로 Error율이 높음
Routing Algorithm 중요
```

---

# 8. Data Transfer 방식

교재에서는 다음 3가지로 구분한다.

```text
Simplex
Half Duplex
Full Duplex
```

---

## 9. Simplex

단방향 통신이다.

```text
Simplex
→ 한 방향으로만 Data 전송
→ 송신만 가능
→ 수신 불가
```

개념:

```text
A → B
```

---

## 10. Half Duplex

반이중 통신이다.

```text
Half Duplex
→ 송신 가능
→ 수신 가능
→ 동시에 송수신 불가능
```

개념:

```text
A → B
또는
A ← B
```

대표 예:

```text
무전기
```

---

## 11. Full Duplex

전이중 통신이다.

```text
Full Duplex
→ 송신 가능
→ 수신 가능
→ 동시에 송수신 가능
```

개념:

```text
A ↔ B
```

대표 예:

```text
전화기
```

---

# 12. Data Transfer 비교

| 방식 | 송신 | 수신 | 동시 송수신 |
|---|---|---|---|
| Simplex | 가능 | 불가 | 불가 |
| Half Duplex | 가능 | 가능 | 불가 |
| Full Duplex | 가능 | 가능 | 가능 |

---

# 시험 직전 암기

```text
PAN
→ 약 5m

LAN
→ 약 50m

MAN
→ 약 20~30km

WAN
→ 광역
```

```text
PAN < LAN < MAN < WAN
```

```text
WPAN
→ Wireless Personal Area Network
→ Bluetooth
```

```text
DQDB
→ MAN
→ IEEE 802.6
→ 2개의 Bus
→ 53Byte 고정 Packet
```

```text
Simplex
→ 단방향
```

```text
Half Duplex
→ 양방향 가능
→ 동시에 불가
→ 무전기
```

```text
Full Duplex
→ 동시에 양방향 가능
→ 전화기
```

## 자주 헷갈리는 부분

```text
PAN
→ 짧은 개인 영역

LAN
→ 근거리

MAN
→ 도시권 / LAN과 WAN 중간

WAN
→ 광역
```

```text
Simplex
→ 한 방향만

Half Duplex
→ 양쪽 가능하지만 번갈아

Full Duplex
→ 양쪽 동시에
```
