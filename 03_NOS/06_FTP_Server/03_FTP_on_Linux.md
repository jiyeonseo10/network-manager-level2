# FTP on Linux

네트워크관리사 2급 NOS 파트의 **리눅스에서 FTP 사용하는 방법**을 정리한다.

---

## 1. 리눅스에서 FTP 서버 접속

리눅스에서 Windows FTP 서버로 접속하려면 FTP 프로그램을 실행하고 서버의 IP 주소를 입력한다.

책의 예시는 다음과 같다.

```bash
ftp 210.221.118.221
```

FTP 서버에 접속하면 사용자 ID와 패스워드를 입력한다.

```text
Linux
→ ftp 서버IP
→ 사용자 ID 입력
→ 패스워드 입력
→ FTP 서버 로그인
```

---

## 2. FTP 현재 세션

리눅스에서 Windows FTP 서버에 로그인하면 IIS 관리자에서 **FTP 현재 세션**을 통해 현재 연결된 FTP 세션 정보를 확인할 수 있다.

이를 통해 FTP 서버에 접속한 클라이언트를 확인할 수 있다.

```text
FTP 현재 세션
→ 현재 접속 중인 FTP 클라이언트 확인
```

---

## 3. netstat를 이용한 FTP 연결 확인

책에서는 `netstat` 명령어를 이용하여 FTP 연결 상태를 확인한다.

```bash
netstat
```

연결 상태에 `ESTABLISHED`가 표시되면 TCP 연결이 정상적으로 확립된 상태이다.

```text
netstat
→ FTP 연결 상태 확인

ESTABLISHED
→ TCP 연결 확립
```

---

## 4. 시험 직전 암기

```text
Linux에서 FTP 접속
→ ftp 서버IP

FTP 로그인
→ 사용자 ID
→ 패스워드

Windows FTP 서버
→ FTP 현재 세션
→ 접속 클라이언트 확인

netstat
→ FTP 연결 상태 확인

ESTABLISHED
→ TCP 연결이 확립된 상태
```
