# Process Management

네트워크관리사 2급 NOS 파트의 **리눅스 프로세스와 프로세스 모니터링** 내용을 정리한다.

---

## 1. Process

프로세스(Process)는 프로그램이 실행되어 메모리에 올라간 상태를 의미한다.

프로세스는 메모리를 점유하며 사용자의 요청에 따라 명령을 실행한다.

```text
Program 실행
→ Memory에 올라감
→ Process
```

---

## 2. Daemon Process

데몬(Daemon) 프로세스는 리눅스 서버가 부팅될 때 백그라운드에서 실행되며 클라이언트의 요청에 대한 서비스를 수행하는 프로그램이다.

리눅스가 부팅될 때 실행되는 데몬 프로세스는 `init` 프로세스가 기동시킨다.

```text
Daemon
→ 서버 부팅 시 실행
→ Background에서 동작
→ Client 요청 처리
```

---

## 3. Daemon 실행 방식

### standalone 방식

백그라운드에서 항상 실행되고 있다가 클라이언트가 서비스를 요청하면 즉시 처리한다.

```text
standalone
→ 항상 실행
→ 요청 즉시 처리
```

### inetd 방식

메모리에 상주하지 않고 sleep 상태로 있다가 클라이언트의 요청이 들어오면 Wake Up하여 서비스를 수행한다.

```text
inetd
→ 평소 Sleep
→ 요청 발생
→ Wake Up
→ 서비스 수행
```

---

## 4. standalone과 inetd 비교

| 방식 | 특징 |
|---|---|
| `standalone` | 항상 실행 중이며 요청 시 즉시 처리 |
| `inetd` | 평소 sleep 상태이며 요청 시 wake up |

```text
standalone
→ Always Running

inetd
→ Sleep → Request → Wake Up
```

---

## 5. ps

`ps` 명령은 프로세스 상태 정보를 확인하는 명령어이다.

실행 중인 프로세스의 목록과 PID 등을 확인할 수 있다.

모든 프로세스에는 PID(Process ID)가 부여된다.

```text
ps
→ 프로세스 상태 확인
→ 실행 중인 프로세스 확인
→ PID 확인
```

책에서는 `init` 프로세스를 리눅스 부팅 시 기동되는 데몬 프로세스로 설명한다.

---

## 6. pstree

`pstree`는 실행 중인 프로세스의 상태를 **트리 형태로 출력**하는 명령어이다.

프로세스의 부모와 자식 관계를 확인할 수 있다.

```text
pstree
→ Process Tree
→ 부모 프로세스
→ 자식 프로세스
```

### pstree 옵션

| 옵션 | 설명 |
|---|---|
| `-n` | PID 순으로 정렬 |
| `-p` | 프로세스명과 함께 PID 출력 |

```text
pstree -n
→ PID 순 정렬

pstree -p
→ 프로세스명 + PID 출력
```

---

## 7. top

`top`은 리눅스 시스템의 시스템 자원을 모니터링할 수 있는 명령어이다.

책에서 확인할 수 있다고 제시한 정보는 다음과 같다.

- CPU 사용률
- 메모리 사용률
- 실행 중인 프로세스 리스트
- 프로세스 우선순위 정보

```text
top
→ 실시간 시스템 모니터링

확인 정보
→ CPU
→ Memory
→ Process
→ Priority
```

`top` 실행 중에도 명령어를 입력하여 추가 기능을 실행할 수 있다.

---

## 8. ps / pstree / top 비교

| 명령어 | 기능 |
|---|---|
| `ps` | 프로세스 상태 정보 확인 |
| `pstree` | 부모-자식 관계를 트리 형태로 확인 |
| `top` | CPU, Memory, Process 등을 실시간 모니터링 |

---

## 9. 시험 직전 암기

```text
Process
→ 프로그램이 실행되어 메모리에 올라간 상태

Daemon
→ Background 실행
→ Client 요청 처리
→ 부팅 시 init이 기동

standalone
→ 항상 실행
→ 요청 즉시 처리

inetd
→ 평소 Sleep
→ 요청 시 Wake Up

ps
→ 프로세스 상태 확인
→ PID 확인

pstree
→ Process Tree
→ 부모 / 자식 관계

pstree -n
→ PID 순 정렬

pstree -p
→ 프로세스명 + PID 출력

top
→ 실시간 시스템 자원 모니터링
→ CPU
→ Memory
→ Process
→ Priority
```
