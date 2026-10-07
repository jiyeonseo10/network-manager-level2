# Frame Relay

## 1. Frame Relay 개요

Frame Relay는 멀티 액세스를 위한 네트워크이다.

```text
Frame Relay
→ 여러 장비를 동시에 Network에 연결
→ X.25의 Packet 전송 기술을
   고속 Data 통신에 맞게 개선
```

---

## 2. X.25와 Frame Relay의 관계

### X.25

```text
Network 선로 상태가 좋지 않던 환경에서 개발
→ 많은 Error 처리 기능 포함
→ Error 처리로 인해 Overhead 증가
```

### Frame Relay

```text
좋은 Network 선로 환경에서 사용
→ X.25의 Error 처리 기능을 단순화
→ Overhead 감소
→ 고속 Data 통신에 적합
```

핵심:

```text
X.25
→ Error 처리 많음
→ Overhead 큼

Frame Relay
→ Error 처리 단순화
→ Overhead 감소
```

---

# 3. Frame Relay 특징

교재 기준:

```text
상위 계층에서 Error 복구 및 재전송
```

```text
경로 설정 가능
```

```text
Data 전송 속도 향상
→ 전송 지연 감소
```

```text
망 내부 기능 단순화
```

```text
하나의 물리적 Link에
복수의 논리적 Virtual Circuit 설정
```

```text
단순한 Data 처리 절차만 규정
```

---

# 4. PVC

PVC는:

```text
PVC
→ Permanent Virtual Circuit
```

즉, Frame Relay에서 사용하는 가상 회선이다.

---

# 5. DLCI

DLCI는:

```text
DLCI
→ Data Link Connection Identifier
```

교재에서는 망과 단말 사이의 PVC마다 DLCI를 설정한다고 설명한다.

```text
PVC
→ Virtual Circuit

DLCI
→ 해당 Virtual Circuit을 구분하는 식별자
```

---

# 6. Frame Relay 기본 Protocol 구조

```text
Flag
→ Address
→ Information
→ FCS
→ Flag
```

### Flag

```text
Frame의 시작과 끝을 구분
```

### FCS

```text
Frame의 Error 검사
```

Error가 발생한 Frame은 제거된다.

---

# 7. Frame Relay 제어 Protocol 구조

```text
Flag
→ Address
→ Control
→ Information
→ FCS
→ Flag
```

기본 Protocol 구조와의 차이:

```text
Control Field 추가
```

### Control 역할

```text
Error 제어
흐름 제어
```

---

# 8. 기본 구조 vs 제어 구조

### 기본 구조

```text
Flag
Address
Information
FCS
Flag
```

### 제어 구조

```text
Flag
Address
Control
Information
FCS
Flag
```

핵심 차이:

```text
Control Field 존재 여부
```

---

# 시험 직전 암기

```text
Frame Relay
→ X.25 개선
→ 고속 Data 통신
```

```text
X.25
→ Error 처리 많음
→ Overhead 증가
```

```text
Frame Relay
→ Error 처리 단순화
→ Overhead 감소
→ 전송 속도 향상
→ 전송 지연 감소
```

```text
하나의 물리적 Link
→ 여러 논리적 Virtual Circuit
```

```text
PVC
→ Permanent Virtual Circuit
```

```text
DLCI
→ Data Link Connection Identifier
```

```text
기본 구조
Flag - Address - Information - FCS - Flag
```

```text
제어 구조
Flag - Address - Control - Information - FCS - Flag
```

```text
Flag
→ 시작 / 끝 구분

FCS
→ Error 검사

Control
→ Error 제어 / 흐름 제어
```
