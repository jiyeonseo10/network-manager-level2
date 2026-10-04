# Fast Ethernet / Gigabit Ethernet

## 1. Fast Ethernet 개요

Fast Ethernet은 기존 Ethernet보다 전송 속도가 향상된 방식이다.

```text
Fast Ethernet
→ IEEE 802.3
→ 100Mbps
```

다른 이름:

```text
100Base-T
```

여기서 100은 전송 속도인 100Mbps를 의미한다.

---

## 2. Fast Ethernet 특징

```text
Star Topology 사용
```

```text
CSMA/CD 사용
```

```text
기존 Ethernet
10Mbps

Fast Ethernet
100Mbps
```

즉:

```text
기존 Ethernet보다 10배 빠름
```

Cable 길이는 교재 기준:

```text
최대 100m
```

---

## 3. 기존 Ethernet과의 호환성

Fast Ethernet은 기존 Ethernet과 호환성을 유지한다.

```text
IEEE 802.3 사용
Frame 형식 동일
Media Access 방식 동일
CSMA/CD 사용
```

또한:

```text
48bit Address 체계 유지
최소 Frame 길이 유지
최대 Frame 길이 유지
```

---

## 4. Frame

Frame은 Data를 전송하는 단위이다.

Frame에는 다음과 같은 정보가 포함된다.

```text
동기화 신호
시작 Bit
Hardware Address
Frame 검사 Bit
```

---

# 5. Ethernet vs Fast Ethernet

| 구분 | Ethernet | Fast Ethernet |
|---|---|---|
| 표준 | IEEE 802.3 | IEEE 802.3 |
| 속도 | 10Mbps | 100Mbps |
| Topology | 성형, 버스형 | 성형 |
| MAC Protocol | CSMA/CD | CSMA/CD |
| Cable | UTP, Fiber | STP, UTP, Fiber |
| 전이중 Cable | 지원 | 지원 |
| 다른 이름 | 10Base-T | 100Base-T |

핵심:

```text
Ethernet
→ 10Mbps

Fast Ethernet
→ 100Mbps
```

---

# 6. Gigabit Ethernet 개요

Gigabit Ethernet은 1초에 1Gbps의 속도로 Data를 전송할 수 있는 Ethernet 표준 기술이다.

```text
Gigabit Ethernet
→ 1Gbps
```

다른 이름:

```text
1000Base-X
```

---

## 7. Gigabit Ethernet 특징

```text
Star Topology 사용
```

```text
CSMA/CD 사용
```

```text
기존 Ethernet과 호환
```

Fast Ethernet보다:

```text
10배 빠름
```

즉:

```text
Fast Ethernet
→ 100Mbps

Gigabit Ethernet
→ 1Gbps
```

---

# 8. Ethernet 속도 비교

```text
Ethernet
→ 10Mbps
```

```text
Fast Ethernet
→ 100Mbps
```

```text
Gigabit Ethernet
→ 1Gbps
```

속도 관계:

```text
10Mbps
→ 100Mbps
→ 1000Mbps
```

---

# 9. 채널 용량 단위

```text
bps
→ bit per second
→ 초당 전송 가능한 bit
```

```text
Kbps
→ 1000bit 단위
```

```text
Mbps
→ 100만 bit 단위
```

```text
Gbps
→ 10억 bit 단위
```

암기:

```text
1 Kbps = 1,000 bps
1 Mbps = 1,000,000 bps
1 Gbps = 1,000,000,000 bps
```

---

# 시험 직전 암기

```text
Ethernet
→ 10Mbps
→ 10Base-T
```

```text
Fast Ethernet
→ 100Mbps
→ 100Base-T
→ IEEE 802.3
→ CSMA/CD
→ Star
→ 최대 100m
```

```text
Gigabit Ethernet
→ 1Gbps
→ 1000Base-X
→ Star
→ CSMA/CD
```

```text
Ethernet
10Mbps

Fast Ethernet
100Mbps

Gigabit Ethernet
1Gbps
```

```text
Fast Ethernet
→ 기존 Ethernet보다 10배 빠름

Gigabit Ethernet
→ Fast Ethernet보다 10배 빠름
```

## 자주 헷갈리는 부분

```text
10Base-T
→ Ethernet
→ 10Mbps
```

```text
100Base-T
→ Fast Ethernet
→ 100Mbps
```

```text
1000Base-X
→ Gigabit Ethernet
→ 1Gbps
```

```text
Fast Ethernet / Gigabit Ethernet
→ 둘 다 Star
→ 둘 다 CSMA/CD
```
