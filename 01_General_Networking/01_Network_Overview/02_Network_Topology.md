# Network Topology

## 1. Network Topology 개요

Network Topology는 Network의 구성 요소인 Link, Node 등을 물리적으로 어떻게 연결하는지를 의미한다.

```text
Network Topology
→ Network 연결 구조
→ Node와 Link의 연결 형태
```

주요 종류:

```text
Tree
Bus
Star
Ring
Mesh
```

---

## 2. Tree Topology

계층형 구조로 Network를 구성하는 방식이다.

```text
Tree
→ 계층 구조
→ 단말 장치 추가가 쉬움
```

### 장점

```text
Network 관리 쉬움
확장 편리
신뢰도 높음
```

### 단점

```text
특정 Node에 Traffic 집중
→ Network 속도 저하
→ 병목 현상 발생 가능
```

---

## 3. Bus Topology

하나의 중심 통신 회선에 여러 정보 단말 장치가 연결되는 구조이다.

```text
Bus
→ 하나의 중심 회선
→ 여러 Node 연결
```

Bus 끝에는 신호 반사를 방지하기 위해 Terminator를 사용한다.

```text
Terminator
→ 신호 반사 방지
```

### 장점

```text
설치 비용 적음
신뢰성 우수
구조 간단
Node 추가 쉬움
```

### 단점

```text
Data 증가
→ 병목 현상 발생

회선 장애
→ 전체 Network 영향
```

---

## 4. Star Topology

모든 정보 단말 장치가 중앙 장치에 연결되는 구조이다.

```text
Star
→ 중앙 Node 중심
→ 모든 Node가 중앙 장치에 연결
```

### 장점

```text
고속 Network에 적합
Node 추가 쉬움
Error 탐지 쉬움
개별 Node 장애 시 Network 사용 가능
```

### 단점

```text
중앙 Node 장애
→ 전체 Network 사용 불가

설치 비용 높음
Node 증가
→ Network 복잡도 증가
```

---

## 5. Ring Topology

인접한 정보 단말 장치가 원형으로 연결되는 구조이다.

```text
Ring
→ 인접 Node 연결
→ 원형 구조
→ Token Ring에서 사용
```

### 장점

```text
Node 수 증가해도 Data 손실 없음
충돌 발생하지 않음
경제적 Network 구성 가능
```

### 단점

```text
Network 구성 변경 어려움

회선 장애
→ 전체 Network 사용 불가
```

---

## 6. Mesh Topology

모든 정보 단말 장치가 통신 회선을 통해 연결되는 구조이다.

```text
Mesh
→ 여러 경로
→ 이중화
```

한 통신 회선에 장애가 발생해도 다른 경로를 통해 통신할 수 있다.

### 장점

```text
완벽한 이중화
장애 시 다른 경로 사용 가능
많은 양의 Data 송수신 가능
```

### 단점

```text
Network 구축 비용 높음
운영 비용 높음
```

---

# 7. Topology 비교

| Topology | 핵심 특징 | 단점 |
|---|---|---|
| Tree | 계층 구조, 확장 쉬움 | Traffic 집중 시 병목 |
| Bus | 하나의 중심 회선 | 장애 시 전체 영향 |
| Star | 중앙 Node 중심 | 중앙 Node 장애 시 전체 장애 |
| Ring | 원형, 충돌 없음 | 회선 장애에 약함 |
| Mesh | 다중 경로, 이중화 | 구축/운영 비용 높음 |

---

# 시험 직전 암기

```text
Tree
→ 계층형
→ 확장/관리 쉬움
→ 병목 가능
```

```text
Bus
→ 하나의 회선
→ Terminator 사용
→ 회선 장애 시 전체 영향
```

```text
Star
→ 중앙 장치
→ 개별 Node 장애는 괜찮음
→ 중앙 Node 장애는 전체 마비
```

```text
Ring
→ 원형
→ Token Ring
→ 충돌 없음
→ 회선 장애 시 전체 사용 불가
```

```text
Mesh
→ 여러 경로
→ 이중화
→ 장애 대응 우수
→ 비용 높음
```

## 자주 헷갈리는 부분

```text
Tree
→ Traffic 집중 → 병목

Bus
→ Terminator

Star
→ 중앙 Node 장애가 핵심

Ring
→ 충돌 없음

Mesh
→ 장애 대응 좋지만 비용 큼
```
