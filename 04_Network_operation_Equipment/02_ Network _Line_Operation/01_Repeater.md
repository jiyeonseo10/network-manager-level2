# Repeater

## 1. Repeater 개요

Repeater는 **OSI 물리 계층**에서 동작하는 장치이다.

```text
Repeater
→ Physical Layer
→ 신호 감쇠 문제 해결
→ 장거리 전송을 위해 신호 증폭
```

네트워크를 통해 전송되는 신호는 거리가 멀어질수록 약해질 수 있는데,
Repeater는 이를 증폭하거나 재생하여 더 멀리 전달할 수 있게 한다.

---

## 2. Repeater 특징

```text
디지털 신호
→ 증폭 또는 재생
```

```text
장거리 전송 가능
→ Network 규모 확장
```

하지만:

```text
신호를 무제한으로 연장할 수는 없음
```

---

## 3. 상위 계층과의 관계

```text
OSI 상위 계층
→ 신호 증폭에 대해 투명성
```

즉, 상위 계층에서는 Repeater가 신호를 증폭하거나 재생하는 과정을 직접 신경 쓰지 않는다.

---

## 4. Hub와 Repeater

별도의 Repeater 장치를 사용할 수도 있지만,
Hub에는 Repeater 기능이 포함되어 있다.

```text
Hub
→ Repeater 기능 포함
```

---

## 5. Amplifier

Amplifier는 입력되는 에너지를 증가시켜 출력에 더 큰 에너지로 전달하는 장치이다.

```text
Amplifier
→ 입력 에너지 증가
→ 더 큰 출력 에너지로 출력
```

---

# 시험 직전 암기

```text
Repeater
→ OSI 물리 계층
→ 신호 감쇠 해결
→ 디지털 신호 증폭 / 재생
→ 장거리 전송
→ Network 규모 확장
→ 무제한 연장 불가
```

```text
Hub
→ Repeater 기능 포함
```

```text
Amplifier
→ 입력 에너지 증가
→ 더 큰 출력 에너지
```

## 자주 헷갈리는 부분

```text
Repeater
→ Routing X
→ IP 변환 X
→ VLAN X
→ 물리 계층에서 신호 처리
```

```text
Repeater
→ 신호 증폭 / 재생

Hub
→ Repeater 기능 포함
```
