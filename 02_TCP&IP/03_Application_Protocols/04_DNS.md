# DNS

네트워크관리사 2급 TCP/IP 파트의 **DNS** 내용을 정리한다.

---

## 1. DNS 개요

DNS는 **Domain Name Service**이다.

인터넷 네트워크에서 컴퓨터 이름을 IP 주소로 변환하거나 해석할 때 사용하는 분산 네이밍 시스템이다.

```text
DNS
→ Domain Name Service
→ 도메인명 ↔ IP 주소 해석
```

DNS는 53번 포트를 사용한다.

교재 기준:

```text
512Byte 초과
→ TCP

512Byte 이하
→ UDP
```

---

## 2. DNS 확인

DNS를 확인할 때 다음 도구를 사용할 수 있다.

```text
nslookup
→ 도메인에 대한 IP 주소 확인
```

---

## 3. DNS 이름 해석

DNS는 이름을 해석할 때 DNS Cache Table과 hosts 파일을 이용한다.

```text
DNS Cache / hosts
→ 이름 정보 확인

정보가 없으면
→ DNS Server에 질의
```

### DNS Cache

자주 조회한 도메인과 IP 주소 정보를 저장한다.

```text
DNS Cache
→ 이미 조회한 정보 저장
→ 빠른 응답 가능
```

### hosts 파일

IP 주소와 URL 정보를 직접 등록하여 이름을 해석할 수 있다.

```text
IP 주소 + 도메인명
```

---

## 4. DNS 구조

DNS는 계층적인 구조를 가진다.

```text
Root Domain
↓
Top Level Domain
↓
Second Level Domain
↓
Third / Subdomain
```

### Root Domain

모든 도메인의 근본이 되는 최상위 Root Level Domain이다.

```text
.
```

### Top Level Domain

예:

```text
.com
.org
.kr
```

### Second Level

사용자가 도메인명을 신청하여 등록할 수 있는 영역이다.

---

## 5. Recursive Query

Recursive Query는 **순환쿼리**이다.

Local DNS 서버에 Query를 보내고 완성된 답을 요청한다.

```text
Recursive Query
→ Local DNS 서버에 질의
→ 최종 답을 요청
```

---

## 6. Iterative Query

Iterative Query는 **반복쿼리**이다.

Local DNS 서버가 다른 DNS 서버들에게 질의하여 단계적으로 정보를 얻는다.

```text
Iterative Query
→ Root DNS
→ Top-Level DNS
→ Second-Level DNS
→ 단계적으로 질의
```

비교:

```text
Recursive
→ 완성된 답 요구

Iterative
→ 단계적으로 DNS 서버에 질의
```

---

## 7. DNS Request / Response

DNS 클라이언트는 DNS Server에 **DNS Request**를 전달한다.

DNS 서버는 이에 대해 **DNS Response**로 응답한다.

```text
Client
→ DNS Request
→ DNS Server

DNS Server
→ DNS Response
→ Client
```

DNS Request의 `type` 필드를 이용하여 원하는 레코드 종류를 지정한다.

```text
A
→ IPv4 주소 요청

AAAA
→ IPv6 주소 요청
```

---

## 8. DNS 레코드

### A Record

A는 Address 레코드이다.

```text
A
→ 호스트 이름을 IPv4 주소로 매핑
```

---

### AAAA Record

```text
AAAA
→ 호스트 이름을 IPv6 주소로 매핑
```

---

### PTR Record

PTR은 Pointer 레코드이다.

```text
PTR
→ IP 주소를 도메인 이름으로 변환
→ 역방향 조회
```

---

### NS Record

NS는 Name Server 레코드이다.

```text
NS
→ 해당 도메인의 DNS 서버 지정
```

---

### MX Record

MX는 Mail Exchanger 레코드이다.

```text
MX
→ 메일을 받을 호스트 지정
```

---

### CNAME Record

CNAME은 Canonical Name 레코드이다.

```text
CNAME
→ 호스트의 다른 이름 정의
→ Alias
```

---

### SOA Record

SOA는 Start of Authority 레코드이다.

```text
SOA
→ 도메인에 대한 권한을 가진 서버 표시
→ 가장 큰 권한을 가진 호스트 선언
```

---

### Any / ALL

```text
Any / ALL
→ 모든 레코드 표시
```

---

## 9. DNS 레코드 한눈에 보기

| 레코드 | 기능 |
|---|---|
| A | 호스트 이름 → IPv4 |
| AAAA | 호스트 이름 → IPv6 |
| PTR | IP 주소 → 도메인 이름 |
| NS | DNS 서버 지정 |
| MX | 메일 서버 지정 |
| CNAME | 별칭 지정 |
| SOA | 도메인 권한 서버 정보 |
| Any / ALL | 모든 레코드 표시 |

---

## 10. 시험 직전 암기

```text
DNS
→ Domain Name Service
→ 도메인명 ↔ IP 주소
→ Port 53

교재 기준
→ 512Byte 초과 TCP
→ 512Byte 이하 UDP

nslookup
→ DNS 확인

Recursive Query
→ Local DNS에 완성된 답 요구

Iterative Query
→ DNS 서버에 단계적으로 질의

A
→ IPv4

AAAA
→ IPv6

PTR
→ IP → 이름
→ 역방향 조회

NS
→ DNS 서버

MX
→ Mail Server

CNAME
→ Alias

SOA
→ 권한 서버 정보

ANY
→ 모든 레코드
```
