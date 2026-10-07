# ATM(Asynchronous Transfer Mode)

## 1. ATM 개요

ATM은 가상회선을 사용하는 비동기 통신 기술이다.

```text
ATM
→ Asynchronous Transfer Mode
→ 가상회선 사용
→ 비동기 통신
```

첫 번째 Packet이 전송될 때 송신자와 수신자 사이의 최적 경로를 확정한다.

```text
첫 번째 Packet
→ 최적 경로 결정

두 번째 Packet부터
→ 결정된 경로로 Forwarding
```

인터넷처럼 Packet마다 경로를 다시 계산하지 않기 때문에 빠른 전송이 가능하다.

---

# 2. ATM 특징

교재 기준:

```text
고속으로 안정적인 통신 가능
```

```text
비동기 전송 Mode 사용
```

```text
음성
영상
Data
→ 모두 전송 가능
```

```text
가상 경로 설정
연결형 Mode 사용
```

```text
Cell 전송 시 우선순위 기능 부여
→ Network 품질 향상
```

---

# 3. ATM Cell

ATM은 IP Header 대신 고정 길이 Cell을 사용한다.

```text
ATM Cell
→ 53Byte
→ 고정 길이
```

시험 핵심:

```text
53bit X
53Byte O
```

---

# 4. ATM의 경로 결정

ATM은 첫 번째 Packet을 보낼 때 경로를 결정한다.

```text
ATM
→ 처음 한 번만 경로 결정
→ 이후 같은 경로 사용
```

반면 인터넷은:

```text
Internet
→ Packet을 전송할 때마다
→ 경로 결정
```

---

# 5. ATM과 Internet 비교

| 구분 | ATM | Internet |
|---|---|---|
| Header | 53Byte Cell | IP Header |
| 경로 결정 | 한 번만 결정 | Packet마다 결정 |
| Data | 음성, 영상, Data | 음성, 영상, Data |
| 공유 | 제한적 사용자 | 공유가 우수 |
| 교환 방식 | 가상회선 | Packet 교환 |
| QoS | 우수 | 낮음 |

---

# 6. ATM의 교환 방식

```text
ATM
→ 가상회선 방식
```

하나의 경로를 먼저 설정한 후 해당 경로를 이용하여 Data를 전송한다.

```text
경로 설정
→ 연결 확립
→ Data 전송
```

---

# 7. ATM과 Packet 교환의 차이

```text
ATM
→ 가상회선
→ 처음에 경로 결정
→ 이후 같은 경로
```

```text
Internet
→ Packet 교환
→ Packet마다 경로 결정
```

ATM은 회선 교환과 Packet 교환의 장점을 결합한 방식이다.

---

# 8. QoS

ATM은 Cell 전송 시 우선순위를 부여할 수 있다.

```text
우선순위 기능
→ Network 품질 향상
→ QoS 우수
```

---

# 시험 직전 암기

```text
ATM
→ Asynchronous Transfer Mode
→ 비동기 통신
→ 가상회선
```

```text
첫 Packet
→ 경로 결정

이후 Packet
→ 같은 경로
```

```text
ATM Cell
→ 53Byte
→ 고정 길이
```

```text
ATM
→ 음성 / 영상 / Data 전송
```

```text
ATM
→ 연결형 Mode
→ 가상 경로 사용
```

```text
ATM QoS
→ 우수
→ 우선순위 기능 제공
```

```text
ATM
→ 경로 한 번 결정

Internet
→ Packet마다 경로 결정
```

## 자주 헷갈리는 부분

```text
ATM
→ 53Byte Cell

Internet
→ IP Header
```

```text
ATM
→ 가상회선

Internet
→ Packet 교환
```

```text
ATM
→ 경로 1회 결정

Internet
→ Packet마다 경로 결정
```
