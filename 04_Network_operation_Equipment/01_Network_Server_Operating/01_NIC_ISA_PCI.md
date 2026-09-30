# NIC / ISA / PCI

## 1. NIC(Network Interface Card)

NIC는 컴퓨터와 네트워크 사이에서 통신을 수행하는 장치이다.

```text
NIC
→ Network Interface Card
→ OSI 물리 계층 장치
→ 컴퓨터 Main Board에 장착
→ LAN Cable(UTP)과 연결
→ Network와 Computer 사이 통신 수행
```

---

## 2. NIC 특징

```text
NIC
→ 데이터 링크 계층과 물리 계층 사이 통신 지원
→ Baseband 사용
→ LAN, Token Ring 등에 사용
→ Interface 역할 수행
→ MAC Address 보유
```

NIC 카드에는 물리적인 Hardware 주소인 MAC 주소가 할당되어 있다.

```text
MAC Address
→ 물리적 Hardware Address
```

MAC 주소의 상위 24bit는 제조사 번호이다.

```text
MAC 상위 24bit
→ 제조사 번호
```

Ethernet은 다음 표준을 사용한다.

```text
Ethernet
→ IEEE 802.3
```

---

## 3. NIC 카드 확인

Windows에서는 장치 관리자에서 NIC 카드를 확인할 수 있다.

```text
Windows
→ 장치 관리자
→ Network Adapter 확인
```

교재 예에서는 NIC 카드가 Main Board와 PCI 방식으로 연결되어 있다.

---

## 4. NIC 카드 종류

### Ethernet

```text
Ethernet
→ IEEE 802.3
→ 10Mbps
```

### Fast Ethernet

```text
Fast Ethernet
→ 기존 Ethernet보다 10배 향상
→ 100Mbps
→ 기존 Ethernet Card와 호환성 유지
```

### Gigabit Ethernet

```text
Gigabit Ethernet
→ 광케이블과 연결
→ 1Gbps 지원
```

### Token Ring

```text
Token Ring
→ Main Frame System에 설치
→ 약 16Mbps
→ 가격이 비쌈
```

### ATM LAN

```text
ATM LAN
→ 고속 ATM Network 접속용 Card
```

---

## 5. NIC와 Main Board 연결 방식

교재에서 설명하는 방식:

```text
ISA
PCI
```

최근 컴퓨터에서는 다음 방식을 사용한다.

```text
PCI Express
```

---

## 6. ISA

ISA는 Industry Standard Architecture bus이다.

```text
ISA
→ IBM PC/XT, PC/AT용 Interface 방식
→ 16bit
→ 3Mbps
→ 고속 환경에 부적합
→ PCI 방식으로 대체
```

---

## 7. PCI

PCI는 Peripheral Component Interconnect bus이다.

```text
PCI
→ Main Board와 주변 장치 사이 Interface Bus
→ ISA보다 고속
→ 32bit / 64bit 지원
→ Bus Mastering 지원
→ PnP 지원
```

---

## 8. Bus Mastering

```text
Bus Mastering
→ Interrupt를 사용하지 않고
→ 단말기에 직접 정보 전송
→ DMA 방식 개선
```

---

# 시험 직전 암기

```text
NIC
→ Network Interface Card
→ 물리 계층
→ UTP 연결
→ MAC 주소 보유
```

```text
MAC 상위 24bit
→ 제조사 번호
```

```text
Ethernet
→ IEEE 802.3
→ 10Mbps

Fast Ethernet
→ 100Mbps

Gigabit Ethernet
→ 1Gbps

Token Ring
→ 약 16Mbps
```

```text
ISA
→ 16bit
→ 3Mbps
→ 오래되고 느림

PCI
→ 32bit / 64bit
→ ISA보다 빠름
→ Bus Mastering
→ PnP
```

```text
최근 방식
→ PCI Express
```

## 헷갈리기 쉬운 것

```text
NIC
→ 물리 계층 장치

MAC 주소 할당
→ 데이터 링크 계층에서 수행
```

```text
Ethernet
→ IEEE 802.3

Fast Ethernet
→ 100Mbps

Gigabit Ethernet
→ 1Gbps
```

```text
ISA
→ 16bit / 3Mbps

PCI
→ 32bit 또는 64bit
→ Bus Mastering + PnP
```
