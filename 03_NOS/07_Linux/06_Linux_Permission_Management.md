# Linux Permission Management

네트워크관리사 2급 NOS 파트의 **리눅스 권한 관리** 내용을 정리한다.

---

## 1. Linux 권한 구조

리눅스의 권한은 다음 세 대상으로 구분된다.

- 소유자(User)
- 그룹(Group)
- 다른 사용자(Other)

권한은 다음과 같이 표시한다.

```text
r → 읽기(Read)
w → 쓰기(Write)
x → 실행(Execute)
```

숫자 값은 다음과 같다.

```text
r = 4
w = 2
x = 1
```

예:

```text
rwx = 4 + 2 + 1 = 7
rw- = 4 + 2 = 6
r-x = 4 + 1 = 5
r-- = 4
```

---

## 2. umask

`umask`는 파일이나 디렉토리를 생성할 때 적용되는 기본 권한과 관련된 값이다.

책의 예에서는 `umask` 값이 `022`일 때 다음과 같이 계산한다.

```text
777 - 022 = 755
```

`755`의 권한은 다음과 같다.

```text
소유자 → 7 → rwx
그룹   → 5 → r-x
기타   → 5 → r-x
```

현재 `umask` 값을 확인한다.

```bash
umask
```

`umask` 값을 변경한다.

```bash
umask 0000
```

```text
umask
→ 기본 권한 관련 값
→ 현재 값 확인 가능
→ 값 변경 가능
```

---

## 3. chmod

`chmod`는 파일이나 디렉토리의 권한을 변경하는 명령어이다.

### 권한 대상

```text
u → user
g → group
o → other
a → all
```

### 권한 변경 기호

```text
+ → 권한 추가
- → 권한 삭제
= → 지정한 권한으로 변경
```

### 권한

```text
r → 읽기
w → 쓰기
x → 실행
```

---

## 4. 숫자를 이용한 chmod

각 권한은 숫자로 표현할 수 있다.

```text
r = 4
w = 2
x = 1
```

예:

```bash
chmod 771 abc
```

```text
소유자 → 7 → rwx
그룹   → 7 → rwx
기타   → 1 → --x
```

또 다른 예:

```bash
chmod 764 limbest.txt
```

```text
소유자 → 7 → rwx
그룹   → 6 → rw-
기타   → 4 → r--
```

따라서:

```text
764
→ rwx rw- r--
```

---

## 5. 문자를 이용한 chmod

숫자 대신 문자 방식으로도 권한을 변경할 수 있다.

다른 사용자의 모든 권한을 삭제한다.

```bash
chmod o-rwx limbest.txt
```

다른 사용자에게 모든 권한을 추가한다.

```bash
chmod o+rwx limbest.txt
```

```text
o-rwx
→ other의 읽기 / 쓰기 / 실행 권한 삭제

o+rwx
→ other에게 읽기 / 쓰기 / 실행 권한 추가
```

책에서는 setuid 권한을 줄 때 `s`를 추가한다고 설명한다.

---

## 6. chown

`chown(Change Owner)`은 파일이나 디렉토리의 소유자와 그룹을 변경하는 명령어이다.

책의 형식은 다음과 같다.

```text
chown [option] [UID:GID] [디렉토리/파일명]
```

주요 옵션:

| 옵션 | 설명 |
|---|---|
| `-R` | 하위 디렉토리와 파일 모두 적용 |
| `-c` | 권한 변경 파일 내용 출력 |

예:

```bash
chown limbest limbest.txt
```

파일의 소유자를 다음과 같이 변경한다.

```text
root
→ limbest
```

```text
chown
→ 소유자 / 그룹 변경
```

---

## 7. chgrp

`chgrp`는 파일이나 디렉토리의 소유 그룹을 변경하는 명령어이다.

형식:

```text
chgrp [옵션] [그룹] 파일
```

주요 옵션:

| 옵션 | 설명 |
|---|---|
| `-c` | 실제 변경된 경우 표시 |
| `-h` | 심볼릭 링크 자체의 그룹 변경 |
| `-f` | 그룹 변경 실패 시 오류 메시지를 표시하지 않음 |
| `-v` | 작업 진행 상태 설명 |
| `-R` | 하위 모든 파일을 지정한 그룹으로 변경 |

예:

```bash
chgrp limbest limbest.txt
```

```text
limbest.txt
→ 소유 그룹을 limbest로 변경
```

---

## 8. 명령어 비교

| 명령어 | 역할 |
|---|---|
| `umask` | 기본 권한 관련 값 확인 및 변경 |
| `chmod` | 파일/디렉토리 권한 변경 |
| `chown` | 소유자 및 그룹 변경 |
| `chgrp` | 소유 그룹 변경 |

---

## 9. 시험 직전 암기

```text
r = 4
w = 2
x = 1

u = user
g = group
o = other
a = all

+
→ 권한 추가

-
→ 권한 삭제

=
→ 지정 권한으로 변경

chmod
→ 파일 / 디렉토리 권한 변경

chmod 764
→ rwx rw- r--

umask
→ 기본 권한 관련 값

책 예시
→ umask 022
→ 777 - 022 = 755

chown
→ 소유자 / 그룹 변경

chown -R
→ 하위 디렉토리와 파일 모두 적용

chown -c
→ 변경 내용 출력

chgrp
→ 그룹 변경

chgrp -h
→ 심볼릭 링크 자체의 그룹 변경

chgrp -f
→ 오류 메시지 표시 안 함

chgrp -v
→ 작업 진행 상태 설명

chgrp -R
→ 하위 모든 파일에 적용
```
