# Linux Account Management

네트워크관리사 2급 NOS 파트의 **리눅스 계정 관리** 내용을 정리한다.

---

## 1. useradd와 adduser

리눅스에서 새로운 사용자를 생성할 때는 `useradd` 또는 `adduser` 명령을 사용한다.

예:

```bash
useradd limbest
```

```text
useradd / adduser
→ 사용자 계정 생성
```

---

## 2. /etc/passwd

`/etc/passwd` 파일은 사용자 계정의 기본 정보를 저장한다.

책의 예시는 다음과 같다.

```text
root:x:0:0:root:/root:/bin/bash
```

각 필드는 콜론(`:`)으로 구분되며 총 7개이다.

| 번호 | 필드 | 설명 |
|---|---|---|
| 1 | Login Name | 사용자 계정 |
| 2 | Password | 사용자 암호가 들어갈 자리 |
| 3 | User ID | 사용자 ID |
| 4 | User Group ID | 사용자가 속한 그룹 ID |
| 5 | Comments | 사용자 설명 정보 |
| 6 | Home Directory | 사용자 홈 디렉토리 |
| 7 | Shell | 사용자가 기본으로 사용하는 Shell |

### root 계정

```text
root UID
→ 0

root GID
→ 0
```

### Password 필드

`/etc/passwd`의 두 번째 필드가 `x`로 표시되어 있으면 실제 패스워드는 `/etc/shadow`에 저장되어 있다는 의미이다.

```text
/etc/passwd
root:x:0:0:root:/root:/bin/bash
     ↑
     x

→ 실제 패스워드는 /etc/shadow에 저장
```

---

## 3. /etc/shadow

`/etc/shadow` 파일은 사용자 암호와 패스워드 관리 정보를 저장한다.

각 필드는 콜론(`:`)으로 구분되며 총 9개이다.

| 번호 | 필드 | 설명 |
|---|---|---|
| 1 | Login Name | 사용자 계정 |
| 2 | Encrypted | 암호화된 패스워드 |
| 3 | Last Changed | 마지막 패스워드 변경 날짜 |
| 4 | Minimum | 패스워드 변경 전 최소 사용 기간 |
| 5 | Maximum | 패스워드 변경 전 최대 사용 기간 |
| 6 | Warn | 패스워드 만료 전 경고 일 수 |
| 7 | Inactive | 로그인 접속 차단 일 수 |
| 8 | Expire | 로그인 사용을 금지하는 날짜 |
| 9 | Reserved | 사용되지 않는 필드 |

```text
/etc/shadow
→ 패스워드 관련 정보
→ 9개 필드
```

---

## 4. 패스워드 암호화 형식

책에서는 `/etc/shadow`의 암호화된 패스워드 형식을 다음과 같이 설명한다.

```text
$1$ → MD5
$5$ → SHA256
$6$ → SHA512
```

또한 `$`와 `$` 사이의 값은 Salt 값을 의미한다.

```text
$6$
→ SHA512
```

---

## 5. /etc/passwd와 /etc/shadow 비교

| 구분 | `/etc/passwd` | `/etc/shadow` |
|---|---|---|
| 주요 내용 | 사용자 기본 계정 정보 | 암호 및 패스워드 관리 정보 |
| 필드 수 | 7개 | 9개 |
| 실제 암호 | `x`로 표시 | 암호화된 형태로 저장 |
| 주요 정보 | UID, GID, 홈 디렉토리, Shell | 암호, 변경일, 만료 기간 등 |

---

## 6. 시험 직전 암기

```text
useradd / adduser
→ 사용자 생성

/etc/passwd
→ 사용자 기본 정보
→ 7개 필드

1 Login Name
2 Password
3 UID
4 GID
5 Comments
6 Home Directory
7 Shell

passwd 두 번째 필드가 x
→ 실제 암호는 /etc/shadow

root UID
→ 0

root GID
→ 0

/etc/shadow
→ 암호 및 패스워드 정책 정보
→ 9개 필드

1 Login Name
2 Encrypted
3 Last Changed
4 Minimum
5 Maximum
6 Warn
7 Inactive
8 Expire
9 Reserved

$1$
→ MD5

$5$
→ SHA256

$6$
→ SHA512
```
