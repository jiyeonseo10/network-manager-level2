# SAMBA

네트워크관리사 2급 NOS 파트의 **SAMBA** 내용을 정리한다.

---

## 1. SAMBA 개요

SAMBA는 리눅스 운영체제에서 Microsoft의 **NETBIOS 프로토콜**을 제공하여 윈도우 시스템 운영체제와 자원 및 프린터를 공유할 수 있도록 하는 프로그램이다.

```text
SAMBA
→ Linux ↔ Windows 자원 공유
→ NETBIOS 프로토콜 사용
```

---

## 2. SAMBA 특징

SAMBA의 특징은 다음과 같다.

- 인터넷 및 인트라넷에서 서버 파일 및 프린터를 공유할 수 있는 프리웨어(Freeware) 프로그램
- 공통 인터넷 파일 시스템인 **CIFS** 클라이언트, 서버 프로토콜
- 리눅스 RPM 패키지 설치 도구를 사용하여 설치
- TCP/UDP **137, 139 포트** 사용
- 설정 파일은 `/etc/samba/smb.conf` 및 `/etc/smb.conf`

```text
CIFS
→ 파일 공유 프로토콜

Port
→ 137
→ 139

설정 파일
→ /etc/samba/smb.conf
→ /etc/smb.conf
```

---

## 3. SAMBA 서버 시작 및 종료

SAMBA 서버를 실행하거나 정지할 때 다음 명령을 사용한다.

```text
samba start
→ SAMBA 서버 실행

samba stop
→ SAMBA 서버 정지
```

---

## 4. smbd

`smbd`는 SAMBA에서 **NETBIOS 프로토콜을 이용하여 자료를 전송**하는 기능을 담당한다.

```text
smbd
→ NETBIOS 프로토콜로 자료 전송
```

---

## 5. nmbd

`nmbd`는 SAMBA에서 **NETBIOS 프로토콜의 이름을 관리**하는 기능을 담당한다.

```text
nmbd
→ NETBIOS 이름 관리
```

---

## 6. smbd와 nmbd 비교

| 구분 | 기능 |
|---|---|
| `smbd` | NETBIOS 프로토콜로 자료 전송 |
| `nmbd` | NETBIOS 프로토콜의 이름 관리 |

```text
smbd
→ 자료 전송

nmbd
→ 이름 관리
```

---

## 7. 시험 직전 암기

```text
SAMBA
→ Linux와 Windows 자원 공유
→ NETBIOS 사용

특징
→ Freeware
→ CIFS 클라이언트 / 서버 프로토콜
→ RPM 패키지로 설치

Port
→ TCP/UDP 137
→ TCP/UDP 139

설정 파일
→ /etc/samba/smb.conf
→ /etc/smb.conf

samba start
→ 서버 실행

samba stop
→ 서버 정지

smbd
→ 자료 전송

nmbd
→ 이름 관리
```
