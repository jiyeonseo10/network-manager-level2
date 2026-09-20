# NetBIOS / SMB / CIFS

네트워크관리사 2급 NOS 파트의 **NetBIOS, SMB, CIFS 프로토콜**을 정리한다.

---

## 1. NetBIOS 개요

**NetBIOS(Network Basic Input/Output System)** 는 서로 다른 두 대의 컴퓨터가 네트워크를 통해 데이터를 교환할 수 있도록 하는 프로토콜이다.

- IBM에서 개발
- Microsoft에서 채택
- 윈도우에서 파일 및 프린터 공유에 사용
- NetBIOS 이름을 IP 주소로 변환
- IP 주소를 NetBIOS 이름으로 변환
- 프로그램이 특정 컴퓨터와 통신할 수 있도록 지원

---

## 2. NetBIOS 통신 포트

| 포트 | 서비스 | 기능 |
|---|---|---|
| `135/TCP` | RPC/DCE Locator Service | 원격 컴퓨터에 RPC(Remote Procedure Call) 연결 |
| `137/UDP` | NetBIOS Name Construction Service | 컴퓨터 이름 및 작업 그룹 정보 확인 |
| `138/UDP` | NetBIOS Datagram Service | NetBIOS 기반 호스트 간 데이터 교환 |
| `139/TCP` | NetBIOS Session Service | NetBIOS 기반 호스트 간 세션 유지 또는 종료 |
| `445/TCP, UDP` | Direct HOST | 윈도우 계열 컴퓨터에서 자원 및 프린터 공유 |

### 포트 암기

```text
135 → RPC
137 → 이름
138 → Datagram
139 → Session
445 → 자원 및 프린터 공유
```

---

## 3. NetBIOS 보안

NetBIOS 프로토콜은 랜섬웨어 및 무작위 공격이 발생할 수 있다.

NetBIOS TCP/IP 바인딩이 활성화된 경우 공격에 악용될 수 있으므로 책에서는 다음과 같이 설정한다.

```text
ncpa.cpl
→ TCP/IPv4 속성
→ WINS
→ NetBIOS over TCP/IP 사용 안 함
```

---

## 4. SMB

**SMB(Server Message Block)** 는 윈도우에서 다른 시스템의 파일 시스템 및 프린터와 같은 자원을 공유할 수 있도록 개발된 프로토콜이다.

- 파일 시스템 공유
- 프린터 공유
- 네트워크 자원 공유
- SMB를 활용하여 WannaCry 랜섬웨어 공격 가능

---

## 5. Samba

**Samba**는 리눅스(유닉스) 환경에서 **SMB/CIFS 프로토콜을 제공하는 오픈 소스 소프트웨어**이다.

```text
Samba
→ Linux / Unix 환경
→ SMB / CIFS 제공
→ 오픈 소스
```

---

## 6. SMB 취약점

| 취약점 | 설명 | 공격 |
|---|---|---|
| EternalBlue(MS17-010) | 버퍼 오버플로우 기반 원격 코드 실행 | WannaCry 및 NetPetya 랜섬웨어 |
| SMB Replay Attack | 인증 토큰을 복사하여 권한 탈취 | 권한 상승 공격 |
| Null Session | 인증 없이 IPC$ 접속 허용 | 시스템 정보 수집 |
| SMBGhost | SMBv3 압축 기능에서 발생 | 원격 시스템 장악 공격 |

### EternalBlue

```text
EternalBlue
→ MS17-010
→ 버퍼 오버플로우
→ 원격 코드 실행
→ WannaCry / NetPetya
```

### SMB Replay Attack

```text
SMB Replay Attack
→ 인증 토큰 복사
→ 권한 탈취
→ 권한 상승 공격
```

### Null Session

```text
Null Session
→ 인증 없이 IPC$ 접속
→ 시스템 정보 수집
```

### SMBGhost

```text
SMBGhost
→ SMBv3 압축 기능
→ 원격 시스템 장악 공격
```

---

## 7. CIFS

**CIFS(Common Internet File System)** 는 네트워크를 위한 **SMB 파일 공유 프로토콜의 확장 버전**이다.

- SMB 파일 공유 프로토콜의 확장 버전
- 윈도우 환경 지원
- 유닉스 환경 지원

### 핵심

```text
CIFS
→ SMB의 확장 버전
→ Windows + Unix 환경 지원
```

---

## 8. 시험 직전 암기

```text
NetBIOS
→ 네트워크를 통한 데이터 교환
→ 파일 및 프린터 공유
→ NetBIOS 이름 ↔ IP 주소 변환

135/TCP
→ RPC

137/UDP
→ 이름 / 작업 그룹 정보

138/UDP
→ Datagram / 데이터 교환

139/TCP
→ Session 유지 / 종료

445/TCP, UDP
→ 자원 및 프린터 공유

SMB
→ 파일 / 프린터 / 자원 공유

Samba
→ Linux / Unix에서 SMB/CIFS 제공

EternalBlue
→ MS17-010
→ WannaCry / NetPetya

SMB Replay Attack
→ 인증 토큰 복사
→ 권한 탈취

Null Session
→ 인증 없이 IPC$
→ 시스템 정보 수집

SMBGhost
→ SMBv3 압축 기능
→ 원격 시스템 장악

CIFS
→ SMB 파일 공유 프로토콜의 확장 버전
→ Windows + Unix 지원
```
