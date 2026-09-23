# Windows DNS Server

네트워크관리사 2급 NOS 파트의 **윈도우 DNS 서버** 내용을 정리한다.

---

## 1. 윈도우 DNS 서버

Windows Server는 **DDNS(Dynamic Domain Name Service)** 형태의 DNS 서버를 관리할 수 있다.

또한 사용자 PC에 IP 주소를 동적으로 할당하는 **DHCP 서버와 연동**하여 관리할 수 있다.

```text
Windows DNS Server
→ DDNS 지원
→ DHCP 서버와 연동 가능
```

---

## 2. DNS 서버 기능

사용자 PC가 DNS Request로 도메인 주소를 전송하면
DNS 서버는 해당 도메인의 IP 주소를 찾은 후
DNS Response로 IP 주소를 사용자 PC에 전달한다.

또한 IP 주소를 DNS 서버에 전송하면
해당하는 도메인 주소를 전달할 수 있다.

DNS는 다음 프로토콜과 포트를 사용한다.

```text
TCP
UDP
Port 53
```

### DNS 동작

```text
사용자 PC
→ DNS Request
→ 도메인 주소 전송
→ DNS 서버가 IP 주소 확인
→ DNS Response
→ 사용자 PC에 IP 주소 전달
```

---

## 3. DNS Cache

DNS 서버가 사용자 PC의 요청이 있을 때마다 도메인을 해석하면
DNS 서버에 많은 부하가 발생할 수 있다.

이를 줄이기 위해 최근 자주 참조한 도메인명과 IP 주소를
메모리에 저장해 두었다가 동일한 요청이 발생하면
저장된 정보를 이용하여 응답한다.

이를 **DNS Cache**라고 한다.

DNS Cache는 다음 위치에 존재한다.

- 사용자 PC
- DNS 서버

```text
DNS Cache
→ 최근 도메인명 / IP 주소 저장
→ 동일한 요청 발생 시 저장된 정보 사용
→ DNS 서버 부하 감소
→ 사용자 PC와 DNS 서버에 존재
```

---

## 4. 주 영역 DNS와 보조 영역 DNS

DNS 서버에 장애가 발생하면 도메인 주소를 해석할 수 없기 때문에
DNS 서비스를 계속 제공할 수 있도록 DNS 서버를 이중화한다.

DNS 서버는 다음과 같이 구성할 수 있다.

- 주(Primary) 영역 DNS
- 보조(Second) 영역 DNS

### 주(Primary) 영역 DNS

- DNS 서비스에서 도메인을 해석
- DNS 서버에 영역(Zone)을 등록
- 등록된 영역 정보를 Zone Transfer를 통해 보조 영역 DNS에 전달

```text
Primary DNS
→ 도메인 해석
→ Zone 등록
→ Zone Transfer로 보조 DNS에 영역 정보 전달
```

### 보조(Second) 영역 DNS

- 주 영역 DNS 서버 장애 시 DNS 서버 역할 수행
- 주 영역 DNS의 Zone Transfer를 통해 영역 정보 수신

```text
Second DNS
→ Primary DNS 장애 시 대신 서비스
→ Zone Transfer로 영역 정보 수신
```

---

## 5. Zone

**Zone**은 DNS에서 도메인 주소를 관리하는 기본 관리 단위이다.

```text
Zone
→ DNS에서 도메인 주소를 관리하는 기본 단위
```

---

## 6. Zone Transfer

Zone 정보를 다른 DNS 서버로 전송하는 것을
**Zone Transfer**라고 한다.

주 영역 DNS는 Zone Transfer를 통해
보조 영역 DNS에 영역 정보를 전달한다.

```text
Zone Transfer
→ Zone 정보 전송

Primary DNS
→ Zone Transfer
→ Second DNS
```

---

## 7. 시험 직전 암기

```text
Windows DNS Server
→ DDNS 지원
→ DHCP 연동 가능

DNS
→ 도메인 주소 ↔ IP 주소
→ TCP / UDP
→ Port 53

DNS Request
→ 사용자 PC가 도메인 주소 요청

DNS Response
→ DNS 서버가 IP 주소 응답

DNS Cache
→ 최근 도메인 / IP 정보 저장
→ 반복 요청 시 저장 정보 이용
→ 사용자 PC + DNS 서버에 존재

Primary DNS
→ Zone 등록
→ Zone Transfer로 보조 DNS에 전달

Second DNS
→ Primary 장애 시 대신 서비스
→ Zone Transfer로 정보 수신

Zone
→ DNS의 기본 관리 단위

Zone Transfer
→ Zone 정보 전송
