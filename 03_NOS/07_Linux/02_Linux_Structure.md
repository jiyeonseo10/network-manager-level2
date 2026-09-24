# Linux Structure

네트워크관리사 2급 NOS 파트의 **리눅스 구조** 내용을 정리한다.

---

## 1. 리눅스 구조

리눅스는 운영체제(Operating System)의 한 종류로 운영체제가 가지는 기본적인 기능을 제공한다.

주요 관리 기능은 다음과 같다.

- 프로세서 관리
- 메모리 관리
- 입출력 장치 관리
- 프로세스 관리
- 사용자 관리
- 보안 관리
- 로그 관리
- 하드웨어 관리
- 파일 시스템 관리

리눅스는 크게 다음과 같이 구성된다.

```text
Linux
→ Kernel
→ Shell
→ File System
```

---

## 2. Kernel

**Kernel**은 운영체제의 핵심 기능을 담당한다.

프로세서, 프로세스, 메모리, 입출력 장치 등을 관리하며 운영체제에서 가장 중요한 역할을 수행한다.

### Kernel의 기능

- Processor 사용 관리
- Main Memory 사용 관리
- 실행 중인 Process 관리
- Device Management
- 입출력 관리

```text
Kernel
→ 운영체제 핵심
→ Processor 관리
→ Memory 관리
→ Process 관리
→ Device / I/O 관리
```

Kernel은 주기억 장치에 상주하며 사용자 프로그램을 관리한다.

책의 리눅스 계층 설명에서는 Kernel의 주요 기능을 다음과 같이 정리한다.

- 프로세스 관리
- 메모리 관리
- 입출력(I/O) 관리
- 파일 관리

---

## 3. Shell

**Shell**은 사용자의 명령을 입력받아 실행하는 인터프리터(Interpreter) 기능을 수행한다.

사용자가 명령어를 입력하면 이를 해석하고 실행한다.

### Shell의 기능

- 사용자 명령어 실행
- 사용자 명령어를 입력하면 바로 실행시키는 인터프리터 기능 제공
- 프로그램 실행

리눅스의 표준 Shell은 **bash**이다.

그 외에도 다음과 같은 Shell을 제공한다.

- Bourne Shell
- C Shell
- Korn Shell

```text
Shell
→ 명령어 해석기 / 번역기
→ 사용자 명령 실행
→ 프로그램 실행

표준 Shell
→ bash

그 외
→ Bourne Shell
→ C Shell
→ Korn Shell
```

책의 예시에서는 다음 명령을 사용한다.

```bash
which sh
```

실행 프로그램의 경로를 출력한다.

```bash
sh
```

Shell을 실행한다.

```bash
ls
```

파일 목록을 출력한다.

---

## 4. File System

**File System**은 디스크, USB, SSD 등의 저장 장치에 보관된 파일을 관리하기 위한 구조이다.

파일과 디렉토리를 생성, 변경, 삭제할 수 있다.

### File System의 기능

- 사용자 파일 및 디렉토리 관리
- 파일과 디렉토리 권한 설정 및 해제
- 파일의 연결 정보인 링크 관리
- 파일 소유자 관리
- 그룹 관리
- 파일 생성 일자 관리
- 파일 변경 일자 관리

```text
File System
→ 파일 / 디렉토리 관리
→ 권한 관리
→ 링크 관리
→ 소유자 관리
→ 그룹 관리
→ 생성 / 변경 일자 관리
```

리눅스 파일 시스템은 **Root 디렉토리**를 중심으로 하위 디렉토리가 구성되는 계층형 구조이다.

```text
Root
└── 하위 디렉토리
    └── 하위 디렉토리
        └── 파일
```

책에서는 Linux뿐 아니라 Windows와 Unix도 계층형 파일 시스템을 사용한다고 설명한다.

---

## 5. 리눅스 계층

리눅스 계층은 다음과 같이 정리할 수 있다.

| 계층 | 설명 |
|---|---|
| Kernel | 주기억 장치에 상주하며 리눅스 운영체제의 핵심 기능 수행 |
| Shell | 사용자 명령을 해석하고 프로그램 실행 |
| File System | 파일과 디렉토리를 트리 구조로 관리 |

### Kernel

```text
Kernel
→ 주기억 장치에 상주
→ 사용자 프로그램 관리
→ 운영체제 핵심
→ Process / Memory / I/O / File 관리
```

### Shell

```text
Shell
→ 명령어 해석기 / 번역기
→ 사용자 명령 입출력
→ 프로그램 실행
```

### File System

```text
File System
→ 시스템 정보를 저장하는 기본 구조
→ 디렉토리 / 서브 디렉토리 / 파일
→ 계층적인 Tree 구조
```

---

## 6. 시험 직전 암기

```text
Linux 구조
→ Kernel
→ Shell
→ File System

Kernel
→ 운영체제 핵심
→ CPU / Processor 관리
→ Memory 관리
→ Process 관리
→ Device / I/O 관리
→ 파일 관리

Shell
→ 사용자 명령 해석 및 실행
→ Interpreter
→ 표준 Shell = bash
→ Bourne / C / Korn Shell

File System
→ 파일 / 디렉토리 관리
→ 권한 설정 / 해제
→ 링크 관리
→ 소유자 / 그룹 관리
→ 생성 / 변경 일자 관리
→ Root 중심 계층형 구조
```
