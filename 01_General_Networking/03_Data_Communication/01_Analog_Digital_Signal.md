# 정보 신호 / Analog / Digital / 신호 변환

## 1. 정보 신호

정보 신호(Information Signal)는 크게 두 종류로 구분된다.

```text
Information Signal
→ Analog Signal
→ Digital Signal
```

---

# 2. Analog Signal

Analog Signal은 연속적으로 변화하는 신호이다.

대표적인 예:

```text
사람의 음성
```

특징:

```text
연속적인 곡선 형태
거리 증가
→ 신호 감쇠
→ 손상 발생
```

---

# 3. Digital Signal

Digital Signal의 대표적인 예는 Computer이다.

```text
Digital Signal
→ 0 또는 1
→ 이진 형태
```

Analog Signal과 비교하면:

```text
잡음이 적음
오류율이 적음
```

---

# 4. 신호 변환 방식

| 정보 형태 | 전송 방식 | 주요 방법 | 변환기 |
|---|---|---|---|
| Analog | Analog 전송 | 신호 증폭 | 전화기 |
| Analog | Digital 전송 | Coding | PCM |
| Digital | Analog 전송 | Modem 사용 | Modem |
| Digital | Digital 전송 | DSU 사용 | DSU |

---

# 5. Analog → Analog

Analog Signal을 Analog 방식으로 전송한다.

```text
Analog
→ Analog
→ 신호 증폭
```

신호가 감쇠되기 때문에 증폭기를 이용하여 신호의 세기를 증폭한다.

교재 표의 신호 변환기:

```text
전화기
```

---

# 6. Analog → Digital

Analog Signal을 Digital Signal로 변환할 때 PCM을 사용한다.

```text
Analog
→ Digital
→ PCM
```

PCM:

```text
Pulse Code Modulation
```

교재 핵심:

```text
Coding 사용
Digital 전송을 위해 원음을 재생
왜곡 발생 방지
패턴 재생을 통한 신호 재생성
```

---

# 7. Digital → Analog

Digital Signal을 Analog 통신망으로 전송할 때 Modem을 사용한다.

```text
Digital
→ Analog
→ Modem
```

```text
Modem
→ Analog 통신망을 이용하여
   Digital Signal 전송
```

---

# 8. Digital → Digital

Digital Signal을 Digital 방식으로 전송할 때 DSU를 사용한다.

```text
Digital
→ Digital
→ DSU
```

DSU:

```text
Digital Service Unit
```

교재 핵심:

```text
Digital Signal을 안정적으로 멀리 전송
적당한 간격으로 Repeater 설치
```

---

# 9. PCM / Modem / DSU 비교

```text
Analog → Digital
→ PCM
```

```text
Digital → Analog
→ Modem
```

```text
Digital → Digital
→ DSU
```

이 세 가지를 반드시 구분한다.

---

# 10. Digital Signal의 장점

교재 기준:

```text
저렴한 비용
Data 무결성 보장
전송 용량 이용 확대
Data 안정성 증대
잡음에 강함
```

핵심:

```text
Digital
→ 무결성
→ 안정성
→ 잡음에 강함
```

---

# 11. Analog Signal의 단점

교재 기준:

```text
유지보수 비용 증가
잡음 증폭도 높음
```

---

# 시험 직전 암기

```text
Analog
→ 연속적으로 변화
→ 대표 예: 음성
→ 거리 증가 시 감쇠
```

```text
Digital
→ 0 / 1
→ 대표 예: Computer
→ 잡음 적음
→ 오류율 적음
```

```text
Analog → Digital
→ PCM
→ Pulse Code Modulation
```

```text
Digital → Analog
→ Modem
```

```text
Digital → Digital
→ DSU
→ Digital Service Unit
```

```text
Digital 장점
→ 저렴한 비용
→ 무결성
→ 안정성
→ 잡음에 강함
```

```text
Analog 단점
→ 유지보수 비용 증가
→ 잡음 증폭도 높음
```

## 자주 헷갈리는 부분

```text
PCM
→ A → D
```

```text
Modem
→ D → A
```

```text
DSU
→ D → D
```

한 줄 암기:

```text
PCM = 아날로그를 디지털로
Modem = 디지털을 아날로그 회선으로
DSU = 디지털을 디지털 회선으로
```
