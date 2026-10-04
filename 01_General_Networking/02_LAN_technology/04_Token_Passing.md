# Token Passing

## 1. Token Passing 개요

Token Passing은 Token이라는 제어 비트를 사용하여 통신하는 방식이다.

```text
Token Passing
→ Token이라는 제어 비트 사용
→ Token을 확보한 Node가 통신
```

Token은 논리적으로 형성된 Ring에서 각 Node 사이를 이동한다.

```text
Ring
→ Token이 Node 사이를 순차적으로 이동
→ Token을 가진 Node가 Data 전송
```

가장 중요한 특징:

```text
Collision 발생하지 않음
```

---

## 2. Token Passing 특징

```text
가변 길이 Data Frame 전송 가능
```

```text
Hardware 장비가 복잡
→ 평균 대기 시간 높음
```

```text
부하가 높을 때 안정적
```

```text
접근 시간이 대략 일정
```

---

## 3. Ring 방식

Token Passing은 Ring 형태의 Network Topology를 사용한다.

```text
Token Passing
→ Ring Topology
```

```text
Node 1
→ Node 2
→ Node 3
→ ...
→ 순차적으로 이동
```

---

## 4. 추가 특징

```text
특정한 Bit Pattern으로 구성된 짧은 Frame 형태
```

```text
통신 회선의 길이가 무제한
```

```text
확장성이 좋음
```

```text
고속 Burst 전송에 유리
```

---

## 5. Token Passing 장점

```text
Collision 발생하지 않음
```

```text
성능 저하가 적음
```

---

## 6. Token Passing 단점

```text
설치 비용이 높음
```

```text
구조가 복잡함
```

```text
Node가 많으면 성능 저하
```

```text
Token 분실 가능
```

---

# 시험 직전 암기

```text
Token Passing
→ Token 사용
→ Ring Topology
→ Collision 없음
```

```text
특징
→ 가변 길이 Frame
→ 부하가 높을 때 안정적
→ 접근 시간 대략 일정
```

```text
장점
→ Collision 없음
→ 성능 저하 적음
```

```text
단점
→ 설치 비용 높음
→ 구조 복잡
→ Node 많으면 성능 저하
→ Token 분실 가능
```

## 자주 헷갈리는 부분

```text
CSMA/CD
→ 충돌 발생 가능
→ 충돌 감지 후 재전송

Token Passing
→ Token 가진 Node만 전송
→ Collision 없음
```

```text
Token Passing
→ Ring
→ 순차적 접근
```
