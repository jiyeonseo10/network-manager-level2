# TCP/IP Protocol

네트워크관리사 2급 TCP/IP 파트의 **TCP/IP 프로토콜** 내용을 정리한다.

---

## 1. TCP/IP 개요

TCP/IP는 **Transmission Control Protocol / Internet Protocol**의 약자이다.

책 기준 특징:

- DoD(미국방성) 모델
- OSI 7계층과 매우 유사
- OSI보다 먼저 만들어짐
- ARPANET에서 개발
- 인터넷에서 널리 사용
- 서로 다른 네트워크 간 상호 접속 가능

```text
TCP/IP
→ Transmission Control Protocol / Internet Protocol
→ DoD 모델
→ ARPANET에서 개발
→ 인터넷에서 널리 사용
```

---

## 2. TCP/IP 4계층

TCP/IP는 다음 4계층으로 구성된다.

```text
Application
Transport
Internet
Network Access
```

---

## 3. Application 계층

사용자가 사용하는 프로그램이 있는 계층이다.

책에 나온 프로토콜:

```text
FTP
Telnet
SSH
HTTP
SMTP
SNMP
```

```text
Application
→ 사용자 응용 프로그램
→ FTP / Telnet / SSH / HTTP / SMTP / SNMP
```

---

## 4. Transport 계층

전송 계층에는 TCP와 UDP가 있다.

### TCP

- 연결지향형(Connection Oriented)
- 신뢰성 있는 전송
- 가상 연결 지원
- Error Control 수행
- ACK 사용

```text
TCP
→ Connection Oriented
→ 신뢰성
→ Error Control
→ ACK
```

수신자는 송신자의 메시지를 정상적으로 받으면 ACK를 전송한다.

```text
ACK가 오지 않음
→ 재전송
```

### UDP

- 비연결형(Connectionless)
- 데이터 전송을 보장하지 않음
- TCP보다 전송 속도가 빠름

```text
UDP
→ Connectionless
→ 비신뢰성
→ 빠른 전송
```

---

## 5. Internet 계층

IP 주소를 이용하여 경로를 결정하고 라우팅을 수행한다.

책 기준 관련 프로토콜:

```text
IP
ARP
RARP
ICMP
```

```text
Internet
→ IP
→ Routing
→ ARP
→ RARP
→ ICMP
```

---

## 6. ARP

ARP는 IP 주소를 MAC 주소로 변환한다.

```text
ARP
→ IP Address → MAC Address
```

---

## 7. RARP

RARP는 MAC 주소를 IP 주소로 변환한다.

```text
RARP
→ MAC Address → IP Address
```

---

## 8. ICMP

ICMP는 네트워크의 오류와 상태를 점검하기 위해 사용한다.

```text
ICMP
→ 네트워크 오류 점검
→ 네트워크 상태 확인
```

---

## 9. IP

IP는 네트워크 주소와 호스트 주소를 정의하고 네트워크의 논리적 관리를 담당한다.

```text
IP
→ 송신자 / 수신자 주소 지정
→ 네트워크 논리적 관리
```

---

## 10. Network Access 계층

물리적 케이블 또는 무선 통신과 연결하여 메시지를 전송한다.

- 물리적 연결
- 전기적 신호 변환
- Ethernet 등 사용

```text
Network Access
→ 물리적 네트워크 연결
→ 전기적 신호 전송
→ Ethernet
```

---

## 11. TCP/IP 4계층과 OSI 7계층 비교

| OSI 7계층 | TCP/IP 4계층 |
|---|---|
| Application | Application |
| Presentation | Application |
| Session | Application |
| Transport | Transport |
| Network | Internet |
| Data Link | Network Access |
| Physical | Network Access |

```text
OSI 7, 6, 5
→ TCP/IP Application

OSI 4
→ TCP/IP Transport

OSI 3
→ TCP/IP Internet

OSI 2, 1
→ TCP/IP Network Access
```

---

## 12. 패킷 스니핑에서 계층별 프로토콜

책의 Wireshark 예에서는 웹 통신이 다음과 같이 나타난다.

```text
Application
→ HTTP

Transport
→ TCP

Internet
→ IP

Network Access
→ Ethernet
```

---

## 13. 시험 직전 암기

```text
TCP/IP
→ DoD 모델
→ ARPANET
→ 4계층

Application
→ FTP / Telnet / SSH / HTTP / SMTP / SNMP

Transport
→ TCP / UDP

TCP
→ 연결지향
→ 신뢰성
→ ACK
→ Error Control

UDP
→ 비연결
→ 비신뢰성
→ 빠름

Internet
→ IP / ARP / RARP / ICMP

ARP
→ IP → MAC

RARP
→ MAC → IP

ICMP
→ 네트워크 오류 / 상태 점검

Network Access
→ Ethernet
→ 물리적 연결
→ 전기적 신호

OSI 7,6,5
→ Application

OSI 4
→ Transport

OSI 3
→ Internet

OSI 2,1
→ Network Access
```
