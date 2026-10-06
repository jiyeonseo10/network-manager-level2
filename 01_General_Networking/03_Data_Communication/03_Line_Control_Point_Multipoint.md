# 교환 회선 / 전용 회선 / Point to Point / Multi Point / 회선 제어

## 1. 교환 회선

교환 회선은 정보 전송 시 교환기를 사용하여 송수신하는 방식이다.

```text
교환 회선
→ 교환기 사용
→ 필요한 시점에 회선 연결
```

교환 회선은 다음과 같이 나뉜다.

```text
회선 교환
축적 교환
```

사용 형태:

```text
Data 양이 적거나
사용자가 많을 때 사용
```

---

## 2. 전용 회선

전용 회선은 교환기를 사용하지 않고 송신자와 수신자를 직접 연결하는 방식이다.

```text
전용 회선
→ 교환기 사용 X
→ Point to Point 직접 연결
```

사용 형태:

```text
사용자는 적지만
전송할 Data가 많을 때 사용
```

---

# 3. Point to Point

송신자 한 명과 수신자 한 명을 1:1로 연결하는 방식이다.

```text
Point to Point
→ 1 : 1 연결
→ 하나의 통신 회선 사용
```

특징:

```text
전용 회선 사용
안정적인 통신 가능
빠른 Data 전송 가능
```

---

# 4. Multi Point

하나의 회선을 여러 사용자가 공유하는 방식이다.

```text
Multi Point
→ 하나의 회선
→ 여러 사용자
```

회선 제어 방식:

```text
Polling
Selection
```

---

# 5. Point to Point의 회선 제어

Point to Point 방식의 회선 제어 기법은 Contention이다.

```text
Contention
→ 송신자와 수신자가 연결되면 독점 사용
```

```text
송신 요청을 누가 먼저 했는지에 따라
→ 회선 사용권 결정
```

---

# 6. Polling

Polling은 송신할 Data가 있는지를 확인하는 방식이다.

```text
Polling
→ 송신자 단말에
   전송할 Data가 있는지 질문
```

Data가 있으면 전송을 허가한다.

```text
"보낼 Data 있어?"
→ 있으면 전송
```

---

# 7. Selection

Selection은 수신자가 Data를 받을 준비가 되었는지 확인하는 방식이다.

```text
Selection
→ 수신 준비 여부 확인
```

준비가 되어 있으면 송신자가 Data를 전송한다.

```text
"받을 준비 됐어?"
→ 준비됐으면 전송
```

---

# 8. Polling vs Selection

```text
Polling
→ 송신할 Data가 있는지 확인
```

```text
Selection
→ 수신 준비가 되었는지 확인
```

한 줄 암기:

```text
Polling = 보낼 거 있어?
Selection = 받을 준비 됐어?
```

---

# 9. 회선 제어 단계

교재 기준 총 5단계이다.

## 1단계: 회선 연결

```text
송신자와 수신자의 회선을 물리적으로 연결
```

## 2단계: 링크 확립

```text
송신자와 수신자가
Data 전송이 가능한지 확인
```

## 3단계: 메시지 전송

```text
송신자 → 수신자
Data 전송
```

## 4단계: 링크 단절

```text
송신자와 수신자의 Link 종료
```

## 5단계: 회선 절단

```text
물리적인 회선을 절단
→ 통신 종료
```

순서:

```text
회선 연결
→ 링크 확립
→ 메시지 전송
→ 링크 단절
→ 회선 절단
```

---

# 시험 직전 암기

```text
교환 회선
→ 교환기 사용
→ 회선 교환 / 축적 교환
```

```text
전용 회선
→ 교환기 사용 X
→ 직접 연결
→ 사용자는 적고 Data 많을 때
```

```text
Point to Point
→ 1 : 1
→ 안정적
→ 빠름
```

```text
Multi Point
→ 하나의 회선을 여러 사용자가 공유
→ Polling / Selection
```

```text
Contention
→ Point to Point 회선 제어
```

```text
Polling
→ 송신할 Data 있는지 확인
```

```text
Selection
→ 수신 준비 여부 확인
```

```text
회선 제어 5단계

1. 회선 연결
2. 링크 확립
3. 메시지 전송
4. 링크 단절
5. 회선 절단
```

## 자주 헷갈리는 부분

```text
Point to Point
→ 1 : 1

Multi Point
→ 1개의 회선을 여러 사용자가 공유
```

```text
Polling
→ 송신 측 확인

Selection
→ 수신 측 준비 확인
```

```text
링크 단절
→ 논리적 연결 종료

회선 절단
→ 물리적 회선 종료
```
