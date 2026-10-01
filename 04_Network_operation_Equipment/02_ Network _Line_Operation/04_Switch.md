# Switch

## 1. Switch 개요

Switch는 Hub와 거의 유사하지만 Hub보다 전송 속도가 향상된 장치이다.

```text
Switch
→ Hub와 유사
→ Hub보다 전송 속도 향상
```

Switch는 목적지 Port로 직접 데이터를 전송하므로
Network 충돌을 줄이고 효율을 향상시킨다.

```text
Switch
→ 목적지 Port로 직접 전송
→ Network 효율 향상
```

---

## 2. Switch의 다른 이름

```text
Switching Hub
Port Switching Hub
```

---

## 3. Switch 특징

송신자 Node와 수신자 Node를 일대일로 연결한다.

```text
송신자 Node
↔ 수신자 Node

→ 일대일 연결
→ 충돌 발생하지 않음
```

또한:

```text
빠른 Data 전송 가능
```

```text
송신/수신 Node 수가 증가해도
→ Network 속도 저하가 적음
```

```text
불필요한 Network 전송 최소화
```

```text
Port별 일정한 속도로 전송
```

교재에서는 전송되는 Packet에 대해 감청이 어렵다고 설명한다.

---

# 4. Switch 방식

Switching 방식은 다음 3가지이다.

```text
Cut Through
Store and Forward
Fragment Free
```

---

## 5. Cut Through

목적지 MAC Address를 확인한 후 해당 Port로 전송한다.

```text
Cut Through
→ Destination MAC Address 확인
→ 해당 Port로 전송
```

핵심:

```text
Destination MAC 확인
→ 바로 전송
```

---

## 6. Store and Forward

전체 Frame을 모두 저장한 후 Error Check를 수행하고 전송한다.

```text
Store and Forward
→ 전체 Frame 저장
→ Error Check
→ 전송
```

순서:

```text
Store
→ Check
→ Forward
```

---

## 7. Fragment Free

Fragment Free는 Cut Through를 수정한 방식이다.

```text
Fragment Free
→ Modify Cut Through
```

교재 기준:

```text
Frame의 64Bit 검사
Header Error 검사 후 전송
```

또한:

```text
512Bit가 수신될 때까지 대기
→ Error 존재 여부 확인
→ Error가 없으면 전송
```

핵심:

```text
Fragment Free
→ Cut Through 변형
→ Frame 앞부분 검사
→ 512Bit 대기
→ Error 확인 후 전송
```

---

# 8. Switching 방식 비교

| 방식 | 특징 |
|---|---|
| Cut Through | Destination MAC 확인 후 즉시 전송 |
| Store and Forward | 전체 Frame 저장 후 Error Check |
| Fragment Free | Cut Through 변형, 앞부분 검사 후 전송 |

---

# 시험 직전 암기

```text
Switch
→ Hub와 유사
→ Hub보다 빠름
→ 목적지 Port로 직접 전송
```

```text
Switching Hub
Port Switching Hub
→ Switch의 다른 이름
```

```text
Switch
→ 송신자/수신자 1:1 연결
→ 충돌 감소
→ 불필요한 전송 최소화
```

```text
Cut Through
→ Destination MAC 확인
→ 바로 전송
```

```text
Store and Forward
→ 전체 Frame 저장
→ Error Check
→ 전송
```

```text
Fragment Free
→ Modify Cut Through
→ 512Bit 수신 대기
→ Error 확인 후 전송
```

## 자주 헷갈리는 부분

```text
Cut Through
→ 빠르게 바로 전달

Store and Forward
→ 전체 Frame 저장 후 검사

Fragment Free
→ 일부를 먼저 검사한 뒤 전달
```

```text
Hub
→ 여러 Port로 신호 분배

Switch
→ 목적지 Port로 직접 전송
```
