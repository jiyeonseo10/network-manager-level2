# Windows System

네트워크관리사 2급 NOS 파트의 **윈도우 시스템** 내용을 정리한다.

---

## 1. 윈도우 시스템 개요

윈도우 운영체제는 과거 단일 사용자 운영체제인 DOS에서 시작되었으며, 현재는 GUI(Graph User Interface) 환경과 다중 사용자, 다중 프로세스 구조를 지원한다.

### 핵심 정리

- DOS에서 발전
- GUI 환경 지원
- 다중 사용자 지원
- 다중 프로세스 지원
- 개인용 PC에서 많이 사용

---

## 2. Plug & Play

윈도우는 다양한 하드웨어를 자동으로 인식하여 사용할 수 있는 **Plug & Play** 기능을 지원한다.

Plug & Play와 관련하여 HAL과 Micro Kernel이 중요한 역할을 한다.

---

## 3. 윈도우 시스템 세부 구성

| 구성 요소 | 역할 |
|---|---|
| HAL | 하드웨어와 시스템 간 원활한 통신 |
| Micro Kernel | Manager에게 작업을 분담시키고 하드웨어를 제어 |
| I/O Manager | 시스템 입출력 제어, 장치 드라이버 사이 메시지 전달 |
| Object Manager | 파일, 포트, 프로세스, 스레드 등의 정보 제공 |
| Security Reference Manager | 데이터 및 시스템 자원 접근을 허가 또는 거부하여 보안 설정 담당 |
| Process Manager | 프로세스 및 스레드를 생성하고 요청에 따른 작업 처리 |
| Local Procedure Call | 프로세스 간 통신 처리 |
| Virtual Memory Manager | RAM 메모리 할당, 가상 메모리 Paging 제어 |
| Win32/64 Sub System | 32비트 및 64비트 응용 프로그램 동작 지원 |
| POSIX | 유닉스 운영체제에 기반한 표준 운영체제 인터페이스 |
| Security Sub System | 로그인 시 데이터를 보호하고 운영체제가 이를 제어할 수 있도록 지원 |

### 자주 헷갈리는 항목

- **Process Manager** → 프로세스, 스레드
- **Virtual Memory Manager** → RAM, 가상 메모리, Paging
- **Security Reference Manager** → 접근 허가/거부
- **I/O Manager** → 입출력, 장치 드라이버
- **Object Manager** → 파일, 포트, 프로세스, 스레드 정보
- **HAL** → 하드웨어와 시스템 통신

---

## 4. 윈도우 파일 시스템

윈도우 파일 시스템은 FAT(File Allocation Table)과 NTFS(NT File System)를 지원한다.

---

## 5. FAT

### FAT16

- DOS와 Windows 95 초기 버전에서 사용
- 최대 디스크 지원 용량: **2G**
- NTFS, FAT로 변경 및 변환 가능

### FAT32

- **2G 이상의 파티션 지원**
- 대용량 디스크 지원 가능
- **NTFS로 변환(Convert) 가능**
- FAT로 변경 변환은 불가능
- 사용 운영체제
  - Windows 95 OSR2
  - Windows 98
  - Windows 2000
  - Windows XP

---

## 6. NTFS

NTFS는 대용량 파일, 긴 파일명, 보안 기능 등을 지원하는 파일 시스템이다.

### 주요 특징

- 파일 암호화(File Encryption)
- 파일 레벨 보안 지원
- 디스크 할당 및 파티션 단위 Quota 지원
- FAT16이나 FAT32로 변환 불가능
- 긴 파일명 지원
- 저널링 시스템 지원

### 사용 운영체제

- Windows NT
- Windows 2000
- Windows XP

---

## 7. FAT / NTFS 비교

| 항목 | FAT16 | FAT32 | NTFS |
|---|---|---|---|
| 최대/용량 특징 | 최대 2G | 2G 이상 파티션 지원 | 대용량 파일 지원 |
| NTFS 변환 | 가능 | 가능 | - |
| FAT 계열로 변환 | 가능 | FAT로 변경 불가 | FAT16/FAT32로 변환 불가 |
| 파일 암호화 | X | X | O |
| 파일 레벨 보안 | X | X | O |
| Quota | X | X | O |
| 긴 파일명 | - | - | O |
| 저널링 | X | X | O |

---

## 8. 시험 직전 암기

```text
HAL
→ Hardware Abstraction Layer
→ 하드웨어와 시스템 간 통신

Object Manager
→ 파일 / 포트 / 프로세스 / 스레드 정보

Process Manager
→ 프로세스 / 스레드 생성

Virtual Memory Manager
→ RAM / 가상 메모리 / Paging

FAT16
→ 최대 2G

FAT32
→ 2G 이상
→ NTFS로 변환 가능

NTFS
→ 파일 암호화
→ 파일 레벨 보안
→ Quota
→ 긴 파일명
→ 저널링
→ FAT16/FAT32로 변환 불가
