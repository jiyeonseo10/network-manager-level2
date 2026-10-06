# 다중화(Multiplexing) / 집중화기(Concentrator)

## 1. 다중화(Multiplexing)

여러 단말 장치의 신호를 하나의 통신 회선을 통해 송신하고,
수신 측에서 여러 단말 장치의 신호로 분리하여 출력하는 방식이다.

```text
Multiplexing
→ 여러 신호
→ 하나의 통신 회선으로 전송
→ 수신 측에서 다시 분리
```

### 장점

```text
하나의 통신 회선 사용
→ 회선 절약
→ Modem 절약
```

### 종류

```text
주파수 분할 다중화(FDM)
시분할 다중화(TDM)
역다중화(Demultiplexing)
파장 분할 다중화(WDM)
```

---

# 2. FDM(Frequency Division Multiplexing)

주파수 분할 다중화이다.

좁은 주파수 대역을 사용하는 여러 신호를
넓은 주파수 대역을 가진 하나의 전송로를 이용해 전송한다.

```text
FDM
→ Frequency Division Multiplexing
→ 주파수 분할
```

각 통신 Channel에 제한된 주파수 대역을 독립적으로 할당한다.

```text
Channel 1 → 주파수 대역 1
Channel 2 → 주파수 대역 2
Channel 3 → 주파수 대역 3
```

### 보호대역(Guard Band)

Channel 사이의 간섭을 방지하기 위해 사용한다.

```text
Guard Band
→ Channel 사이의 간섭 방지
```

핵심:

```text
FDM
→ 주파수로 나눔
→ 여러 Channel
→ Guard Band 사용
```

---

# 3. TDM(Time Division Multiplexing)

시분할 다중화이다.

전송 회선의 Data 전송 시간을 일정한 시간 폭으로 나누어
Channel별로 Data를 전송한다.

```text
TDM
→ Time Division Multiplexing
→ 시간 분할
```

### Time Slot

```text
전송 시간을 일정한 폭으로 나눈 것
→ Time Slot
```

특징:

```text
고속 전송 가능
Point to Point 방식에 주로 사용
```

종류:

```text
동기식 시분할 다중화
비동기식 시분할 다중화
```

---

# 4. FDM vs TDM

```text
FDM
→ Frequency
→ 주파수를 나눔
```

```text
TDM
→ Time
→ 시간을 나눔
→ Time Slot 사용
```

한 줄 암기:

```text
FDM = 주파수 분할
TDM = 시간 분할
```

---

# 5. 역다중화(Demultiplexing)

교재에서는 하나의 신호를 2개의 저속 신호로 나누어 전송하는 방식으로 설명한다.

```text
Demultiplexing
→ 하나의 신호
→ 2개의 저속 신호로 분리
```

장점:

```text
한 Channel에 고장 발생
→ 나머지 Channel 사용 가능
→ 50% 속도로 계속 사용
```

또한:

```text
2개의 음성 회선 사용
→ 광대역 통신 속도 확보 가능
```

---

# 6. WDM(Wavelength Division Multiplexing)

파장 분할 다중화이다.

```text
WDM
→ Wavelength Division Multiplexing
→ 파장 분할
```

교재 기준:

```text
광섬유 사용
→ 하나의 선로에서
→ 8개 이하의 신호를 중첩하여 전송
```

핵심:

```text
WDM
→ 광섬유
→ 파장을 이용하여 다중화
```

---

# 7. 다중화 종류 비교

| 구분 | 핵심 |
|---|---|
| FDM | 주파수 분할 |
| TDM | 시간 분할 |
| Demultiplexing | 하나의 신호를 2개의 저속 신호로 분리 |
| WDM | 광섬유에서 파장 분할 |

```text
FDM → Frequency
TDM → Time
WDM → Wavelength
```

---

# 8. 집중화기(Concentrator)

여러 개의 입력 회선을 n개의 출력 회선으로 집중하는 장치이다.

```text
Concentrator
→ 여러 입력 회선
→ 적은 수의 출력 회선으로 집중
```

교재 기준:

```text
입력 회선 수 ≥ 출력 회선 수
```

사용 목적:

```text
하나의 고속 통신 회선
← 여러 개의 저속 통신 회선 접속
```

---

# 9. 집중화기 특징

```text
고속 회선 사용 가능
```

```text
동적인 시간 할당
```

```text
입력과 출력 각각의 대역폭이 다름
```

```text
구조가 복잡함
```

```text
불규칙한 전송에 사용
```

---

# 시험 직전 암기

```text
Multiplexing
→ 여러 신호를 하나의 회선으로 전송
→ 수신 측에서 분리
→ 회선 / Modem 절약
```

```text
FDM
→ 주파수 분할
→ Guard Band
```

```text
TDM
→ 시간 분할
→ Time Slot
→ Point to Point
```

```text
Demultiplexing
→ 하나의 신호를
→ 2개의 저속 신호로 분리
```

```text
WDM
→ 파장 분할
→ 광섬유
```

```text
Concentrator
→ 입력 회선 수 ≥ 출력 회선 수
→ 여러 저속 회선을 고속 회선에 집중
→ 동적인 시간 할당
```

## 자주 헷갈리는 부분

```text
FDM
→ Frequency
→ 주파수

TDM
→ Time
→ 시간

WDM
→ Wavelength
→ 파장
```

```text
Multiplexing
→ 여러 신호를 하나의 회선에 모음

Concentrator
→ 여러 입력 회선을 적은 출력 회선에 집중
```
