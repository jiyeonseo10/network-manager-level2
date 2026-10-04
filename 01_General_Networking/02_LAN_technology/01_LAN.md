# LAN / ALOHA / CSMA-CD / IEEE 802

## 1. LAN(Local Area Network) 개요

LAN은 건물, 공장, 학교 등 제한된 지역 내에서 정보기기 간 통신을 수행하기 위한 근거리 통신망이다.

```text
LAN
→ Local Area Network
→ 제한된 지역
→ 일반적인 전송 거리 약 50m
```

특징:

```text
파일 Server 공유
Printer 공유
통신기기 연결
```

교재 기준 전송 속도:

```text
10Mbps ~ 100Mbps
```

또한 Multimedia Data를 전송할 수 있다.

---

## 2. Channel

Channel은 데이터 통신을 위해 통신 매체에서 제공하는 통로이다.

```text
Channel
→ Data 통신을 위한 통로
```

---

# 3. LAN의 주요 목적

## 자원 공유

```text
원격지 자원 공유
여러 사용자가 자원 사용
자원을 효율적으로 활용
```

## 분산 처리

```text
독립된 장비에서 계산 및 작업 처리
```

전체 System의 능력은 연결된 Computer의 능력에 따라 결정된다.

## 분산 제어

```text
독립된 장치 간 통신
→ Process 제어
```

```text
높은 Data 전송 속도
신뢰도 유지
```

## 정보 교환

```text
Video
Voice
Text Data
```

---

# 4. LAN 장점

```text
Packet 손실 및 지연이 적음
자료 공유가 쉽고 빠름
신뢰성이 높음
구축 비용이 적음
오류 발생률이 낮음
```

---

# 5. LAN 단점

```text
전송 거리가 짧음
→ 거리 제한
```

```text
Node 증가
→ 충돌 발생
→ 성능 저하
```

---

# 6. 자원 공유 확인

Windows에서 공유된 자원을 확인할 때:

```bash
net share
```

```text
net share
→ 공유된 자원 확인
```

---

# 7. ALOHA

ALOHA는 중앙국의 제어 없이 무작위로 공통 전송 Channel에 접속하는 경쟁 방식의 다원 접속 Protocol이다.

```text
ALOHA
→ 중앙 제어 없음
→ 무작위 접속
→ 공통 Channel 사용
```

송신 측:

```text
Packet이 있으면 전송
→ ACK 대기
```

수신 측:

```text
Packet 수신
→ 오류 검사
→ ACK 전송
```

ACK가 일정 시간 안에 도착하지 않으면:

```text
Packet 손실로 판단
→ 일정 시간 대기
→ 재전송
```

---

# 8. Slotted ALOHA

Slotted ALOHA는 Clock을 사용하여 모든 Station을 동기화한 후 Packet을 전송한다.

```text
Slotted ALOHA
→ Clock 사용
→ Station 동기화
```

장점:

```text
충돌 확률 감소
→ 성능 향상
```

교재 기준:

```text
ALOHA보다 전송 처리율 2배
```

또한 주로 무선 LAN에서 사용된다.

---

# 9. CSMA/CD

CSMA/CD는 전송 전에 전송 매체가 사용 중인지 확인한다.

```text
Carrier Sense
→ 회선 사용 여부 확인
```

다른 장치가 사용 중이면:

```text
전송하지 않음
→ 대기
```

CSMA/CD:

```text
Carrier Sense Multiple Access
with Collision Detection
```

핵심:

```text
전송 전 회선 확인
→ 충돌 감지
```

---

# 10. CSMA/CD 충돌 처리

충돌이 발생하면:

```text
Collision 발생
→ Frame 송신 중단
→ Jam Signal 전송
→ 일정 시간 대기
→ 재전송
```

교재 기준:

```text
최대 15번 재전송
```

---

# 11. Jam Signal

```text
Jam Signal
→ Collision 발생을 모든 Host에게 알림
```

---

# 12. IEEE 802

IEEE 802 위원회는 LAN 관련 표준화를 수행한다.

주요 표준:

| 표준 | 내용 |
|---|---|
| 802.1 | 상위 계층 Interface와 MAC Bridge |
| 802.2 | LLC(Logical Link Control) |
| 802.3 | CSMA/CD |
| 802.4 | Token Bus |
| 802.5 | Token Ring |
| 802.6 | MAN |
| 802.7 | Broadband LAN |
| 802.8 | Fiber Optic LAN |
| 802.9 | 종합 Data & 음성 Network |
| 802.10 | Security |
| 802.11 | Wireless Network |

---

# 시험 직전 암기

```text
LAN
→ 약 50m
→ 10~100Mbps
→ File / Printer 공유
```

```text
LAN 장점
→ 손실/지연 적음
→ 신뢰성 높음
→ 자료 공유 쉬움
→ 구축 비용 적음
```

```text
LAN 단점
→ 거리 제한
→ Node 증가 시 Collision 발생
→ 성능 저하
```

```text
net share
→ 공유 자원 확인
```

```text
ALOHA
→ 중앙 제어 X
→ 무작위 접속
→ ACK 없으면 재전송
```

```text
Slotted ALOHA
→ Clock 동기화
→ Collision 감소
→ 처리율 2배
```

```text
CSMA/CD
→ 회선 먼저 확인
→ Collision Detection
→ Jam Signal
→ 대기 후 재전송
→ 최대 15회
```

```text
802.3 → CSMA/CD
802.4 → Token Bus
802.5 → Token Ring
802.6 → MAN
802.10 → Security
802.11 → Wireless Network
```

## 자주 헷갈리는 부분

```text
ALOHA
→ 아무 때나 전송 가능

Slotted ALOHA
→ Clock에 맞춰 전송
```

```text
CSMA/CD
→ 보내기 전에 회선 확인
→ 충돌 발생하면 Jam Signal
```

```text
802.3 → CSMA/CD
802.5 → Token Ring
802.6 → MAN
802.11 → Wireless
```
