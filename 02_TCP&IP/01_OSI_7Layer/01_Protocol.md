# Protocol

네트워크관리사 2급 TCP/IP 파트의 **프로토콜(Protocol)** 내용을 정리한다.

---

## 1. 프로토콜 개요

프로토콜은 송신자와 수신자 사이에서 데이터를 주고받기 위해 미리 정해 놓은 **통신 규약**이다.

```text
송신자 ↔ 수신자

어떤 형식으로 데이터를 보낼지
어떤 의미로 해석할지
어떤 순서와 속도로 통신할지

→ 미리 정한 약속 = Protocol
```

프로토콜은 데이터 통신을 수행하기 위한 규칙들의 집합이다.

---

## 2. 프로토콜 구성 요소

프로토콜은 송신자와 수신자 간의 통신을 위해 다음 세 가지를 규약한다.

- 구문(Syntax)
- 의미(Semantics)
- 순서(Timing)

### 구문(Syntax)

데이터의 형식과 관련된 규칙이다.

```text
Syntax
→ 데이터 형식
→ 신호 레벨
→ 부호화
```

### 의미(Semantics)

통신 내용의 의미와 제어 정보를 규정한다.

```text
Semantics
→ 개체의 조정
→ 에러 제어 정보
```

### 순서(Timing)

데이터의 전송 순서와 통신 속도를 규정한다.

```text
Timing
→ 순서 제어
→ 통신 속도 제어
```

---

## 3. 프로토콜 구성 요소 비교

| 구성 요소 | 설명 |
|---|---|
| Syntax | 데이터 형식, 신호 레벨, 부호화 |
| Semantics | 개체의 조정, 에러 제어 정보 |
| Timing | 순서 제어, 통신 속도 제어 |

```text
Syntax
→ 형식

Semantics
→ 의미 / 제어

Timing
→ 순서 / 속도
```

---

## 4. 데이터 전송 방식

송신자와 수신자 사이의 데이터 전송 방식은 비트 단위, 바이트 단위, 문자 단위 전송 방법으로 구분한다.

---

## 5. 비트 단위 전송

비트 단위로 데이터를 전송할 때 특수 플래그를 포함하여 데이터를 전송한다.

대표 프로토콜:

```text
SDLC
→ Synchronous Data Link Control

HDLC
→ High-level Data Link Control
```

```text
비트 단위 전송
→ SDLC
→ HDLC
```

---

## 6. 바이트 단위 전송

바이트 단위 전송은 전송을 위한 제어 정보를 **데이터 헤더에 포함**하여 데이터를 전송한다.

대표 프로토콜:

```text
DDCM
→ Digital Data Communication Message
```

```text
바이트 단위 전송
→ DDCM
```

---

## 7. 문자 단위 전송

문자 단위 전송은 데이터를 전송할 때 데이터의 시작과 끝에 **특수 문자를 포함**하여 전송한다.

대표 프로토콜:

```text
BSC
→ Binary Synchronous Communication
```

```text
문자 단위 전송
→ BSC
```

---

## 8. OSI 7계층

통신 프로토콜 중 대표적인 것은 ISO에서 정의한 **OSI 7계층 프로토콜**이다.

```text
ISO
→ International Organization for Standardization

OSI
→ Open System Interconnection
→ 7계층
```

---

## 9. 데이터 전송 방식 비교

| 전송 방식 | 특징 | 프로토콜 |
|---|---|---|
| 비트 단위 | 특수 플래그 포함 | SDLC, HDLC |
| 바이트 단위 | 제어 정보를 데이터 헤더에 포함 | DDCM |
| 문자 단위 | 시작과 끝에 특수 문자 포함 | BSC |

---

## 10. 시험 직전 암기

```text
Protocol
→ 송신자와 수신자 간 통신 규약
→ 데이터 통신 수행 규칙의 집합

프로토콜 구성 요소 3개

Syntax
→ 데이터 형식
→ 신호 레벨
→ 부호화

Semantics
→ 개체 조정
→ 에러 제어 정보

Timing
→ 순서 제어
→ 통신 속도 제어

비트 단위
→ SDLC
→ HDLC

바이트 단위
→ DDCM

문자 단위
→ BSC

ISO
→ OSI 7계층 정의
```
