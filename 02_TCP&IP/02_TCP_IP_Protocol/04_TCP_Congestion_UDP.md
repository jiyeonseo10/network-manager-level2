# TCP Congestion Control & UDP

## 1. Congestion Control

```text
Congestion Control
→ 네트워크 혼잡 제어
→ 송신 전송률 조절
→ 데이터 손실 최소화
```

## 2. TCP Slow Start

```text
초기 CWnd = 1

ACK 수신
→ 2
→ 4
→ 8
→ 16
```

```text
Slow Start
→ 지수적 증가
```

## 3. Congestion Avoidance

```text
임계값 도달
→ Congestion Avoidance

Congestion Avoidance
→ 선형적 증가
```

## 4. Fast Retransmit

```text
Duplicate ACK가 연속적으로 일정 기준 이상 수신
→ 해당 Segment 즉시 재전송
```

## 5. Fast Recovery

```text
Fast Retransmit 이후
→ 새 Slow Start로 처음부터 시작하지 않음
→ Congestion Avoidance 상태에서 전송
```

## 6. Sequence Number / ACK Number

```text
ACK Number
= Sequence Number + 받은 Byte 수
```

예:

```text
Seq 1301 + 100Byte
→ ACK 1401

Seq 1401 + 100Byte
→ ACK 1501
```

3-Way Handshaking에서는:

```text
Seq = 1000
→ ACK = 1001
```

## 7. UDP

UDP는 User Datagram Protocol이다.

```text
UDP
→ Connectionless
→ Unreliable
→ 빠른 전송
→ 재전송 기능 없음
```

송수신 성공 여부에 대한 책임은 Application이 가진다.

## 8. UDP 특징

```text
비신뢰성
→ 전송 성공 보장 X

비접속성
→ Packet 상태 유지 X

간단한 Header
→ 처리 단순

빠른 전송
→ TCP보다 빠름
```

## 9. UDP Header

```text
Source Port
Destination Port
Length
Checksum
```

```text
UDP
→ Sequence Number 없음
→ ACK Number 없음
→ Sliding Window 사용하지 않음
```

## 시험 직전 비교

```text
TCP
→ 연결지향
→ 신뢰성
→ ACK
→ Sequence Number
→ 재전송
→ Sliding Window
→ Flow Control
→ Congestion Control

UDP
→ 비연결
→ 비신뢰성
→ 재전송 X
→ Header 단순
→ 빠른 전송
```
