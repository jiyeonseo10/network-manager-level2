# Ethernet / UTP Cable

## 1. Ethernet 개요

Ethernet은 LAN을 위해 개발된 근거리 유선 Network 통신 기술이다.

```text
Ethernet
→ LAN용 유선 Network
→ IEEE 802.3
```

일반적으로:

```text
동축 Cable
비차폐 연선(UTP)
```

을 사용한다.

대표적인 방식:

```text
10BASE-T
100BASE-T
```

---

## 2. IEEE 802.3

```text
IEEE 802.3
→ Ethernet 국제 표준
→ CSMA/CD 방식 사용
```

시험 핵심:

```text
Ethernet
→ IEEE 802.3
→ CSMA/CD
```

---

## 3. Ethernet 장점

```text
적은 용량 Data 전송 시 성능 우수
설치 비용 저렴
관리 쉬움
Network 구조 간단
```

---

## 4. Ethernet 단점

```text
Network 사용 시 Collision 발생 가능
```

```text
Collision 발생
→ Network 지연 발생
```

```text
System 부하 증가
→ Collision 증가
→ 성능 저하
```

---

# 5. Ethernet 표준

## 10Base-5

```text
10Base-5
→ 동축 Cable
→ Thick Cable
→ 500m
```

또한:

```text
2.5m 간격으로 Transceiver 연결
```

---

## 10Base-2

```text
10Base-2
→ Thin Cable
→ 200m
```

---

## 10Base-T

```text
10Base-T
→ UTP Cable
→ 100m
```

---

# 6. Ethernet 표준 비교

```text
10Base-5
→ Thick
→ 500m

10Base-2
→ Thin
→ 200m

10Base-T
→ UTP
→ 100m
```

---

# 7. UTP Cable

UTP Cable은 유선 LAN을 연결할 때 사용한다.

교재에서는 5개의 Category로 구분한다.

---

## 8. UTP Category

```text
Category 1
→ 전화 통신
→ Data 전송에는 적합하지 않음
```

```text
Category 2
→ 최대 4Mbps
```

```text
Category 3
→ 10Base-T
→ 최대 10Mbps
```

```text
Category 4
→ Token Ring
→ 최대 16Mbps
```

```text
Category 5
→ UTP Cable
→ 최대 100Mbps
```

암기:

```text
Cat 2 → 4Mbps
Cat 3 → 10Mbps
Cat 4 → 16Mbps
Cat 5 → 100Mbps
```

---

# 9. UTP Cable 구조

교재 기준:

```text
Category 5 사용
4쌍의 꼬임선
총 8가닥
```

```text
4 Pair
→ 8 Wire
```

---

# 10. T568A / T568B

UTP Cable 배열에는 다음 두 종류가 있다.

```text
T568A
T568B
```

### Direct Cable

```text
Direct Cable
→ 양쪽 모두 같은 Type 사용
```

예:

```text
A - A
또는
B - B
```

### Cross Cable

```text
Cross Cable
→ 한쪽 T568A
→ 다른쪽 T568B
```

즉:

```text
A - B
```

---

# 11. EIA-568A 배열

```text
1 흰색+녹색
2 녹색
3 흰색+주황
4 파랑
5 흰색+파랑
6 주황
7 흰색+갈색
8 갈색
```

신호:

```text
1 → Tx+
2 → Tx-
3 → Rx+
6 → Rx-
```

---

# 12. EIA-568B 배열

```text
1 흰색+주황
2 주황
3 흰색+녹색
4 파랑
5 흰색+파랑
6 녹색
7 흰색+갈색
8 갈색
```

신호:

```text
1 → Tx+
2 → Tx-
3 → Rx+
6 → Rx-
```

---

# 13. T568A와 T568B 차이

핵심은 녹색 계열과 주황색 계열의 위치가 바뀌는 것이다.

```text
568A
1 흰녹
2 녹
3 흰주
6 주
```

```text
568B
1 흰주
2 주
3 흰녹
6 녹
```

---

# 시험 직전 암기

```text
Ethernet
→ IEEE 802.3
→ CSMA/CD
```

```text
10Base-5
→ Thick
→ 500m
```

```text
10Base-2
→ Thin
→ 200m
```

```text
10Base-T
→ UTP
→ 100m
```

```text
Cat 2 → 4Mbps
Cat 3 → 10Mbps
Cat 4 → 16Mbps
Cat 5 → 100Mbps
```

```text
UTP
→ 4쌍
→ 8가닥
```

```text
Direct
→ 양쪽 같은 Type
```

```text
Cross
→ 한쪽 A
→ 한쪽 B
```

```text
568A
1 흰녹
2 녹
3 흰주
6 주
```

```text
568B
1 흰주
2 주
3 흰녹
6 녹
```

## 자주 헷갈리는 부분

```text
802.3
→ Ethernet
→ CSMA/CD
```

```text
10Base-5
→ 500m

10Base-2
→ 200m

10Base-T
→ 100m
```

```text
Direct
→ 같은 배열

Cross
→ 서로 다른 배열
```
