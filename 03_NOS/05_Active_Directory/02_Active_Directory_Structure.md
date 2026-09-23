# Active Directory Structure

네트워크관리사 2급 NOS 파트의 **Active Directory 구조** 내용을 정리한다.

---

## 1. Active Directory 구조

Active Directory 서비스는 네트워크상의 모든 정보를 **계층형 디렉터리**에 저장하여 관리한다.

네트워크 자원(Network Resource)을 디렉터리에 저장함으로써 사용자는 자원을 쉽게 검색할 수 있고, 관리자는 관리 편의성을 높일 수 있다.

Active Directory는 네트워크에 대한 정보를 보유하고 있으며, 저장된 정보를 **이름 공간(Name Space)** 을 통해 검색할 수 있다.

### Object

**Object**는 Active Directory에서 자원의 최소 단위이다.

일반적인 객체에는 다음이 있다.

- 컴퓨터
- 연락처
- 그룹
- 사용자 계정
- 공유 폴더

```text
Object
→ Active Directory 자원의 최소 단위
→ 컴퓨터 / 연락처 / 그룹 / 사용자 계정 / 공유 폴더
```

---

## 2. Active Directory 논리적 구조

Active Directory는 **논리적 구조와 물리적 구조**로 구분된다.

논리적 구조에는 다음이 있다.

- Domain
- Organizational Units
- Tree
- Forest

### Domain

**Domain**은 Active Directory를 관리하기 위한 논리적인 조직 구성의 그룹이다.

- 사용자 계정, 컴퓨터, 프린터 등을 포함
- 네트워크의 모든 객체는 Domain에 소속
- Domain은 고유한 보안 정책을 보유
- 하나 이상의 Domain Controller를 가져야 함

```text
Domain
→ 논리적인 조직 구성 그룹
→ 사용자 / 컴퓨터 / 프린터 등 포함
→ 모든 객체는 Domain에 소속
→ 고유 보안 정책 보유
→ 하나 이상의 Domain Controller 필요
```

### Organizational Units

**OU(Organizational Units)** 는 Domain 내부의 객체를 관리하기 위한 그룹이다.

- 하나의 Domain 안에 여러 OU 존재 가능
- 관리 편의를 위한 작은 계층 구조

```text
OU
→ Domain 내부 객체 관리 그룹
→ 하나의 Domain에 여러 OU 존재 가능
```

### Tree

**Tree**는 Domain의 계층 구조를 의미한다.

- 하나의 Domain으로 구성될 수도 있음
- Root Domain과 하위 Domain 사이에 양방향 신뢰 관계 존재
- Tree 내의 Domain은 같은 Schema를 가짐
- 스키마는 Active Directory 내에 저장

```text
Tree
→ Domain의 계층 구조
→ Root Domain + 하위 Domain
→ 양방향 신뢰 관계
→ 같은 Schema 사용
```

### Forest

**Forest**는 여러 Domain Tree가 모인 그룹이다.

- Domain Tree들이 모여 구성
- Tree 사이에 양방향 신뢰 관계 존재

```text
Forest
→ 여러 Tree의 집합
→ Tree 간 양방향 신뢰 관계
```

---

## 3. Active Directory 물리적 구조

물리적 구조에는 다음이 있다.

- Domain Controller
- Site

### Domain Controller

**Domain Controller**는 Domain 내부의 Active Directory Database를 가지고 있는 컴퓨터이다.

Domain Controller에는 다음 정보가 저장된다.

- 보안 정책
- 사용자 인증 데이터
- 네트워크 Directory 정보

```text
Domain Controller
→ Active Directory Database 보유
→ 보안 정책 저장
→ 사용자 인증 데이터 저장
→ 네트워크 Directory 정보 저장
```

### Site

**Site**는 하나의 IP 서브넷을 기준으로 한 물리적 연결을 의미한다.

- 하나의 Site는 하나의 IP 서브넷으로 물리적 연결
- 하나의 Domain에는 여러 Site가 연결될 수 있음

```text
Site
→ IP 서브넷 기준의 물리적 구조
→ 하나의 Domain에 여러 Site 연결 가능
```

---

## 4. Active Directory 보안 기능

### ACL

**ACL(Access Control List)** 은 어떤 사용자가 어떤 권한으로 객체에 접근할 수 있는지를 지정한다.

```text
ACL
→ 사용자별 객체 접근 권한 지정
```

### Delegation

**Delegation(권한 위임)** 은 관리자가 특정 개인이나 그룹에게 권한 관리를 위임하는 기능이다.

```text
Delegation
→ 권한 위임
→ 특정 개인 또는 그룹에 관리 권한 부여
```

### Inheritance

**Inheritance(상속)** 은 상위 객체의 정의를 하위 자식 객체가 그대로 적용받는 기능이다.

```text
Inheritance
→ 상위 객체의 정의
→ 하위 객체에 그대로 적용
```

### Trust Relationships

**Trust Relationships(신뢰 관계)** 는 다른 Domain의 자원에 접근하기 위해 필요한 신뢰 관계이다.

- 다른 Domain의 자원에 접근하려면 신뢰 관계 필요
- Schema, 환경, Global Catalog Server를 공유

```text
Trust Relationships
→ 다른 Domain 자원 접근
→ 신뢰 관계 필요
```

---

## 5. 논리적 구조와 물리적 구조 정리

| 구분 | 구성 |
|---|---|
| 논리적 구조 | Domain, OU, Tree, Forest |
| 물리적 구조 | Domain Controller, Site |

```text
논리적 구조
→ Domain
→ OU
→ Tree
→ Forest

물리적 구조
→ Domain Controller
→ Site
```

---

## 6. 시험 직전 암기

```text
Object
→ AD 자원의 최소 단위

Domain
→ 객체 관리 논리 단위
→ 고유 보안 정책
→ Domain Controller 필요

OU
→ Domain 내부 객체 관리 그룹

Tree
→ Domain 계층 구조
→ 양방향 신뢰 관계
→ 같은 Schema

Forest
→ 여러 Tree의 집합
→ Tree 간 양방향 신뢰 관계

Domain Controller
→ Active Directory Database
→ 보안 정책
→ 사용자 인증
→ Directory 정보

Site
→ IP 서브넷 기준 물리적 구조

ACL
→ 객체 접근 권한

Delegation
→ 권한 위임

Inheritance
→ 상위 객체 정의가 하위 객체에 적용

Trust Relationships
→ 다른 Domain 자원 접근을 위한 신뢰 관계
```
