# Network Commands

네트워크관리사 2급 NOS 파트의 **리눅스 네트워크 명령어** 내용을 정리한다.

---

## 1. netstat

`netstat`는 시스템과 연결된 모든 네트워크 연결 상태를 확인하는 명령어이다.

```text
netstat
→ 네트워크 연결 상태 확인
```

### netstat 옵션

| 옵션 | 설명 |
|---|---|
| `-a` | 모든 소켓 정보 확인 |
| `-n` | 도메인 주소를 읽지 않고 숫자로 출력 |
| `-p` | PID와 사용 중인 프로그램명 출력 |
| `-g` | 멀티캐스트 그룹 정보 출력 |

```text
netstat -a
→ 모든 소켓

netstat -n
→ 주소를 숫자로 출력

netstat -p
→ PID / 프로그램명

netstat -g
→ 멀티캐스트 그룹 정보
```

---

## 2. netstat 상태 값

| 상태 값 | 설명 |
|---|---|
| `LISTEN` | 접속 요청을 대기하고 있는 상태 |
| `ESTABLISHED` | 연결이 확립되어 통신이 이루어지는 상태 |
| `CLOSE_WAIT` | 연결 종료를 대기하고 있는 상태 |
| `TIME_WAIT` | 연결 종료 후 일정 시간 동안 소켓을 열어둔 상태 |
| `CLOSE` | 연결이 종료된 상태 |

```text
LISTEN
→ 접속 요청 대기

ESTABLISHED
→ 연결 확립 / 통신 중

CLOSE_WAIT
→ 연결 종료 대기

TIME_WAIT
→ 연결 종료 후 일정 시간 대기

CLOSE
→ 연결 종료
```

---

## 3. 네트워크 인터페이스 정보

책의 예시에서 다음과 같은 인터페이스를 확인할 수 있다.

```text
eth0
→ 네트워크 인터페이스

lo
→ Loopback
→ 127.0.0.1
```

MTU는 한 번에 통과할 수 있는 패킷의 최대 크기를 의미한다.

---

## 4. Routing Flags

netstat로 라우팅 상태를 확인하면 Flag 정보를 볼 수 있다.

| Flag | 설명 |
|---|---|
| `U` | 라우터 Up 상태 |
| `G` | Default Gateway |
| `H` | 라우터가 호스트 장비 |
| `S` | setsrc 옵션으로 생성 |
| `D` | redirect로 동적으로 생성 |
| `A` | 혼합된 라우팅 |
| `B` | 브로드캐스트 주소 |
| `L` | 호스트 로컬 주소 |

```text
U
→ Up

G
→ Default Gateway

H
→ Host

D
→ redirect에 의해 동적 생성
```

---

## 5. arp

ARP는 IP 주소를 MAC 주소로 변환하는 프로토콜이다.

```text
ARP
→ IP 주소 → MAC 주소
```

### arp 옵션

| 옵션 | 설명 |
|---|---|
| `-a` | ARP Cache의 모든 호스트 정보 출력 |
| `-s` | ARP Cache의 특정 IP에 대한 MAC 주소 변경 |
| `-d` | ARP Cache의 특정 MAC 주소 삭제 |
| `-i` | 특정 Ethernet의 ARP 확인 |

```text
arp -a
→ ARP Cache 전체 확인

arp -s
→ 특정 IP의 MAC 주소 변경

arp -d
→ 특정 MAC 주소 삭제

arp -i
→ 특정 Ethernet ARP 확인
```

---

## 6. traceroute

`traceroute`는 네트워크를 이용하여 목적지까지 찾아가는 경로 정보를 확인하는 명령어이다.

IP 주소 또는 URL을 입력하면 네트워크를 통과하는 구간별 정보를 표시한다.

확인할 수 있는 정보:

- Gateway
- IP 주소
- 시간

책에서는 `traceroute`가 내부적으로 **UDP와 ICMP**를 사용한다고 설명한다.

```text
traceroute
→ 목적지까지의 경로 확인
→ UDP / ICMP 사용
```

### traceroute 옵션

| 옵션 | 설명 |
|---|---|
| `-m` | 최대 TTL 설정, 기본값 30 |
| `-n` | Hop 주소 출력 |
| `-p` | 사용하는 UDP 포트 지정 |
| `-r` | 목적 호스트가 직접 로컬로 연결되었다고 지정 |
| `-s` | 호스트 IP 지정 |
| `-t` | Packet의 Type of Service 지정 |
| `-v` | 상세 정보 출력 |
| `-w` | 전송 패킷 대기 시간 설정 |

TTL 또는 Hop은 통과할 수 있는 라우터의 수를 의미한다.

```text
TTL = Hop
→ 통과할 수 있는 라우터 수
```

---

## 7. ping

`ping`은 네트워크 상태를 점검하기 위한 명령어이다.

ICMP 프로토콜을 사용하며 다음 과정을 통해 연결 상태를 확인한다.

```text
ICMP Echo Request
→ 요청 전송

ICMP Echo Reply
→ 응답 확인
```

```text
ping
→ 네트워크 상태 점검
→ ICMP 사용
```

---

## 8. nslookup

`nslookup`은 도메인명에 대한 IP 주소를 확인하기 위해 DNS 서버에 질의하는 명령어이다.

```text
nslookup
→ DNS 서버에 Query
→ 도메인 이름에 대한 IP 주소 확인
```

책의 예시에서는 DNS 서버의 포트 번호도 확인할 수 있다.

```text
DNS
→ Port 53
```

---

## 9. 명령어 비교

| 명령어 | 역할 |
|---|---|
| `netstat` | 네트워크 연결 상태 확인 |
| `arp` | IP 주소와 MAC 주소 정보 확인 |
| `traceroute` | 목적지까지의 경로 확인 |
| `ping` | 네트워크 연결 상태 점검 |
| `nslookup` | 도메인 이름의 IP 주소 확인 |

---

## 10. 시험 직전 암기

```text
netstat
→ 네트워크 연결 상태

-a
→ 모든 소켓

-n
→ 숫자로 출력

-p
→ PID / 프로그램명

-g
→ 멀티캐스트 그룹

LISTEN
→ 접속 요청 대기

ESTABLISHED
→ 연결 확립

CLOSE_WAIT
→ 연결 종료 대기

TIME_WAIT
→ 종료 후 일정 시간 소켓 유지

CLOSE
→ 연결 종료

lo
→ Loopback
→ 127.0.0.1

ARP
→ IP → MAC

arp -a
→ ARP Cache 전체 확인

traceroute
→ 목적지까지 경로 확인
→ UDP / ICMP

TTL / Hop
→ 통과할 수 있는 라우터 수

ping
→ ICMP Echo Request / Reply
→ 네트워크 상태 확인

nslookup
→ DNS Query
→ 도메인 → IP 주소 확인

DNS
→ Port 53
```
