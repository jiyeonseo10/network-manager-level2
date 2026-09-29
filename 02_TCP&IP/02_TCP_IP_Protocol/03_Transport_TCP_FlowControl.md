# Transport Layer - TCP & Flow Control

## 1. 전송 계층

전송 계층은 송신자와 수신자 사이의 논리적 연결을 수행하는 End-to-End 계층이다.

```text
TCP
→ 연결지향
→ 신뢰성

UDP
→ 비연결
→ 비신뢰성
```

## 2. Segment

```text
Message + TCP Header
→ Segment

Message + UDP Header
→ Segment
```

## 3. TCP

TCP는 Transmission Control Protocol이다.

```text
TCP
→ Connection Oriented
→ Reliable
→ Error Control
→ Flow Control
```

## 4. Sequence Number

```text
Sequence Number
→ 데이터의 Byte 순서 표시
→ 메시지 순서 제어
```

## 5. Checksum

```text
Checksum
→ 데이터 오류 확인
→ TCP / UDP 모두 존재
```

## 6. Receive Window

```text
Receive Window
→ 수신자가 받을 수 있는 버퍼 크기
```

## 7. 3-Way Handshaking

```text
SYN
→ SYN + ACK
→ ACK

→ ESTABLISHED
```

Client:

```text
CLOSED
→ SYN-SENT
→ ESTABLISHED
```

Server:

```text
CLOSED
→ LISTEN
→ SYN-RECEIVED
→ ESTABLISHED
```

## 8. 4-Way Handshaking

```text
FIN
→ ACK
→ FIN
→ ACK
```

관련 상태:

```text
FIN_WAIT1
FIN_WAIT2
TIME_WAIT
CLOSE_WAIT
LAST_ACK
CLOSED
```

## 9. TCP Header 핵심

```text
Source Port
Destination Port
Sequence Number
Acknowledgement Number
Header Length
URG
ACK
RST
SYN
FIN
Window Size
Checksum
Urgent Pointer
Options
```

```text
SYN
→ 연결 설정

ACK
→ 전송 확인

FIN
→ 연결 해제

RST
→ 연결 재설정

Window Size
→ 수신 가능한 최대 Byte 수

Checksum
→ 오류 검사
```

## 10. TCP 주요 기능

```text
신뢰성 있는 전송
→ ACK

순서 제어
→ Sequence Number

완전이중
→ 송신 / 수신 동시 수행

흐름 제어
→ 송신 속도 조절

혼잡 제어
→ 네트워크 상황에 따라 전송 속도 조절
```

## 11. Flow Control

```text
Flow Control
→ 전송량 / 속도 조절
→ 수신 측 Overflow 방지
```

## 12. Sliding Window

```text
Sliding Window
→ Window Size만큼 연속 전송
→ ACK 확인 후 Window 이동
→ 전송 효율 향상
```
