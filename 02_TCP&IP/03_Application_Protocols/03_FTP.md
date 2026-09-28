# FTP

네트워크관리사 2급 TCP/IP 파트의 **FTP** 내용을 정리한다.

---

## 1. FTP 개요

FTP는 **File Transfer Protocol**의 약자이다.

서버에 파일을 업로드하거나 다운로드하기 위한 인터넷 표준 프로토콜이다.

- TCP 프로토콜 사용
- FTP 클라이언트 프로그램을 이용하여 접속
- 접속 후 사용자 ID와 Password로 인증

```text
FTP
→ File Transfer Protocol
→ 파일 업로드 / 다운로드
→ TCP 사용
→ ID / Password 인증
```

---

## 2. FTP 특징

FTP는 **두 개의 포트**를 사용한다.

```text
명령 채널
→ FTP 명령 전달

데이터 전송 채널
→ 실제 파일 송수신
```

명령 포트는 고정되어 있다.

```text
Port 21
→ 명령 포트
```

데이터 포트는 전송 모드에 따라 달라진다.

---

## 3. FTP 명령 채널과 데이터 채널

FTP의 명령 채널과 데이터 전송 채널은 서로 독립적으로 동작한다.

명령 채널에서는 다음과 같은 명령을 전달한다.

```text
USER
PASS
GET
```

실제 파일은 데이터 전송 채널을 통해 전달한다.

```text
명령 채널
→ USER / PASS / GET 등

데이터 채널
→ 실제 파일 업로드 / 다운로드
```

---

## 4. FTP 로그인 과정

FTP 클라이언트는 FTP 서버에 접속한 후 USER와 PASS 명령을 사용하여 인증한다.

```text
FTP Client
→ TCP 3 Way Handshaking
→ FTP Server 연결
```

서버 응답 코드:

```text
220
→ FTP 서버 접속

331
→ Password 입력 필요

230
→ 로그인 성공
```

로그인 과정:

```text
서버 접속
→ 220

USER 전송
→ 331

PASS 전송
→ 230
```

---

## 5. Active Mode

Active Mode에서는 FTP 서버의 데이터 포트로 **20번**을 사용한다.

```text
Active Mode

Port 21
→ Command

Port 20
→ Data
```

책의 설명:

```text
FTP Client
→ FTP Server 21번 포트에 접속

FTP Server
→ 20번 포트를 이용하여 데이터 전송
```

```text
Active
→ Server Data Port = 20
```

---

## 6. Passive Mode

Passive Mode에서도 명령 연결은 21번 포트를 사용한다.

하지만 데이터 송수신을 위해 FTP 서버가 **1024~65535 범위의 Random Port**를 선택한다.

```text
Passive Mode

Port 21
→ Command

Random Port
→ Data
```

책 기준:

```text
FTP Client
→ FTP Server 21번 포트에 접속

FTP Server
→ 1024~65535 범위 Random Port 선택

FTP Client
→ 데이터 송수신 시 Random Port 사용
```

```text
Passive
→ 서버가 데이터 포트 결정
→ Random Port 사용
```

---

## 7. Active Mode와 Passive Mode 비교

| 구분 | Active Mode | Passive Mode |
|---|---|---|
| 명령 포트 | 21 | 21 |
| 데이터 포트 | 20 | Random Port |
| 데이터 포트 결정 | 고정 | 서버가 결정 |
| Random Port | 사용하지 않음 | 1024~65535 |

```text
Active
→ 21 Command
→ 20 Data

Passive
→ 21 Command
→ Random Data Port
```

---

## 8. FTP의 종류

책에서는 FTP, TFTP, SFTP를 비교한다.

### FTP

- ID 및 Password 인증
- TCP 사용
- 사용자 데이터 송수신

```text
FTP
→ 인증 O
→ TCP
```

### TFTP

- 인증 과정 없음
- UDP 기반
- 데이터를 빠르게 송수신
- 69번 포트 사용

```text
TFTP
→ 인증 X
→ UDP
→ Port 69
```

### SFTP

전송 구간에서 암호화 기법을 사용하여 기밀성을 제공한다.

```text
SFTP
→ 암호화
→ 기밀성 제공
```

---

## 9. FTP 로그

FTP 서비스의 로그 파일은 `xferlog`이다.

```text
xferlog
→ FTP 서비스 로그 파일
```

FTP 실행 시 `-l` 옵션을 사용하면 xferlog 파일에 로그를 기록한다.

```text
-l
→ FTP 로그 기록
```

---

## 10. xferlog 파일 구조

책에서 제시한 xferlog 정보:

- 접근 날짜 및 시간
- 접속 IP
- 전송 파일 Size
- 전송 파일
- 파일 종류
- 행위
- 파일 동작
- 사용자 접근 방식
- 로그인 ID
- 인증 방법
- 전송 상태

주요 코드:

```text
파일 종류

b
→ Binary

a
→ ASCII
```

```text
행위

_
→ 아무 일도 수행하지 않음
```

```text
파일 동작

o
→ 파일을 받았음
```

```text
사용자 접근 방식

r
→ 인증된 사용자
```

```text
전송 상태

c
→ 전송 성공
```

---

## 11. 시험 직전 암기

```text
FTP
→ File Transfer Protocol
→ TCP
→ 파일 업로드 / 다운로드
→ ID / Password 인증

명령 포트
→ 21

Active Mode
→ Command 21
→ Data 20

Passive Mode
→ Command 21
→ Data Random Port
→ 1024~65535

FTP 응답 코드

220
→ 서버 접속

331
→ Password 필요

230
→ 로그인 성공

FTP
→ TCP
→ 인증 O

TFTP
→ UDP
→ 인증 X
→ Port 69

SFTP
→ 암호화
→ 기밀성

xferlog
→ FTP 로그 파일

-l
→ FTP 로그 기록
```
