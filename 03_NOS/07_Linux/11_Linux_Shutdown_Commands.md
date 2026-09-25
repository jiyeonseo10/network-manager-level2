# Linux Shutdown Commands

네트워크관리사 2급 NOS 파트의 **리눅스 종료 및 재부팅 명령어**를 정리한다.

---

## 1. shutdown

`shutdown`은 리눅스 시스템을 정지하기 위한 명령어이다.

### shutdown 옵션

| 옵션 | 설명 |
|---|---|
| `-r` | 재부팅 수행 |
| `-h` | shutdown 완료 후 시스템 종료 |
| `-c` | 진행 중인 shutdown 취소 |
| `-k` | 경고 메시지만 출력하고 실제 shutdown은 수행하지 않음 |
| `-f` | fsck를 실행하지 않고 재부팅 |
| `-n` | init을 호출하지 않고 shutdown 실행 |
| `-t sec` | 지정한 시간에 재기동 |
| `-v` | 상세 정보 출력 |

예:

```bash
shutdown -h 5
```

```text
→ 5분 후 시스템 종료
```

```text
shutdown -r
→ 재부팅

shutdown -h
→ 시스템 종료

shutdown -c
→ 진행 중인 shutdown 취소

shutdown -k
→ 경고 메시지만 출력

shutdown -f
→ fsck 없이 재부팅

shutdown -n
→ init 호출 없이 shutdown

shutdown -v
→ 상세 정보 출력
```

---

## 2. reboot

`reboot`는 리눅스를 다시 시작하는 명령어이다.

### reboot 옵션

| 옵션 | 설명 |
|---|---|
| `-n` | 연산을 중지하고 다시 시작 |
| `-f` | 강제로 다시 시작 |
| `-p` | 연산 중지 시 전원을 종료 |
| `-q` | 오류가 없으면 다시 시작하지 않음 |
| `-v` | 상세 정보 출력 |

```text
reboot
→ 시스템 재시작

reboot -f
→ 강제 재시작

reboot -p
→ 연산 중지 시 전원 종료
```

---

## 3. halt

`halt`는 리눅스를 종료하는 명령어이다.

### halt 옵션

| 옵션 | 설명 |
|---|---|
| `-d` | wtmp에 로그를 기록하지 않음 |
| `-f` | 강제로 종료 |
| `-n` | 종료할 때 동기화를 하지 않음 |
| `-w` | 실제 종료하지 않고 `/var/log/wtmp`에 로그 기록 |

```text
halt
→ 시스템 종료

halt -f
→ 강제 종료

halt -d
→ wtmp 로그 기록 안 함

halt -n
→ 종료 시 동기화 안 함

halt -w
→ 실제 종료 없이 wtmp 로그만 기록
```

---

## 4. 명령어 비교

| 명령어 | 핵심 기능 |
|---|---|
| `shutdown` | 시스템 종료 또는 재부팅 제어 |
| `reboot` | 시스템 재시작 |
| `halt` | 시스템 종료 |

---

## 5. 시험 직전 암기

```text
shutdown
→ 시스템 종료 명령

-r
→ 재부팅

-h
→ 종료

-c
→ shutdown 취소

-k
→ 경고 메시지만 출력

-f
→ fsck 없이 재부팅

-n
→ init 호출 없이 shutdown

-v
→ 상세 정보

reboot
→ 시스템 재시작

reboot -f
→ 강제 재시작

reboot -p
→ 연산 중지 시 전원 종료

halt
→ 시스템 종료

halt -d
→ wtmp 로그 기록 안 함

halt -f
→ 강제 종료

halt -n
→ 종료 시 동기화 안 함

halt -w
→ 실제 종료 없이 /var/log/wtmp 로그 기록
```
