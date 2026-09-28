# HTTP

네트워크관리사 2급 TCP/IP 파트의 **HTTP** 내용을 정리한다.

---

## 1. HTTP 개요

HTTP는 **Hyper Text Transfer Protocol**의 약자이다.

웹 브라우저와 웹 서버 사이에서 메시지를 송수신하기 위해 사용하는 프로토콜이다.

책에서는 HTTP를 W3C 표준 프로토콜이며 개방형 프로토콜(Open Protocol)이라고 설명한다.

```text
HTTP
→ Hyper Text Transfer Protocol
→ Web Browser ↔ Web Server
→ W3C 표준 프로토콜
→ Open Protocol
```

HTTP는 송신과 수신 시 TCP 프로토콜을 사용한다.

```text
HTTP
→ TCP 사용
```

HTTP의 기본 포트 번호는 80번이다.

```text
HTTP
→ Port 80
```

---

## 2. HTTP의 통신 방식

HTTP는 TCP를 사용하여 신뢰성 있게 데이터를 송수신한다.

하지만 TCP 연결을 계속 유지하는 것이 아니라 요청이 있을 때 연결하고 메시지를 처리한 후 연결을 종료하는 방식이다.

이러한 특성을 **State-less 프로토콜**이라고 한다.

```text
HTTP
→ Request
→ Response
→ 처리 후 연결 종료
→ Stateless
```

---

## 3. HTTP Request / Response

HTTP는 기본적으로 Request와 Response 구조를 가진다.

```text
Client
→ Request
→ Server

Server
→ Response
→ Client
```

---

## 4. HTTP 구조

HTTP 메시지는 Header와 Body로 구분된다.

Header와 Body 사이에는 개행문자가 존재한다.

책에 나온 구분 문자열:

```text
\r\n\r\n
```

구조:

```text
HTTP Message

Header
\r\n\r\n
Body
```

---

## 5. HTTP Request Method

책에 나온 HTTP 요청 방식은 다음과 같다.

```text
GET
POST
HEAD
PUT
DELETE
TRACE
OPTION
CONNECT
```

---

## 6. GET

GET은 URL에 입력 파라미터를 포함하여 요청하는 방식이다.

- 리소스 위치를 URL로 표시
- Request Body 없음
- 서버에 전달할 데이터를 URL에 포함
- 전송 가능한 데이터 양 제한 있음

예:

```text
login.php?userid=limbest&password=test
```

```text
GET
→ URL에 데이터 포함
→ Request Body 없음
→ 데이터 전송량 제한 있음
```

---

## 7. POST

POST는 요청 파라미터를 HTTP Body에 넣어 전송한다.

- Request Body에 입력값 전송
- 서버에 전달할 데이터를 Request Body에 포함
- 데이터 전송량 제한 없음

```text
POST
→ 데이터를 Body에 포함
→ 데이터 전송량 제한 없음
```

---

## 8. GET과 POST 비교

| 구분 | GET | POST |
|---|---|---|
| 데이터 위치 | URL | Request Body |
| Request Body | 없음 | 있음 |
| 데이터 전송량 | 제한 있음 | 제한 없음 |

```text
GET
→ URL

POST
→ Body
```

---

## 9. HEAD

HEAD는 서버의 정보를 확인하기 위해 사용한다.

GET과 비슷하지만 Response Body는 없고 Response Code와 Header만 응답한다.

```text
HEAD
→ 서버 정보 확인
→ Response Body 없음
→ Header만 응답
```

---

## 10. PUT

PUT은 요청된 자원을 수정하기 위해 사용한다.

메시지 Body의 데이터를 지정된 URL 이름에 저장한다.

```text
PUT
→ 자원 수정
→ Body 데이터를 지정 URL에 저장
```

---

## 11. DELETE

DELETE는 요청된 자원을 서버에서 삭제하기 위해 사용한다.

```text
DELETE
→ 자원 삭제
```

---

## 12. TRACE

TRACE는 요청 메시지가 최종 수신되는 경로를 기록하기 위한 용도로 사용한다.

책에서는 Loopback 메시지를 호출하기 위한 테스트용으로 설명한다.

```text
TRACE
→ Loopback
→ 테스트
```

---

## 13. OPTION

OPTION은 웹 서버에서 지원하는 메서드를 확인하기 위해 사용한다.

```text
OPTION
→ 서버가 지원하는 Method 확인
```

---

## 14. CONNECT

CONNECT는 Proxy 기능을 사용할 때 사용한다.

```text
CONNECT
→ Proxy 기능
```

---

## 15. HTTP 주요 특징

```text
HTTP
→ Hyper Text Transfer Protocol
→ Web Browser ↔ Web Server
→ TCP
→ Port 80
→ Request / Response
→ Stateless
```

---

## 16. 시험 직전 암기

```text
HTTP
→ Hyper Text Transfer Protocol
→ Web Browser ↔ Web Server
→ TCP 사용
→ Port 80
→ Request / Response
→ Stateless

HTTP 구조
→ Header
→ \r\n\r\n
→ Body

GET
→ URL에 데이터 포함
→ Request Body 없음
→ 데이터 양 제한 있음

POST
→ Request Body에 데이터 포함
→ 데이터 전송량 제한 없음

HEAD
→ 서버 정보 확인
→ Response Body 없음
→ Header만 응답

PUT
→ 자원 수정

DELETE
→ 자원 삭제

TRACE
→ Loopback / 테스트

OPTION
→ 지원 Method 확인

CONNECT
→ Proxy 기능
```
