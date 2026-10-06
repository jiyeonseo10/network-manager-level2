# 전송 매체 / 유선 선로 / 전송 에러

## 1. 전송 매체

전송 선로는 실제 Data를 보내기 위한 물리적인 선로이다.

```text
전송 선로
→ 유선
→ 무선
```

이번 범위에서는 유선 선로를 중심으로 다룬다.

---

# 2. 트위스티드 페어 케이블(Twisted Pair Cable)

2개의 구리선이 서로 감겨 있는 형태의 Cable이다.

```text
Twisted Pair Cable
→ 2개의 구리선
→ 서로 꼬여 있음
```

주요 용도:

```text
전화선
```

### 특징

```text
구성이 쉬움
비용이 저렴함
```

단점:

```text
혼선
감쇠
도청에 취약
```

---

# 3. 동축 케이블(Coaxial Cable)

중앙의 구리선을 플라스틱 절연체 등으로 감싸 만든 Cable이다.

```text
Coaxial Cable
→ 중앙 구리선 사용
```

대표적인 용도:

```text
가정의 TV 수신
```

---

# 4. 광섬유 케이블(Optical Fiber Cable)

빛의 전반사 현상을 이용하여 Data를 전송하는 Cable이다.

```text
Optical Fiber
→ 빛 이용
→ 전반사
```

### 장점

```text
신뢰성이 높음
온도 변화에도 안정적
Error율이 낮음
감쇠의 영향을 적게 받음
도청에 강함
```

### 단점

```text
비용이 높음
설치가 어려움
```

---

# 5. 유선 Cable 비교

| 전송 매체 | 핵심 특징 |
|---|---|
| Twisted Pair | 2개의 구리선이 서로 꼬임 |
| Coaxial | 중앙 구리선 사용, TV 수신 |
| Optical Fiber | 빛의 전반사 이용 |

```text
Twisted Pair
→ 저렴 / 구성 쉬움
→ 혼선·감쇠·도청에 취약
```

```text
Optical Fiber
→ 신뢰성 높음
→ Error율 낮음
→ 비용 높고 설치 어려움
```

---

# 6. 전송 에러

교재에서 제시한 전송 에러:

```text
Noise
Attenuation
Crosstalk
```

---

# 7. 노이즈(Noise)

전송 및 송수신 과정에서 추가되는 불필요한 신호이다.

```text
Noise
→ 불필요한 신호
→ 전송 신호에 왜곡 발생
```

발생 환경의 예:

```text
Monitor
형광등
전자레인지
주변 회선
```

---

# 8. 감쇠(Attenuation)

Data가 회선을 통해 전송되는 동안 전기적 신호가 약해지는 현상이다.

```text
Attenuation
→ 신호 약화
```

쉽게:

```text
전송 거리가 멀어질수록
→ 신호가 약해짐
```

---

# 9. 혼선(Crosstalk)

서로 다른 전송로의 신호가 전기적 결합에 의해 다른 회선에 영향을 주는 현상이다.

```text
Crosstalk
→ 다른 회선의 신호가 섞임
```

교재 예:

```text
전화 통화 중
→ 다른 사람의 말소리가 들리는 현상
```

---

# 10. 전송 에러 비교

| 종류 | 의미 |
|---|---|
| Noise | 불필요한 신호가 추가됨 |
| Attenuation | 신호의 세기가 약해짐 |
| Crosstalk | 다른 회선의 신호가 섞임 |

---

# 시험 직전 암기

```text
Twisted Pair
→ 2개의 구리선
→ 서로 꼬임
→ 전화선
→ 저렴
→ 혼선/감쇠/도청에 취약
```

```text
Coaxial
→ 중앙 구리선
→ TV 수신
```

```text
Optical Fiber
→ 빛
→ 전반사
→ 신뢰성 높음
→ Error율 낮음
→ 도청에 강함
→ 비싸고 설치 어려움
```

```text
Noise
→ 불필요한 신호
```

```text
Attenuation
→ 신호 약화
```

```text
Crosstalk
→ 다른 회선 신호가 섞임
→ 전화 중 다른 사람 목소리
```

## 자주 헷갈리는 부분

```text
Noise
→ 쓸데없는 신호가 추가됨

Attenuation
→ 원래 신호 자체가 약해짐

Crosstalk
→ 옆 회선의 신호가 넘어옴
```
