# Active Directory

네트워크관리사 2급 NOS 파트의 **액티브 디렉터리(Active Directory)** 내용을 정리한다.

---

## 1. Active Directory 개요

**Active Directory**는 네트워크 정보를 중앙에서 통합적으로 관리하기 위해 사용하는 서비스이다.

주요 관리 대상은 다음과 같다.

- 네트워크
- 사용자
- 그룹

```text
Active Directory
→ 네트워크 정보 중앙 관리
→ 사용자 / 그룹 통합 관리
```

---

## 2. Workgroup과 Domain

Windows 시스템에서는 Workgroup과 Domain을 사용할 수 있다.

### Workgroup

- 각 PC에 저장된 데이터베이스를 이용
- 작은 규모의 네트워크 환경에서 사용
- 각 사용자 계정을 개별적으로 관리
- 각 PC가 스스로 관리

```text
Workgroup
→ 각 PC가 개별 관리
→ 소규모 네트워크
```

### Domain

Domain은 기업 내 여러 컴퓨터 및 사용자 계정을 중앙에서 관리하는 방식이다.

하나의 **Domain Controller**가 컴퓨터와 사용자 계정을 중앙 집중적으로 관리한다.

Domain Controller는 전체 컴퓨터의 **Directory Database**를 가지고 있다.

```text
Domain
→ 중앙 집중 관리
→ Domain Controller 사용
→ Directory Database 보유
```

---

## 3. Directory Service

Directory Database 또는 Directory Service는 네트워크 내의 자원을 관리하기 위한 서비스이다.

다음 작업을 수행할 수 있다.

- 추가
- 삭제
- 변경
- 검색

```text
Directory Service
→ 네트워크 자원 관리
→ 추가 / 삭제 / 변경 / 검색
```

---

## 4. Active Directory 기능

Active Directory의 주요 기능은 다음과 같다.

- 사용자 계정 중앙 통합 관리
- 사용자에게 일관된 보안 정책 적용
- 사용자 데스크톱 환경의 보안 설정 관리
- 공유 자원에 대한 접근 권한 할당
- 응용 프로그램에 Directory Service 제공

```text
Active Directory 기능
→ 사용자 계정 중앙 관리
→ 일관된 보안 정책 적용
→ 데스크톱 보안 설정 관리
→ 공유 자원 접근 권한 할당
→ 응용 프로그램에 Directory Service 제공
```

---

## 5. LDAP

**LDAP(Lightweight Directory Access Protocol)** 는 Directory Database에 접속하기 위해 사용하는 통신 규약이다.

책에서는 다음과 같이 설명한다.

- TCP/IP 기반
- Directory Database에 접속
- 네트워크를 이용하여 사용자 정보 검색
- 디렉터리 정보 등록
- 디렉터리 정보 갱신
- 디렉터리 정보 검색
- 디렉터리 정보 삭제

```text
LDAP
→ Lightweight Directory Access Protocol
→ TCP/IP 기반
→ Directory Database 접근
→ 등록 / 갱신 / 검색 / 삭제
```

---

## 6. Workgroup과 Domain 비교

| 구분 | Workgroup | Domain |
|---|---|---|
| 관리 방식 | 각 PC 개별 관리 | 중앙 집중 관리 |
| 규모 | 소규모 네트워크 | 중앙 관리가 필요한 네트워크 |
| 계정 관리 | 각 PC에서 관리 | Domain Controller에서 관리 |
| 데이터베이스 | 각 PC에 저장 | Directory Database 사용 |

---

## 7. 시험 직전 암기

```text
Active Directory
→ 중앙 집중 관리
→ 네트워크 / 사용자 / 그룹

Workgroup
→ 각 PC가 개별 관리
→ 소규모 네트워크

Domain
→ Domain Controller
→ 중앙 집중 관리
→ Directory Database

Directory Service
→ 추가
→ 삭제
→ 변경
→ 검색

Active Directory 기능
→ 사용자 계정 중앙 관리
→ 보안 정책 적용
→ 공유 자원 접근 권한
→ Directory Service 제공

LDAP
→ Lightweight Directory Access Protocol
→ TCP/IP 기반
→ Directory Database 접근
→ 등록 / 갱신 / 검색 / 삭제
```
