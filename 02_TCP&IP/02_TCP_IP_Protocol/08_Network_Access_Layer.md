# 네트워크 접근 계층(Network Access Layer)

## 1. 네트워크 접근 계층 개요

네트워크 접근 계층은 LAN 카드의 물리적 주소인 MAC 주소를 사용하여 메시지를 전기적인 Bit 신호로 전송하는 계층이다.

```text
Network Access Layer
→ MAC Address 사용
→ Frame 단위
→ Bit 신호로 전송
→ 통신기기 간 연결 및 데이터 전송 지원
```

인터넷 계층과 비교:

```text
Internet Layer
→ IP 주소
→ 경로 결정

Network Access Layer
→ MAC 주소
→ 실제 데이터 전송
```

---

## 2. 데이터 단위

네트워크 접근 계층의 데이터 단위는 Frame이다.

```text
Network Access Layer
→ Frame
→ Bit 단위로 전송
```

---

## 3. Frame 구조

```text
Preamble
SOF
Destination Address
Source Address
Type
Data
PAD
FCS
```

Frame은 크게 다음과 같이 구성된다.

```text
Header
Payload
Footer
```

---

## 4. Preamble

```text
Preamble
→ 동기화 정보
→ 7 Bytes
```

---

## 5. SOF

SOF는 Starting Frame Delimiter이다.

```text
SOF
→ Frame 시작을 알리는 구분자
→ 1 Byte
```

```text
Preamble 7 Bytes
+
SOF 1 Byte
=
8 Bytes
```

---

## 6. Destination Address

```text
Destination Address
→ 수신자(목적지)의 물리적 MAC 주소
→ 6 Bytes
```

---

## 7. Source Address

```text
Source Address
→ 송신자의 물리적 MAC 주소
→ 6 Bytes
```

핵심:

```text
Destination
→ 수신자

Source
→ 송신자
```

---

## 8. Type

```text
Type
→ 상위 계층 Protocol의 종류 표시
→ 2 Bytes
```

---

## 9. Data

실제 데이터를 저장하는 영역이다.

```text
Data
→ 46 ~ 1500 Bytes
```

---

## 10. PAD

Frame이 최소 길이를 만족하지 못할 경우 부족한 부분을 0으로 채운다.

```text
PAD
→ Frame 길이를 맞추는 영역
→ 최소 64 Byte를 만족하지 못하면 0으로 채움
```

---

## 11. FCS

FCS는 Frame Check Sequence이다.

```text
FCS
→ Bit열의 오류 검사
→ 4 Bytes
```

---

## 12. Frame 크기

```text
Frame
→ 64 ~ 1518 Bytes
```

교재 그림 기준 주요 크기:

```text
Preamble        → 7 Bytes
SOF             → 1 Byte
Destination MAC → 6 Bytes
Source MAC      → 6 Bytes
Type            → 2 Bytes
Data            → 46 ~ 1500 Bytes
FCS             → 4 Bytes
```

---

# 시험 직전 암기

```text
Network Access Layer
→ MAC Address
→ Frame
→ Bit 전송
```

```text
Preamble
→ 동기화
→ 7 Bytes

SOF
→ Frame 시작
→ 1 Byte

Destination Address
→ 수신자 MAC
→ 6 Bytes

Source Address
→ 송신자 MAC
→ 6 Bytes

Type
→ 상위 Protocol 종류
→ 2 Bytes

Data
→ 46 ~ 1500 Bytes

PAD
→ 최소 Frame 길이 맞춤
→ 부족하면 0으로 채움

FCS
→ 오류 검사
→ 4 Bytes
```

```text
Frame Size
→ 64 ~ 1518 Bytes
```

## 자주 헷갈리는 부분

```text
IP 주소
→ Internet Layer

MAC 주소
→ Network Access Layer
```

```text
SOF
→ 시작 표시

FCS
→ 오류 검사

PAD
→ 길이 맞춤
```

```text
Destination
→ 받는 쪽

Source
→ 보내는 쪽
```
