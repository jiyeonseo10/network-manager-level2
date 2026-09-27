# Error Control

네트워크관리사 2급 TCP/IP 파트의 **에러 제어(Error Control)** 내용을 정리한다.

---

## 1. 에러 제어 개요

네트워크를 이용하여 데이터를 송신하면 여러 형태의 에러가 발생할 수 있다.

책에서 제시한 예:

- 송신 및 수신 프로그램 에러
- 네트워크 케이블 절단
- 무선 전송 시 신호 감소
- 잡음

에러가 발생하면 먼저 에러 발생 여부를 탐지한 후 에러를 수정해야 한다.

```text
Error Control

1. Error Detection
→ 오류 발생 여부 탐지

2. Error Correction
→ 오류 수정
```

---

## 2. FEC와 BEC

에러 제어 방식은 크게 FEC와 BEC로 구분한다.

### FEC

FEC는 **Forward Error Correction**이다.

수신된 데이터에 에러가 없는지 확인하고 필요한 경우 오류를 정정하는 방식이다.

```text
FEC
→ Forward Error Correction
→ 수신 데이터 오류 확인
→ 오류 정정
```

### BEC

BEC는 **Backward Error Correction**이다.

수신자가 데이터를 정상적으로 수신하지 못했을 경우 송신자에게 재전송을 요청하는 방식이다.

```text
BEC
→ Backward Error Correction
→ 오류 검출
→ 송신 측에 재전송 요청
```

---

## 3. FEC 오류 검출 및 정정 코드

책에서 제시한 대표적인 방식은 다음과 같다.

- Hamming Code
- CRC
- Parity Bit

---

## 4. Hamming Code

해밍 코드(Hamming Code)는 오류 발견 및 교정이 가능한 코드이다.

책에서는 **1비트의 에러 검출 및 교정**이 가능하다고 설명한다.

```text
Hamming Code
→ 1bit 오류 검출
→ 1bit 오류 교정
```

---

## 5. CRC

CRC는 **Cyclic Redundancy Check**이다.

데이터 통신에서 전송 중 오류가 발생했는지를 확인하기 위해 데이터를 추가하여 검사하는 방식이다.

책에서는 실제로 많이 사용되는 오류 검출 방식으로 설명한다.

```text
CRC
→ Cyclic Redundancy Check
→ 데이터 전송 중 오류 발생 여부 확인
```

책에서는 Check Sum 비트를 전송하여 수신자가 오류 여부를 확인하는 것으로 설명한다.

사용 예:

```text
무선 LAN
Ethernet Frame
```

---

## 6. Parity Bit

패리티 비트는 데이터에 하나의 비트를 추가하여 오류를 검출한다.

데이터 내의 Set(1) 비트 수를 확인하여 짝수 또는 홀수가 되도록 비트를 추가한다.

### Odd Parity

```text
Odd Parity
→ 1의 개수를 홀수로 맞춤
```

### Even Parity

```text
Even Parity
→ 1의 개수를 짝수로 맞춤
```

책에서는 패리티 검사를 FEC 기법 중 가장 간단한 방식으로 설명한다.

---

## 7. FEC와 BEC 비교

| 구분 | 설명 |
|---|---|
| FEC | 송수신되는 패킷의 무결성을 검사 |
| BEC | 수신 측에서 오류를 검출한 후 재전송 요청 |

FEC 방식의 예:

```text
Parity Check
CRC
```

BEC에서는 오류 처리를 위해 ARQ를 사용한다.

```text
ARQ
→ Auto Repeat Request
```

---

## 8. BEC 기법

책에 나온 BEC 방식:

```text
Stop-and-Wait
Go-Back-N
Selective Repeat
Adaptive ARQ
```

---

## 9. Stop-and-Wait

송신자가 데이터를 전송한 후 수신 응답이 오면 다음 데이터를 전송하는 방식이다.

```text
송신
→ 응답 대기
→ ACK 수신
→ 다음 데이터 전송
```

오류가 발생하면 즉시 재전송한다.

### 특징

- 순차적으로 수신
- 가장 단순한 구현
- 신뢰성 있는 전송
- 대기 시간 때문에 전송 효율이 저하될 수 있음

```text
Stop-and-Wait
→ 하나 전송
→ ACK 기다림
→ 다음 데이터 전송
```

---

## 10. Go-Back-N

수신자가 데이터를 정상적으로 받지 못한 경우 **마지막으로 정상 수신된 데이터 이후의 모든 데이터를 다시 전송**하는 방식이다.

책에서는 TCP 프로토콜에서 사용하는 방식이라고 설명한다.

```text
Go-Back-N
→ 오류 또는 손실 발생
→ 그 이후의 데이터 모두 재전송
```

### 특징

- 프레임 송신 순서와 수신 순서가 동일해야 함
- 구현이 간단
- 수신 측 버퍼 사용량이 적음

```text
오류 이후
→ 전부 다시 전송
```

---

## 11. Selective Repeat

수신한 데이터 중 중간에 빠져 있는 데이터만 선택적으로 재전송하는 방식이다.

```text
Selective Repeat
→ 오류 난 프레임만 재전송
```

### 특징

- 순서와 관계없이 Window 크기 범위 안에서 자유롭게 수신
- 오류 또는 손실 프레임을 재요청하거나 타임아웃으로 재전송
- 구현이 복잡
- 버퍼 사용량이 큼
- 불필요한 재전송이 적어 대역폭을 효율적으로 사용

---

## 12. BEC 기법 비교

| 구분 | Stop-and-Wait | Go-Back-N | Selective Repeat |
|---|---|---|---|
| 재전송 | 오류 발생 즉시 재전송 | 오류 이후 모든 프레임 재전송 | 오류 프레임만 재전송 |
| 수신 | 순차적 | 송신 순서와 수신 순서 동일 | Window 범위에서 자유롭게 수신 |
| 구현 | 가장 단순 | 간단 | 복잡 |
| 버퍼 | - | 적게 사용 | 많이 사용 |
| 특징 | 대기 시간으로 효율 저하 | 불필요한 재전송 가능 | 재전송 대역폭 효율적 |

---

## 13. 시험 직전 암기

```text
Error Control
→ 오류 탐지
→ 오류 수정

FEC
→ Forward Error Correction
→ 수신 데이터 오류 확인 및 정정

BEC
→ Backward Error Correction
→ 오류 검출 후 재전송 요청

Hamming Code
→ 1bit 오류 검출 및 교정

CRC
→ Cyclic Redundancy Check
→ 전송 오류 확인
→ 무선 LAN / Ethernet Frame

Parity Bit
→ 1bit 추가

Odd Parity
→ 1의 개수를 홀수로

Even Parity
→ 1의 개수를 짝수로

BEC
→ ARQ 사용

Stop-and-Wait
→ 하나 보내고 ACK 기다림

Go-Back-N
→ 오류 이후 모두 재전송

Selective Repeat
→ 오류 난 프레임만 재전송
```
