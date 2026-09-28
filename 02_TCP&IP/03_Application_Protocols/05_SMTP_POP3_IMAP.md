# SMTP / POP3 / IMAP

네트워크관리사 2급 TCP/IP 파트의 **SMTP, POP3, IMAP** 내용을 정리한다.

---

## 1. SMTP 개요

SMTP는 **Simple Mail Transfer Protocol**의 약자이다.

인터넷 전자우편의 표준 프로토콜이며, 책에서는 **RFC 821**에 명시되어 있다고 설명한다.

```text
SMTP
→ Simple Mail Transfer Protocol
→ 전자우편 전송 프로토콜
→ RFC 821
```

---

## 2. Store-and-Forward 방식

SMTP는 **Store-and-Forward 방식**으로 메시지를 전달한다.

```text
송신자 메일
→ 저장(Store)
→ 전달(Forward)
→ 수신자 메일
```

즉, 메일을 저장한 뒤 다음 메일 서버로 전달하는 방식이다.

---

## 3. SMTP 기본 동작

SMTP는 전자우편을 전송하는 프로토콜이다.

메일 서버는 다음과 같이 동작한다.

- 수신자의 전자우편 주소 분석
- 최단 경로를 찾음
- 근접한 메일 서버로 전달
- 최종 수신자 측 메일 서버까지 계속 중계

```text
SMTP
→ 수신자 주소 분석
→ 최단 경로 탐색
→ 메일 서버 간 중계
→ 최종 서버 도착
```

---

## 4. SMTP 구성 요소

### MTA

MTA는 **Mail Transfer Agent**이다.

```text
MTA
→ 메일을 전송하는 서버
```

---

### MDA

MDA는 **Mail Delivery Agent**이다.

```text
MDA
→ 수신 측 우체부 역할
→ MTA가 받은 메일을 사용자에게 전달
```

---

### MUA

MUA는 **Mail User Agent**이다.

```text
MUA
→ 사용자가 사용하는 클라이언트 애플리케이션
```

---

## 5. SMTP 구성 요소 비교

| 구성 요소 | 역할 |
|---|---|
| MTA | 메일 전송 서버 |
| MDA | 받은 메일을 사용자에게 전달 |
| MUA | 사용자가 사용하는 메일 클라이언트 |

```text
MTA
→ 서버 간 메일 전송

MDA
→ 사용자에게 메일 전달

MUA
→ 사용자가 사용하는 프로그램
```

---

## 6. POP3

POP3는 메일 서버에 접속하여 저장된 메일을 내려받는 프로토콜이다.

책 기준:

- TCP 110번 사용
- 저장된 메일을 내려받음
- 메시지를 읽은 후 서버에서 해당 메일 삭제

```text
POP3
→ TCP 110
→ 메일 다운로드
→ 읽은 후 서버에서 삭제
```

---

## 7. IMAP / IMAP3

IMAP은 POP3와 달리 메일을 내려받아도 메일 서버에 원본을 계속 저장한다.

책 기준:

```text
IMAP
→ Port 143
→ 메일 다운로드
→ 서버에 원본 계속 저장
```

---

## 8. POP3와 IMAP 비교

| 구분 | POP3 | IMAP |
|---|---|---|
| 포트 | TCP 110 | 143 |
| 메일 다운로드 | 가능 | 가능 |
| 서버 원본 | 읽은 후 삭제 | 계속 저장 |

```text
POP3
→ 다운로드 후 서버에서 삭제

IMAP
→ 서버에 원본 유지
```

---

## 9. 시험 직전 암기

```text
SMTP
→ Simple Mail Transfer Protocol
→ 전자우편 전송
→ RFC 821
→ Store-and-Forward

MTA
→ 메일 전송 서버

MDA
→ 받은 메일을 사용자에게 전달

MUA
→ 사용자가 쓰는 메일 클라이언트

POP3
→ TCP 110
→ 메일 다운로드
→ 읽은 후 서버에서 삭제

IMAP
→ Port 143
→ 메일 다운로드
→ 서버에 원본 유지
```
