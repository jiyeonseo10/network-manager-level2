# 변조 / Baseband / Broadband / PCM

## 1. 변조(Modulation)

변조는 아날로그 또는 디지털로 부호화된 신호를 전송 매체에 전달할 수 있도록 변환하는 과정이다.

```text
Modulation
→ 전송 매체에 맞는 신호로 변환
```

부호화(Encoding)는 현재의 정보나 신호를 다른 형태로 변환하는 것을 의미한다.

---

# 2. 아날로그 변조

아날로그 신호를 아날로그 신호로 변조하는 방식이다.

대표 방식:

```text
AM
FM
PM
```

---

## 3. AM

```text
AM
→ Amplitude Modulation
→ 진폭 변조
```

반송파의 진폭을 정보 신호의 진폭 변화에 따라 변화시킨다.

특징:

```text
구현이 비교적 간단
잡음에 취약
전송 효율 낮음
```

---

## 4. FM

```text
FM
→ Frequency Modulation
→ 주파수 변조
```

반송파의 주파수를 정보 신호의 변화에 따라 변화시킨다.

특징:

```text
주파수 대역 넓음
잡음에 강함
```

용도:

```text
FM 방송
저속 Data 전송용 Modem
```

---

## 5. PM

```text
PM
→ Phase Modulation
→ 위상 변조
```

반송파의 위상을 정보 신호의 변화에 따라 변화시킨다.

용도:

```text
Digital 전송용 Modem
Digital 무선 전송
```

---

# 6. 디지털 변조

Digital Signal을 Analog Signal로 변조하는 대표 방식:

```text
ASK
FSK
PSK
QAM
```

---

## 7. ASK

```text
ASK
→ Amplitude Shift Keying
→ 진폭 편이 변조
```

```text
0과 1
→ 서로 다른 진폭 사용
```

장점:

```text
회로 간단
가격 저렴
```

단점:

```text
잡음이나 신호 변동에 약함
비효율적
```

---

## 8. FSK

```text
FSK
→ Frequency Shift Keying
→ 주파수 편이 변조
```

```text
0과 1
→ 서로 다른 주파수 사용
```

특징:

```text
저속 비동기 전송에 많이 사용
ASK보다 Error에 강함
회로가 비교적 간단
```

---

## 9. PSK

```text
PSK
→ Phase Shift Keying
→ 위상 편이 변조
```

```text
0과 1
→ 서로 다른 위상 사용
```

특징:

```text
중속·고속 동기 전송에 많이 사용
주로 Modem에서 사용
```

---

## 10. QAM

```text
QAM
→ Quadrature Amplitude Modulation
→ 직교 진폭 변조
```

위상이 90도 다른 두 반송파를 사용하고 각각 진폭 변조한다.

```text
QAM
→ AM + PM 조합
```

특징:

```text
고속 Digital Signal 전송
좁은 주파수 대역 사용에 적합
```

용도:

```text
고속 Modem
고속 Digital 무선 전송
```

---

# 11. Baseband

Digital Signal을 변조하지 않고 그대로 전송하는 방식이다.

```text
Baseband
→ Digital
→ 변조 없음
→ 근거리
→ 단일 Channel
```

장점:

```text
운영 비용 저렴
전이중 전송 가능
Network 구성 간단
관리 용이
```

단점:

```text
장거리 전송에 부적합
장거리에서는 Repeater 필요
잡음에 쉽게 변형
```

---

# 12. Broadband

Digital Signal을 여러 신호로 변조하여 서로 다른 주파수 대역으로 동시에 전송하는 방식이다.

```text
Broadband
→ Analog
→ 변조 필요
→ 장거리
→ 다중 Channel
```

장점:

```text
장거리 전송에 효율적
다중 Channel 사용
음성·영상·Data 전송 가능
```

단점:

```text
회로 복잡
주파수 관리 어려움
Baseband보다 속도 느림
단방향 전송
```

---

# 13. Baseband vs Broadband

| 구분 | Baseband | Broadband |
|---|---|---|
| 종류 | Digital | Analog |
| 거리 | 근거리 | 장거리 |
| Channel | 단일 | 다중 |
| 방식 | 양방향 | 단방향 |
| 용도 | Data | 음성, 영상, Data |
| 변조 | 없음 | 필요 |
| 다중화 | 시분할 다중화 | 주파수 분할 다중화 |

---

# 14. PCM

```text
PCM
→ Pulse Code Modulation
```

아날로그 신호를 디지털 신호로 변환하는 방식이다.

```text
Analog
→ Digital
→ PCM
```

---

# 15. PCM 변조 과정

순서:

```text
표본화(Sampling)
→ 양자화(Quantization)
→ 부호화(Encoding)
→ 복호화(Decoding)
→ 여과(Filtering)
```

### 표본화

```text
Analog 파형을
일정한 시간 간격으로 나누어 Sample 생성
```

### 양자화

```text
표본화된 신호의 진폭을
일정한 값으로 수량화
```

### 부호화

```text
양자화된 진폭 값을
2진법으로 표현
→ Digital Signal로 변환
```

### 복호화

```text
Digital Signal
→ Pulse Signal
```

### 여과

```text
원래 Analog Signal로 복원
```

---

# 16. PCM 특징

장점:

```text
전송 Level 변동 없음
잡음에 강함
다중화가 용이
```

단점:

```text
점유 주파수 대역폭이 큼
```

---

# 시험 직전 암기

```text
AM → 진폭
FM → 주파수
PM → 위상
```

```text
ASK → 0/1에 다른 진폭
FSK → 0/1에 다른 주파수
PSK → 0/1에 다른 위상
```

```text
QAM
→ AM + PM
→ 고속 전송
```

```text
Baseband
→ Digital
→ 근거리
→ 단일 Channel
→ 변조 없음
```

```text
Broadband
→ Analog
→ 장거리
→ 다중 Channel
→ 변조 필요
```

```text
PCM
→ Analog → Digital
```

```text
PCM 순서
표본화
→ 양자화
→ 부호화
→ 복호화
→ 여과
```

## 자주 헷갈리는 부분

```text
AM / ASK
→ 진폭

FM / FSK
→ 주파수

PM / PSK
→ 위상
```

```text
Baseband
→ 변조 X

Broadband
→ 변조 O
```

```text
PCM
→ 표본화 → 양자화 → 부호화
```
