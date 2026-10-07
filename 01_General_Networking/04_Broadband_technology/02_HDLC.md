# HDLC(High-Level Data Link Control)

## 1. HDLC 개요

HDLC는 ISO에서 개발한 국제 표준 프로토콜이다.

```text
HDLC
→ High-Level Data Link Control
→ ISO 국제 표준
```

특징:

```text
Bit-Oriented Protocol
→ 비트 지향형 프로토콜
```

지원 링크:

```text
Point to Point
Multi Point
```

지원 통신 방식:

```text
Half Duplex
Full Duplex
```

---

# 2. HDLC 특징

```text
반이중 통신 지원
전이중 통신 지원
```

```text
동기식 전송 방식
```

Error 제어:

```text
Go-back-N ARQ
Selective Repeat ARQ
```

Flow Control:

```text
Sliding Window
```

---

# 3. 명령과 응답

HDLC는 Frame 내부의 제어 정보를 이용한다.

```text
Command
→ Data Link 설정
→ Data 전송
→ 종료 지시
```

```text
Response
→ Command에 대한 실행 결과
```

---

# 4. Bit Stuffing

HDLC는 문자 코드와 관계없는 비트 지향형 프로토콜이다.

```text
Bit Stuffing 사용
→ 투명한 Data 전송 보장
```

---

# 5. HDLC Frame 구조

```text
Start Flag
→ Address
→ Control
→ Information
→ FCS
→ Stop Flag
```

Bit 크기:

```text
Start Flag → 8bit
Address → 8bit
Control → 8bit
Information → 무제한
FCS → 16bit
Stop Flag → 8bit
```

---

# 6. HDLC Frame 종류

## Information Frame

```text
Information Frame
→ 사용자 Data 전달
```

## Supervisory Frame

```text
Supervisory Frame
→ 흐름 제어
→ Error 제어
```

## Unnumbered Frame

```text
Unnumbered Frame
→ 회선 설정
→ 유지
→ 종결
```

암기:

```text
I Frame
→ Data

S Frame
→ Flow / Error Control

U Frame
→ 회선 설정 / 유지 / 종결
```

---

# 7. Flag Field

Flag는 Frame의 시작과 끝을 구분한다.

```text
Flag
→ 01111110
```

```text
시작 Flag 1개
끝 Flag 1개
```

---

# 8. Address Field

```text
Address Field
→ 송수신 Station 식별
```

기본 크기:

```text
8bit
```

교재 기준:

```text
7bit의 배수 확장 가능
```

Broadcast:

```text
11111111
→ 모든 Station에 방송
```

---

# 9. Control Field

Control Field는 Frame 종류를 정의한다.

```text
Information
→ 사용자 Data 전송
```

```text
Supervisory
→ Piggyback 사용하지 않는 ARQ
```

```text
Unnumbered
→ 보조 링크 제어 가능
```

```text
첫 번째 1bit 또는 2bit
→ Frame 종류 식별
```

---

# 10. Information Field

```text
Information Frame과
Unnumbered Frame에 존재
```

```text
8bit 단위 사용
가변적인 길이
```

---

# 11. FCS

```text
FCS
→ Frame Check Sequence
→ Error 검출
```

교재 기준:

```text
16bit CRC 사용
```

선택적으로:

```text
32bit CRC 사용
```

---

# 시험 직전 암기

```text
HDLC
→ ISO
→ Bit-Oriented
→ Point to Point / Multi Point
→ Half Duplex / Full Duplex
```

```text
전송 방식
→ 동기식
```

```text
Error Control
→ Go-back-N ARQ
→ Selective Repeat ARQ
```

```text
Flow Control
→ Sliding Window
```

```text
Frame 구조
Flag
→ Address
→ Control
→ Information
→ FCS
→ Flag
```

```text
I Frame
→ 사용자 Data
```

```text
S Frame
→ 흐름 / Error 제어
```

```text
U Frame
→ 회선 설정 / 유지 / 종결
```

```text
Flag
→ 01111110
```

```text
FCS
→ Error 검출
→ 16bit CRC
→ 선택적으로 32bit CRC
```
