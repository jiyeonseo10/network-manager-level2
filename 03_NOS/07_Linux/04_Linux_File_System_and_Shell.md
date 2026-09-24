# Linux File System and Shell

네트워크관리사 2급 NOS 파트의 **리눅스 파일 시스템과 Shell** 내용을 정리한다.

---

## 1. 리눅스 파일 시스템

리눅스 파일 시스템에는 다음과 같은 종류가 있다.

- ext2
- ext3
- ext4

현재 대부분의 리눅스는 ext4 파일 시스템을 지원한다.

---

## 2. ext2 파일 시스템

ext2의 특징은 다음과 같다.

- 단일 파일 크기 최대 2GB
- 파일명 최대 256Byte
- 최대 파일 시스템 크기 4TB
- 디렉토리당 저장 가능한 최대 파일 수 약 25,500개
- 저널링 파일 시스템을 지원하지 않음

```text
ext2
→ 단일 파일 최대 2GB
→ 파일명 최대 256Byte
→ 파일 시스템 최대 4TB
→ 저널링 X
```

---

## 3. ext3 파일 시스템

ext3의 특징은 다음과 같다.

- 단일 파일 크기 제한 4GB
- 파일명 최대 256Byte
- 최대 파일 시스템 크기 16TB
- 디렉토리당 저장 가능한 최대 파일 수 65,565개
- 저널링 파일 시스템 지원

저널링 파일 시스템은 파일 시스템 오류 수정을 위한 기능이다.

```text
ext3
→ 단일 파일 최대 4GB
→ 파일명 최대 256Byte
→ 파일 시스템 최대 16TB
→ 저널링 O
```

---

## 4. ext4 파일 시스템

ext4는 대용량 파일 시스템을 지원하며 ext2와 ext3의 기능을 확장한 파일 시스템이다.

책에서 제시한 주요 특징은 다음과 같다.

| 특징 | 설명 |
|---|---|
| 대용량 파일 지원 | 1 exabyte 블록 지원, 단일 파일 크기 16TB 지원 |
| 호환성 | ext2 및 ext3 호환, 마운트 가능 |
| fsck | 파일 무결성 오류 시 실행되는 fsck 성능 향상 |
| Extents 지원 | 큰 사이즈 파일을 삭제할 때 시간 단축 |
| 하위 디렉토리 | 기존 32,000개 제한에서 2배 확대 |
| 조각모음 | ext3 저널링 파일 시스템에서 발생하는 단편화를 개선 |

```text
ext4
→ 대용량 파일 지원
→ ext2 / ext3 호환
→ fsck 성능 향상
→ Extents 지원
→ 하위 디렉토리 수 증가
→ 단편화 개선
```

---

## 5. ext2 / ext3 / ext4 비교

| 파일 시스템 | 핵심 특징 |
|---|---|
| ext2 | 저널링 지원 안 함 |
| ext3 | 저널링 지원 |
| ext4 | 대용량 지원, ext2/ext3 호환, Extents, fsck 향상 |

```text
ext2 → 저널링 X
ext3 → 저널링 O
ext4 → 대용량 + 호환성 + Extents + fsck 향상
```

---

## 6. 리눅스 디렉토리 구조

리눅스 파일 시스템은 Root(`/`)를 기준으로 하위 디렉토리가 구성되는 계층형 구조이다.

| 디렉토리 | 설명 |
|---|---|
| `/` | 루트 디렉토리 |
| `/bin` | 기본적인 실행 명령 |
| `/boot` | LILO 등 부팅 관련 파일 |
| `/dev` | 장치 파일 모음 |
| `/etc` | 시스템 설정 파일 |
| `/home` | 사용자 홈 디렉토리 |
| `/lib` | C 라이브러리 |
| `/mnt` | 임시 마운트용 디렉토리 |
| `/proc` | 시스템 정보를 가진 가상 디렉토리 |
| `/root` | root 사용자의 홈 디렉토리 |
| `/sbin` | 시스템 관리용 실행 파일 |
| `/tmp` | 임시 파일 디렉토리 |
| `/usr` | 애플리케이션이 설치되는 디렉토리 |
| `/var` | 시스템에서 운영되는 임시 파일 및 로그 파일 |

### 주요 디렉토리 구분

```text
/home
→ 일반 사용자 홈 디렉토리

/root
→ root 사용자 홈 디렉토리

/bin
→ 기본 실행 명령

/sbin
→ 시스템 관리용 실행 파일

/etc
→ 시스템 설정 파일

/tmp
→ 임시 파일

/var
→ 로그 파일 및 시스템 운영 중 생성되는 파일

/proc
→ 현재 시스템 정보를 가진 가상 디렉토리
```

---

## 7. /dev 장치 파일

`/dev` 디렉토리는 주변 장치와 관련된 장치 정보를 가지고 있다.

| 장치 파일 | 설명 |
|---|---|
| `/dev/fd` | 플로피 디스크 |
| `/dev/hda` | 마스터 IDE 하드 디스크 |
| `/dev/sda` | SCSI 및 SATA 하드 디스크 |
| `/dev/cdrom` | CD-ROM 드라이브 |
| `/dev/mouse` | 마우스 |
| `/dev/hdb` | 슬레이브 IDE 하드 디스크 |
| `/dev/hd` | 하드 디스크 |

```text
/dev
→ 장치 파일

/dev/hda
→ Master IDE HDD

/dev/hdb
→ Slave IDE HDD

/dev/sda
→ SCSI / SATA HDD

/dev/cdrom
→ CD-ROM

/dev/mouse
→ Mouse
```

---

## 8. /proc 디렉토리

`/proc`는 실행 중인 리눅스 시스템의 정보를 가지고 있는 가상 디렉토리이다.

책에서 제시한 정보는 다음과 같다.

- CPU 사용량
- 메모리 사용량
- 파티션 정보
- 입출력 DMA 정보
- 현재 리눅스 운영체제 정보

```text
/proc
→ 시스템 정보를 가진 가상 디렉토리
→ CPU
→ Memory
→ Partition
→ I/O DMA
→ Linux 시스템 정보
```

---

## 9. Shell 개요

Shell은 운영체제와 사용자 사이에서 대화형 인터페이스를 제공한다.

사용자가 명령어를 입력하면 Shell이 명령을 해석하고 Kernel에 전달하여 실행한다.

```text
사용자
→ 명령 입력
→ Shell
→ 명령 해석
→ Kernel
→ 명령 실행
→ 결과 출력
```

리눅스의 표준 Shell은 **bash**이다.

---

## 10. Shell 기능

책에서 제시한 Shell의 주요 기능은 다음과 같다.

- 시그널 처리
- 프로그램 실행
- 파이프 설정
- 리다이렉션 설정
- 백그라운드 프로세스 설정
- 입력된 명령줄 분석
- 와일드카드 분석
- 히스토리 문자 분석

또한 다음 명령을 사용할 수 있다.

```bash
env
```

Shell의 환경 정보를 확인한다.

```bash
set
```

환경 변수를 설정한다.

```text
env
→ Shell 환경 정보 확인

set
→ 환경 변수 설정
```

---

## 11. C Shell

C Shell은 사용 편의를 위해 `.cshrc` 파일에 환경 변수를 저장한다.

로그인할 때 지정된 명령을 자동으로 실행할 수 있다.

```text
C Shell
→ .cshrc
→ 환경 변수 저장
```

---

## 12. Bourne Shell

Bourne Shell은 `.profile` 파일에 환경 변수를 저장한다.

`.profile`은 C Shell의 `.cshrc`와 같은 역할을 한다.

```text
Bourne Shell
→ .profile
→ 환경 변수 저장
```

---

## 13. Korn Shell

Korn Shell은 `.kshrc` 또는 `.profile`에 환경 변수를 저장한다.

C Shell과 TC Shell의 기능을 제공한다.

```text
Korn Shell
→ .kshrc
→ .profile
```

---

## 14. Bash Shell

Bash Shell은 C Shell과 Korn Shell의 특징을 결합한 Shell이다.

- GNU 프로젝트에 의해 개발
- 리눅스에서 가장 많이 사용
- 명령 편집 기능 제공

```text
Bash
→ GNU 프로젝트
→ Linux에서 가장 많이 사용
→ 명령 편집 기능 제공
```

---

## 15. TC Shell

TC Shell(tcsh)은 C Shell의 기능을 강화한 Shell이다.

명령 편집 기능을 제공한다.

```text
TC Shell
→ C Shell 기능 강화
→ 명령 편집 기능
```

---

## 16. Shell 종류 정리

| Shell | 특징 |
|---|---|
| C Shell | `.cshrc` 사용 |
| Bourne Shell | `.profile` 사용 |
| Korn Shell | `.kshrc` 또는 `.profile` 사용 |
| Bash Shell | GNU 프로젝트, 리눅스에서 가장 많이 사용 |
| TC Shell | C Shell 기능 강화 |

---

## 17. 시험 직전 암기

```text
ext2
→ 저널링 X

ext3
→ 저널링 O

ext4
→ 대용량 파일 지원
→ ext2 / ext3 호환
→ Extents
→ fsck 향상

/
→ Root

/bin
→ 기본 실행 명령

/boot
→ 부팅 관련 파일

/dev
→ 장치 파일

/etc
→ 시스템 설정 파일

/home
→ 일반 사용자 홈

/root
→ root 사용자 홈

/lib
→ C 라이브러리

/mnt
→ 임시 마운트

/proc
→ 시스템 정보 가상 디렉토리

/sbin
→ 시스템 관리용 실행 파일

/tmp
→ 임시 파일

/usr
→ 애플리케이션 설치

/var
→ 로그 및 운영 중 생성되는 파일

/dev/sda
→ SCSI / SATA HDD

Shell
→ 사용자 ↔ Kernel 인터페이스
→ 명령 해석 및 실행

Linux 표준 Shell
→ bash

env
→ Shell 환경 정보 확인

set
→ 환경 변수 설정

C Shell
→ .cshrc

Bourne Shell
→ .profile

Korn Shell
→ .kshrc / .profile

Bash
→ GNU
→ Linux에서 가장 많이 사용

TC Shell
→ C Shell 기능 강화
```
