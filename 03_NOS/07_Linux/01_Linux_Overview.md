# Linux Overview

네트워크관리사 2급 NOS 파트의 **리눅스 개요와 특징**을 정리한다.

---

## 1. 리눅스 개요

리눅스는 컴퓨터 시스템의 하드웨어를 효율적으로 관리하기 위한 시스템 소프트웨어이며 운영체제의 한 종류이다.

책에서는 다음과 같이 설명한다.

- 1989년 핀란드 헬싱키 대학의 **Linus Torvalds**가 개발
- Unix를 기반으로 개발
- 공개용(Open Source) 운영체제
- 개인용 컴퓨터와 워크스테이션을 위해 개발
- 소스코드부터 운영체제 사용까지 무료 공개
- 사용자가 운영체제를 수정하여 사용할 수 있음

```text
Linux
→ Unix 기반
→ Linus Torvalds
→ 1989년
→ Open Source
→ 무료 공개
→ 사용자 수정 가능
```

---

## 2. 다중 사용자

**Multi User**는 여러 사용자가 네트워크를 통해 접속하여 하나의 컴퓨터 시스템을 사용할 수 있도록 하는 기능이다.

다중 사용자를 지원하기 때문에 다음 기능도 제공한다.

- 사용자별 권한 관리
- 자원 관리

```text
Multi User
→ 여러 사용자 사용
→ 사용자별 권한 관리
→ 자원 관리
```

---

## 3. 다중 작업

**Multi-Tasking**은 운영체제에서 여러 개의 프로세스(Process)를 동시에 실행하는 기능이다.

여러 프로세스가 동시에 실행되므로 CPU 스케줄링이 필요하다.

책에서는 기본적으로 일정 시간(Time Slice)만큼 자원을 할당하는 **Time Sharing System**을 지원한다고 설명한다.

```text
Multi-Tasking
→ 여러 Process 동시 실행
→ CPU Scheduling
→ Time Slice
→ Time Sharing System
```

---

## 4. 다중 처리기

**Multi-Processor**는 하나 이상의 CPU가 설치된 시스템에서 여러 CPU를 지원하는 기능이다.

여러 CPU를 사용하여 작업을 병렬적으로 처리할 수 있다.

```text
Multi-Processor
→ 여러 CPU 지원
→ 병렬 처리
→ 시스템 효율 향상
```

---

## 5. 다중 플랫폼

**Multi-Platform**은 여러 종류의 CPU를 지원하는 기능이다.

책에서 제시한 예는 다음과 같다.

- Intel
- Sun Sparc
- Power PC

```text
Multi-Platform
→ 여러 종류의 CPU 지원
→ Intel
→ Sun Sparc
→ Power PC
```

---

## 6. 계층형 파일 시스템

리눅스 파일 시스템은 **Root**를 기반으로 하위 디렉토리가 구성되는 계층형 구조이다.

이러한 구조를 이용하여 디렉토리를 쉽게 추가하고 관리할 수 있다.

책에서는 Linux뿐 아니라 Windows와 Unix도 계층형 파일 시스템을 사용한다고 설명한다.

```text
File System
→ 계층형 구조
→ Root 기반
→ 하위 디렉토리 구성
```

---

## 7. POSIX 호환

POSIX는 Unix 시스템의 표준 인터페이스를 정의한 규격이다.

다양한 Unix 계열 운영체제의 공통적인 API를 제시하여 시스템 간 이식성을 높이기 위해 IEEE가 지정한 인터페이스 규격이다.

리눅스는 POSIX 표준을 따른다.

```text
POSIX
→ Unix 시스템 표준 인터페이스
→ Unix 계열 시스템 간 이식성 향상
→ IEEE 지정
→ Linux는 POSIX 표준을 따름
```

---

## 8. 네트워킹

리눅스는 다양한 네트워크 프로토콜을 지원한다.

책에서 제시한 프로토콜은 다음과 같다.

- TCP/IP
- IPX/SPC
- Appletalk
- Bluetooth

리눅스 설치 후 다음 정보를 설정하면 네트워크를 사용할 수 있다.

- IP 주소
- Gateway
- Subnet

```text
Networking
→ TCP/IP
→ IPX/SPC
→ Appletalk
→ Bluetooth

네트워크 설정
→ IP 주소
→ Gateway
→ Subnet
```

---

## 9. 가상 콘솔

리눅스는 기본적으로 **6개의 가상 콘솔(Virtual Console)** 을 지원한다.

각 가상 콘솔에서 서로 다른 작업을 수행할 수 있어 물리적 모니터의 한계를 극복할 수 있다.

```text
Virtual Console
→ 기본 6개
→ 각 콘솔에서 서로 다른 작업 수행
```

---

## 10. 가상 기억 장치

**Virtual Memory**는 주기억 장치(Main Memory)의 한계를 극복하기 위해 보조 기억 장치를 주기억 장치처럼 사용하는 방식이다.

이를 통해 주기억 장치의 공간을 확대하여 기억 장치를 효율적으로 사용할 수 있다.

```text
Virtual Memory
→ 보조 기억 장치를 주기억 장치처럼 사용
→ 메모리 공간 확대
→ 시스템을 안정적으로 사용
```

---

## 11. 시험 직전 암기

```text
Linux
→ Unix 기반
→ Linus Torvalds
→ 1989년
→ Open Source
→ 무료 / 수정 가능

Multi User
→ 여러 사용자
→ 권한 / 자원 관리

Multi-Tasking
→ 여러 Process 동시 실행
→ Time Slice
→ Time Sharing System

Multi-Processor
→ 여러 CPU
→ 병렬 처리

Multi-Platform
→ Intel / Sun Sparc / Power PC

File System
→ Root 기반 계층형 구조

POSIX
→ Unix 표준 인터페이스
→ IEEE 지정

Networking
→ TCP/IP
→ IPX/SPC
→ Appletalk
→ Bluetooth

Virtual Console
→ 기본 6개

Virtual Memory
→ 보조 기억 장치를 주기억 장치처럼 사용
→ 메모리 공간 확장
```
