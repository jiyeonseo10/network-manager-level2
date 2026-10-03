# 회선 교환 / 패킷 교환 / 데이터그램 / 가상회선 / 메시지 교환

## 1. 회선 교환(Circuit Switching)

회선 교환은 송신자와 수신자 사이의 회선을 먼저 독점적으로 연결한 후 통신하는 방식이다.

```text
Circuit Switching
→ 회선 먼저 확보
→ Point to Point
→ 안정적인 통신
```

특징:

```text
송신자의 Message
→ 항상 같은 경로로 전송
```

```text
실시간 처리 가능
안정적 통신 가능
```

```text
음성 전화 시스템에 활용
```

---

## 2. 회선 교환 장점

```text
대용량 Data 고속 전송에 유리
```

```text
고정적인 Bandwidth 사용
```

```text
접속 이후 회선 유지
→ 전송 지연 일정
```

```text
Analog / Digital Data 전송 가능
```

```text
연속적인 전송에 적합
```

---

## 3. 회선 교환 단점

```text
회선 이용률 측면에서 비효율적
```

```text
연결 장치 간 같은 전송률 필요
```

```text
속도 변환 / Code 변환 어려움
```

```text
Error 없는 Data 전송이 중요한 구조에는 부적합
```

```text
통신 비용 높음
```

---

## 4. QoS

QoS는 Quality of Service이다.

```text
QoS
→ Network 품질 평가 지표
```

교재 기준:

```text
QoS가 가장 우수한 Network
→ 회선 교환
```

---

## 5. Bandwidth

```text
Bandwidth
→ 최고 주파수 - 최저 주파수
→ Hz
```

```text
Bandwidth가 클수록
→ 더 많은 Data 전송 가능
```

---

# 6. 패킷 교환(Packet Switching)

패킷 교환은 송신 측에서 Message를 일정 크기의 Packet으로 나누어 전송하고,
수신 측에서 다시 원래 Message로 조립하는 방식이다.

```text
Message
→ Packet 분할
→ 전송
→ 수신 측 재조립
```

인터넷은 고정 경로를 사용하지 않고
Network 상태에 따라 다른 경로를 선택한다.

```text
Internet
→ 고정 경로 X
→ Network 상태에 따라 경로 선택
```

---

## 7. Packet / Datagram

```text
Packet
→ Network 전송을 위해 Data를 일정 단위로 나눈 것
```

```text
Packet + IP Address
→ Datagram
```

Router는 Packet의 최적 경로를 결정한다.

```text
Router
→ 최적 경로 결정
```

---

## 8. 패킷 교환 특징

### 다중화

```text
여러 경로가 Packet 공유
```

### 채널

```text
Virtual Circuit
또는
Datagram 교환 채널 사용
```

### 경로 선택

```text
Packet마다 최적 경로 결정
```

### 순서 제어

```text
Packet마다 다른 경로 가능
→ 도착 순서 달라질 수 있음
→ 순서 제어 필요
```

### Traffic 제어

```text
전송 속도 및 흐름 제어
```

### Error 제어

```text
Error 탐지
→ 재전송
```

---

## 9. 패킷 교환 장점

```text
회선 이용률 높음
```

```text
속도 변환 / Protocol 변환 가능
```

```text
회선 장애 발생
→ 다른 경로 사용 가능
```

```text
Error 검사 및 재전송 가능
```

```text
다중화 사용
→ 효율 높음
```

---

## 10. 패킷 교환 단점

```text
교환기마다 지연 발생 가능
```

```text
송신량 증가
→ 지연 증가 가능
```

```text
Packet Header 추가
→ Overhead 발생
```

---

# 11. 가상회선(Virtual Circuit)

가상회선은 논리적인 연결을 먼저 수행하고,
처음 Packet에서 정한 경로를 계속 사용하는 방식이다.

```text
Virtual Circuit
→ 논리적 연결 먼저
→ 처음 경로 설정
→ 같은 경로 계속 사용
```

특징:

```text
Packet 순서 보장에 유리
```

```text
연결 종료
→ Clear Request Packet 사용
```

---

# 12. 데이터그램(Datagram)

Datagram 방식은 각 Packet이 독립적으로 목적지까지 전송되는 방식이다.

```text
Datagram
→ 사전 경로 설정 없음
→ Packet마다 독립 전송
```

```text
Packet마다 다른 경로 가능
```

장점:

```text
경로 설정 단계 회피 가능
유연성 높음
장애 시 다른 경로 우회 가능
```

단점:

```text
짧은 Message 전송
→ Header 부담
→ 비효율 가능
```

---

# 13. 가상회선 vs 데이터그램

| 구분 | 가상회선 | 데이터그램 |
|---|---|---|
| 연결 | 논리적 연결 먼저 | 사전 연결 없음 |
| 경로 | 같은 경로 사용 | Packet마다 다른 경로 가능 |
| 순서 | 보장에 유리 | 달라질 수 있음 |
| 유연성 | 상대적으로 낮음 | 높음 |
| 장애 우회 | 제한적 | 가능 |

---

# 14. 메시지 교환(Message Switching)

메시지 교환은 송신된 Message를 중앙에 저장한 후 전달하는 방식이다.

```text
Message Switching
→ 중앙에 Message 저장
→ 이후 전달
```

또 다른 표현:

```text
축적 교환 방식
```

특징:

```text
Message를 Memory에 저장
→ 여러 수신자에게 전달 가능
```

```text
전자우편에서 사용
```

---

## 15. 메시지 교환 특징

```text
Message 공유 가능
```

```text
Message별 우선순위 부여 가능
```

```text
Error 제어 제공
```

단점:

```text
응답 속도 느림
```

```text
대화형 System에 부적합
```

---

# 시험 직전 암기

```text
Circuit Switching
→ 회선 독점
→ Point to Point
→ 같은 경로
→ 안정적
→ 전화
```

```text
Packet Switching
→ Packet 분할
→ 인터넷
→ 최적 경로 선택
→ 다중화
→ Error / Traffic / 순서 제어
```

```text
Virtual Circuit
→ 논리적 연결 먼저
→ 같은 경로 사용
```

```text
Datagram
→ Packet마다 독립
→ 서로 다른 경로 가능
```

```text
Message Switching
→ 축적 후 전달
→ 전자우편
→ 응답 느림
```

## 자주 헷갈리는 부분

```text
Circuit Switching
→ 전용 회선

Packet Switching
→ Packet 단위 전송
```

```text
Virtual Circuit
→ 같은 경로

Datagram
→ 다른 경로 가능
```

```text
Message Switching
→ 중앙 저장 후 전달
```
