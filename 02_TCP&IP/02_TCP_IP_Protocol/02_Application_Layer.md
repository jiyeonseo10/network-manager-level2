# Application Layer

네트워크관리사 2급 TCP/IP 파트의 **애플리케이션 계층(Application Layer)** 내용을 정리한다.

---

## 1. 애플리케이션 계층 개요

애플리케이션 계층은 일반 사용자가 사용하는 프로그램이 있는 계층이다.

사용자는 프로그램을 이용하여 통신하며, 응용 프로그램은 프로토콜을 이용하여 다양한 서비스를 제공한다.

예:

- 전자우편
- FTP 파일 전송
- HTTP 웹
- VoIP 전화
- 동영상 학습 프로그램
- 카카오톡

```text
Application Layer
→ 사용자가 사용하는 프로그램이 있는 계층
→ 응용 프로그램을 통해 통신
→ 다양한 서비스 제공
```

---

## 2. 애플리케이션 계층 역할

책 기준 역할:

- 사용자 인터페이스 설계
- 상대편 응용 계층과 연결
- 에러 제어
- 일관성 제어
- 파일 전송 방법 처리
- 프린터 공유 방법 처리
- 전자우편 전송 방법 처리

```text
Application Layer
→ 사용자 인터페이스
→ 상대 응용 계층과 연결
→ 에러 / 일관성 제어
→ 응용 서비스 처리
```

---

## 3. FTP

FTP는 **File Transfer Protocol**이다.

- 파일 업로드
- 파일 다운로드
- 파일 전송을 위한 인터넷 표준
- 제어 접속과 데이터 접속을 위해 분리된 포트 사용

```text
FTP
→ File Transfer Protocol
→ 파일 업로드 / 다운로드
```

---

## 4. DNS

DNS는 책에서 **Domain Name Server**로 설명한다.

DNS Query를 사용하여 URL을 DNS Server에 전달하고, 해당 URL에 매핑되는 IP 주소를 제공한다.

```text
DNS
→ URL을 IP 주소로 변환
→ DNS Query 사용
```

---

## 5. HTTP

HTTP는 **Hyper Text Transfer Protocol**이다.

웹 브라우저와 웹 서버 사이에서 웹 페이지의 Request와 Response를 처리한다.

```text
HTTP
→ Web Browser ↔ Web Server
→ Request / Response
```

---

## 6. Telnet

Telnet은 지역적으로 떨어져 있는 컴퓨터에 로그인하여 사용하는 서비스이다.

```text
Telnet
→ 원격 로그인
```

---

## 7. SMTP

SMTP는 **Simple Mail Transfer Protocol**이다.

- 인터넷 전자우편 전송
- RFC 821
- Store and Forward 방식 사용
- 책에서는 암호화 및 인증 기능 없이 사용자의 이메일을 전송한다고 설명

```text
SMTP
→ 전자우편 전송
→ Store and Forward
```

---

## 8. SNMP

SNMP는 **Simple Network Management Protocol**이다.

네트워크 트래픽과 세션 등 네트워크 상태를 모니터링하고 정보를 전달할 때 사용한다.

```text
SNMP
→ 네트워크 관리
→ 트래픽 / 세션 / 상태 모니터링
```

---

## 9. 시험 직전 암기

```text
Application Layer
→ 사용자가 사용하는 프로그램 계층

FTP
→ 파일 전송

DNS
→ URL → IP 주소

HTTP
→ 웹 Request / Response

Telnet
→ 원격 로그인

SMTP
→ 전자우편 전송
→ Store and Forward

SNMP
→ 네트워크 상태 / 트래픽 모니터링
```
