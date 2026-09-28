# Telnet and SSH

네트워크관리사 2급 TCP/IP 파트의 **Telnet과 SSH** 내용을 정리한다.

---

## 1. Telnet

Telnet은 원격으로 서버에 로그인하여 작업할 때 사용하는 프로그램이다.

- TCP 프로토콜 사용
- 기본 포트 번호는 23번
- 원격 서버 접속 시 사용자 ID와 패스워드 입력
- ID와 패스워드가 맞으면 로그인 완료

```text
Telnet
→ 원격 로그인
→ TCP 사용
→ 기본 Port 23
```

---

## 2. services 파일

리눅스 시스템에서 사용하는 포트 번호는 `/etc/services` 파일에 등록되어 있다.

```text
/etc/services
→ 서비스별 포트 번호 확인
```

Telnet의 기본 포트 번호:

```text
23
```

책에서는 `/etc/services` 파일을 vi로 열어 Telnet의 포트 번호를 확인할 수 있다고 설명한다.

또한 23번 포트처럼 널리 알려진 포트 대신 보안을 위해 임의의 포트로 변경할 수도 있다.

---

## 3. Telnet의 보안 문제

Telnet은 통신 시 송수신되는 모든 데이터가 암호화되지 않은 **평문**으로 전송된다.

따라서 Sniffing을 통해 패킷을 캡처하면 통신 내용을 확인할 수 있다.

```text
Telnet
→ 평문 전송
→ 암호화 X
→ Sniffing 시 내용 확인 가능
```

이러한 문제 때문에 Telnet 대신 SSH를 많이 사용한다.

---

## 4. SSH

SSH는 송신 및 수신되는 모든 데이터를 암호화하여 전송하는 원격 접속 방식이다.

```text
SSH
→ 원격 접속
→ 송수신 데이터 암호화
```

책에서는 SSH 서비스를 실행하기 위해 다음 명령을 사용한다.

```bash
service ssh start
```

```text
service ssh start
→ SSH 서비스 실행
```

PuTTY 프로그램을 사용하여 SSH 연결을 수행할 수 있다.

---

## 5. SSH 암호화 확인

SSH 연결 후 Wireshark로 패킷을 확인하면 전송 데이터가 암호화된 상태로 보인다.

```text
Encrypted Packet
```

즉, 실제 통신 내용을 그대로 확인하기 어렵다.

```text
SSH
→ 데이터 암호화
→ Sniffing으로 내용 확인 어려움
```

---

## 6. Telnet과 SSH 비교

| 구분 | Telnet | SSH |
|---|---|---|
| 용도 | 원격 로그인 | 원격 로그인 |
| 전송 방식 | 평문 | 암호화 |
| 보안 | 낮음 | 높음 |
| 기본 포트 | 23 | 이번 교재 페이지에는 명시되지 않음 |
| Sniffing | 내용 확인 가능 | 내용 확인 어려움 |

---

## 7. 시험 직전 암기

```text
Telnet
→ 원격 서버 로그인
→ TCP 사용
→ Port 23
→ ID / Password 입력
→ 평문 전송
→ Sniffing에 취약

/etc/services
→ 서비스별 포트 번호 확인

SSH
→ 원격 접속
→ 송수신 데이터 암호화

service ssh start
→ SSH 서비스 실행

Telnet
→ 평문

SSH
→ 암호화
```
