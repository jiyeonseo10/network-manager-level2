# VLAN / VTP / Trunk

## 1. VLAN(Virtual Local Area Network)

VLAN은 하나의 물리적 Switch를 여러 개의 논리적 환경으로 나누어 각각 별도로 설정하고 관리할 수 있게 하는 네트워크 가상화 기술이다.

```text
VLAN
→ 하나의 물리적 Switch
→ 여러 개의 논리적 Network로 분리
```

교재 핵심:

```text
VLAN
→ 불필요한 Broadcast 방지
→ Network 성능 향상
→ 보안성 향상
```

---

## 2. VLAN 장점

```text
Port / Protocol / MAC Address를 이용하여 VLAN 구성

불필요한 Broadcast 차단
→ Network 성능 향상

데이터 처리 흐름 관리
→ 보안성 향상
```

---

## 3. VLAN 특징

### Broadcast 제어

```text
같은 VLAN에서 발생한 Broadcast
→ 다른 VLAN으로 전달되지 않음
```

따라서:

```text
Broadcast Storm 감소
```

### 보안성 향상

```text
Broadcast Frame
→ 같은 VLAN 내부 장비 또는 Router에만 전달
→ 보안 유지
```

### Trunk

```text
Trunk Link
→ 여러 VLAN 정보를 장치 사이에서 전달
```

DTP:

```text
DTP
→ Dynamic Trunking Protocol
→ Trunk 설정을 자동화하는 Protocol
```

---

## 4. VLAN 종류

### Static VLAN

```text
Static VLAN
→ Port별로 VLAN 구성
→ 가장 일반적인 방식
→ Port 단위 관리
```

### Dynamic VLAN

```text
Dynamic VLAN
→ MAC Address 기반
→ 대형 Switch에서 사용
```

---

## 5. VLAN 구성 기준

### Port 기반

```text
Port를 VLAN에 할당
→ 같은 VLAN Port끼리 통신
→ 가장 일반적인 방식
```

### MAC 주소 기반

```text
같은 VLAN에 속한 MAC Address 간 통신
→ Host MAC Address 등록 및 관리
```

### Protocol 기반

```text
같은 Protocol을 사용하는 Host끼리 VLAN 구성
```

### Network Address 기반

```text
Network Address를 기준으로 VLAN 구성
→ 같은 Network의 Host끼리 통신
```

---

## 6. VTP(VLAN Trunking Protocol)

VTP는 복수의 Switch 간에 VLAN 설정 정보를 교환하는 Protocol이다.

```text
VTP
→ Switch 간 VLAN 설정 정보 교환
→ VLAN 설정 관리 편의성 향상
```

---

## 7. VLAN 장점 요약

### 유연성

```text
물리적 Network 변경 없이
→ Network 구조 변경 가능
```

### 보안성

```text
Network 분리
→ 별도 접근 통제 가능
```

---

## 8. VLAN 구성 방식

### End to End VLAN

```text
물리적 위치와 관계없이
→ 업무별 / 데이터 종류별 VLAN 할당

사용자 위치와 관계없이
→ 동일 정책 적용
```

### Local VLAN

```text
사용자의 물리적 위치에 따라 VLAN 할당
→ 설정 및 관리 쉬움
```

### Static VLAN

```text
관리자가 모든 Port에 직접 VLAN 할당
```

### Dynamic VLAN

```text
VMPS 사용
→ VLAN 자동 할당
```

단점:

```text
VMPS 장애
→ 전체 Network 장애 가능
```

---

## 9. VLAN Trunk 방식

```text
ISL
IEEE 802.1q
LANE
802.10(FDDI)
```

### ISL

```text
ISL
→ Inter Switch Link
→ Cisco Switch에서 사용
→ Fast Ethernet / Gigabit Ethernet Link에 사용
```

### IEEE 802.1q

```text
IEEE 802.1q
→ Frame Tagging 표준 방식
→ VLAN 구분을 위해 Frame에 Field 추가
```

Cisco와 다른 Vendor 장비를 연결할 때:

```text
IEEE 802.1q 사용
```

### LANE

```text
LANE
→ LAN Emulation
→ 다중 VLAN을 ATM과 연결
```

### 802.10(FDDI)

```text
802.10(FDDI)
→ VLAN 정보 전달 시
→ Frame Header의 SAID Field 사용
```

---

## 10. VLAN 정보 확인

Cisco Switch에서:

```text
show vlan
```

사용.

예:

```text
VLAN 1
→ default

VLAN 50
→ Computers
```

---

# 시험 직전 암기

```text
VLAN
→ 물리적 Switch 하나
→ 논리적으로 여러 Network
```

```text
장점
→ Broadcast 제어
→ Network 성능 향상
→ 보안성 향상
```

```text
Static VLAN
→ Port 기반
→ 관리자 직접 설정

Dynamic VLAN
→ MAC Address 기반
```

```text
Trunk
→ 여러 VLAN 정보 전달
```

```text
DTP
→ Dynamic Trunking Protocol
```

```text
VTP
→ Switch 간 VLAN 설정 정보 교환
```

```text
End to End VLAN
→ 위치와 관계없이 업무/데이터 기준

Local VLAN
→ 물리적 위치 기준
```

```text
ISL
→ Cisco

IEEE 802.1q
→ 표준 Frame Tagging
```

```text
show vlan
→ VLAN 정보 확인
```

## 자주 헷갈리는 것

```text
Static VLAN
→ Port 기준

Dynamic VLAN
→ MAC Address 기준
```

```text
DTP
→ Trunk 자동 협상

VTP
→ VLAN 설정 정보 교환
```

```text
ISL
→ Cisco

802.1q
→ 표준 방식
```
