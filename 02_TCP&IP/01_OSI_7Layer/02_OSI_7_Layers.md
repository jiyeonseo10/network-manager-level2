# OSI 7 Layers

네트워크관리사 2급 TCP/IP 파트의 **OSI 7계층** 내용을 정리한다.

---

## 1. OSI 7계층 개요

OSI는 **Open System Interconnection**의 약자이다.

개방형 시스템의 효율적인 네트워크 이용을 위해 데이터 통신 기능을 계층으로 나누고, 각 계층에서 필요한 프로토콜을 규정한다.

국제표준화기구 ISO에서 개방형 시스템 간의 상호 정보 전송을 위해 제정한 표준안이다.

```text
OSI
→ Open System Interconnection
→ 통신 기능을 7개 계층으로 구분
→ 서로 다른 네트워크 간 통신 지원
```

---

## 2. OSI 7계층 목표

네트워크 형태에 차이가 발생하더라도 데이터 통신이 가능하도록 정보가 전달되는 Framework를 제공한다.

```text
Framework
→ 작업(Task)을 처리하기 위한 기본적인 틀
```

---

## 3. OSI 7계층 특징

- 개방형 시스템 간 상호 접속을 위한 표준화 방법 제시
- 계층별 정보 흐름을 최소화하여 각 계층의 독립성 향상
- 프로토콜 표준화를 통해 효율성과 생산성 향상

---

## 4. 캡슐화

상위 계층에서 하위 계층으로 내려가면서 각 계층의 정보를 헤더에 추가하는 과정을 **캡슐화**라고 한다.

```text
Application
↓
Presentation
↓
Session
↓
Transport
↓
Network
↓
Data Link
↓
Physical
```

하위 계층으로 내려갈 때마다 헤더가 추가되고, 수신 측에서는 반대로 올라가면서 헤더가 제거된다.

---

## 5. OSI 7계층 순서

```text
7. Application
6. Presentation
5. Session
4. Transport
3. Network
2. Data Link
1. Physical
```

---

## 6. Application 계층

사용자가 사용하는 프로그램이 있는 계층이다.

- 사용자 소프트웨어가 네트워크에 접근할 수 있도록 함
- 사용자에게 최종 서비스 제공
- 데이터 송신을 위한 Message 생성
- OSI 7계층의 최상위 계층

주요 프로토콜:

```text
FTP
SNMP
HTTP
Mail
Telnet
SMTP
```

```text
Application
→ 사용자 서비스
→ Message 생성
→ HTTP / FTP / SMTP / SNMP / Telnet
```

---

## 7. Presentation 계층

애플리케이션에서 전달된 메시지에 대한 코드화를 수행한다.

- 사전에 정해진 코드로 변환
- 메시지 압축
- 암호화
- 다른 컴퓨터가 이해할 수 있는 데이터 형태로 변환

주요 내용:

```text
압축
암호화
코드 변환
GIF
ASCII
EBCDIC
```

```text
Presentation
→ 변환
→ 압축
→ 암호화
```

---

## 8. Session 계층

송신자와 수신자 간 통신을 위해 동기화 신호를 주고받는다.

- 세션 연결
- 가상 연결 제공
- 동기화 수행
- Login / Logout 수행
- 통신 방식 결정

통신 방식:

```text
단순
반이중
전이중
```

```text
Session
→ 세션 연결
→ 동기화
→ 가상 연결
→ 통신 방식 결정
```

---

## 9. Transport 계층

송신자와 수신자 간 논리적 연결을 수행한다.

- End-to-End 연결 관리
- 가상 연결
- 에러 제어
- 데이터 흐름 제어
- 에러 탐지 및 재전송
- 다중화
- Segment 단위
- 신뢰도 및 품질 보장

주요 프로토콜:

```text
TCP
UDP
```

```text
Transport
→ End-to-End
→ TCP / UDP
→ Segment
→ 흐름 제어
→ 오류 탐지 및 교정
```

---

## 10. Network 계층

수신자의 IP 주소를 이용해 목적지까지의 경로를 결정한다.

- IP 주소 사용
- 경로 선택
- Routing
- Forwarding
- IPv4 / IPv6
- 네트워크 에러 확인에 ICMP 사용
- Datagram 단위

주요 프로토콜:

```text
IP
ICMP
RIP
OSPF
```

```text
Network
→ IP 주소
→ Routing
→ Forwarding
→ Router
```

---

## 11. Data Link 계층

네트워크 계층의 IP 정보를 이용하여 하드웨어 주소인 MAC 주소를 구한다.

- 물리 주소 결정
- MAC 주소 사용
- 에러 탐지 및 교정
- 흐름 제어
- Frame 단위 전송

주요 프로토콜 및 기술:

```text
ARQ
HDLC
Frame Relay
```

```text
Data Link
→ MAC 주소
→ Frame
→ 오류 제어
→ 흐름 제어
```

---

## 12. MAC 주소

MAC 주소는 물리적 하드웨어 주소이다.

```text
MAC
→ 48bit
```

구성:

```text
상위 24bit
→ 제조사 번호

하위 24bit
→ NIC 일련번호
```

Windows에서는 다음 명령으로 확인할 수 있다.

```bash
ipconfig /all
```

---

## 13. Physical 계층

물리적 선로를 통해 전기적 신호인 Bit로 데이터를 전송한다.

- Bit 단위 전송
- 전기적 신호
- 전압 구성
- 케이블
- 인터페이스

주요 매체:

```text
동축 케이블
광섬유
Twisted Pair Cable
```

```text
Physical
→ Bit
→ 전기적 신호
→ 물리적 전송 매체
```

---

## 14. OSI 계층별 단위 및 핵심

| 계층 | 핵심 기능 |
|---|---|
| Application | 사용자 서비스 |
| Presentation | 압축, 암호화, 코드 변환 |
| Session | 세션 연결, 동기화 |
| Transport | End-to-End, TCP/UDP, Segment |
| Network | IP, Routing |
| Data Link | MAC, Frame, 오류 제어 |
| Physical | Bit, 전기 신호, 케이블 |

---

## 15. End-to-End와 Point-to-Point

```text
End-to-End
→ 7~4계층
→ 송신자와 수신자 간 에러 Control

Point-to-Point
→ 3~1계층
→ 각 구간에 대한 에러 Control
```

---

## 16. Physical 계층 장비

### Cable

책에 나온 케이블:

```text
Twisted Pair Cable
Coaxial Cable
Fiber-Optic Cable
```

### Repeater

네트워크 구간의 케이블 전기적 신호를 재생하고 증폭한다.

```text
Repeater
→ 전기적 신호 재생
→ 신호 증폭
```

---

## 17. Data Link 계층 장비

### Bridge

- 서로 다른 LAN Segment 연결
- MAC 주소 기반 필터링
- 대역폭 사용 효율 향상
- MAC 기반으로 동작

```text
Bridge
→ LAN Segment 연결
→ MAC 기반
```

### Switch

- 목적지 MAC 주소를 확인
- 지정된 포트로 데이터 전송
- Repeater와 Bridge 기능 결합
- Data Link 계층에서 동작

```text
Switch
→ MAC 주소
→ 지정 포트로 전송
```

---

## 18. Network 계층 장비

### Router

- 패킷을 받아 경로 설정
- 패킷 전달
- 네트워크 주소까지 참조
- IP 주소를 이용하여 목적지 네트워크로 전달
- Broadcasting 차단

```text
Router
→ Network 계층
→ IP 주소
→ 경로 설정
→ 패킷 전달
```

---

## 19. Application 계층 장비

### Gateway

서로 다른 네트워크망을 연결한다.

책의 예:

```text
PSTN
Internet
Wireless Network
```

```text
Gateway
→ 서로 다른 네트워크망 연결
```

---

## 20. 계층과 장비 비교

| 계층 | 장비 |
|---|---|
| Physical | Cable, Repeater |
| Data Link | Bridge, Switch |
| Network | Router |
| Application | Gateway |

---

## 21. 계층과 주소 비교

```text
Network
→ IP 주소

Data Link
→ MAC 주소

Physical
→ Bit / 전기 신호
```

---

## 22. 시험 직전 암기

```text
7 Application
→ 사용자 서비스
→ HTTP / FTP / SMTP / SNMP / Telnet
→ Gateway

6 Presentation
→ 변환
→ 압축
→ 암호화
→ ASCII / GIF / EBCDIC

5 Session
→ 세션 연결
→ 동기화
→ Login / Logout
→ 단순 / 반이중 / 전이중

4 Transport
→ End-to-End
→ TCP / UDP
→ Segment
→ 오류 제어 / 흐름 제어

3 Network
→ IP
→ Routing
→ Forwarding
→ ICMP
→ RIP / OSPF
→ Router

2 Data Link
→ MAC
→ Frame
→ 오류 제어 / 흐름 제어
→ HDLC / Frame Relay
→ Bridge / Switch

1 Physical
→ Bit
→ 전기 신호
→ Cable
→ Repeater

MAC
→ 48bit
→ 상위 24bit 제조사
→ 하위 24bit NIC 일련번호

End-to-End
→ 7~4계층

Point-to-Point
→ 3~1계층
```
