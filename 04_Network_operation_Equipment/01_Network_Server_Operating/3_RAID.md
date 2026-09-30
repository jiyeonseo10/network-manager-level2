# RAID

## 1. RAID 개요

RAID는 **Redundant Array of Independent Disks**이다.

여러 개의 디스크를 하나의 배열(Array) 구조로 구성하여 다음 효과를 얻는다.

```text
RAID
→ 고용량
→ 고성능
→ 고가용성
```

데이터를 여러 디스크에 분산 저장하여 동시에 접근할 수 있고,
병렬 데이터 채널을 통해 데이터 전송 시간을 줄일 수 있다.

---

## 2. RAID 특징

```text
여러 개의 Hard Disk
→ 하나의 Array로 관리

논리적으로
→ 하나의 Disk처럼 보임
```

특징:

```text
Disk 장애 발생
→ Backup Disk를 이용해 복구
→ 가용성 향상
```

데이터를 중복 저장할수록 더 많은 Disk가 필요하지만 장애 복구가 쉬워진다.

---

# 3. RAID 0

RAID 0은 **Striping** 방식이다.

```text
RAID 0
→ 최소 2개의 Disk
→ 데이터를 나누어 저장
→ 중복 저장 없음
```

장점:

```text
데이터 분산 저장
→ I/O 성능 향상
```

단점:

```text
복구 기능 없음
→ Disk 장애 발생 시 복구 불가
```

핵심:

```text
RAID 0
→ Striping
→ 성능 좋음
→ 복구 불가
```

---

# 4. RAID 1

RAID 1은 **Mirroring** 방식이다.

```text
RAID 1
→ 동일한 데이터를 여러 Disk에 완전히 이중화
```

장점:

```text
Disk 장애 발생
→ 복구 가능

Read / Write 병렬 실행
→ 속도 향상
```

단점:

```text
동일 데이터 중복 저장
→ 비용 많이 발생
```

핵심:

```text
RAID 1
→ Mirroring
→ 복구 가능
→ 비용 큼
```

---

# 5. RAID 2

RAID 2는 **Hamming Code ECC**를 사용한다.

```text
RAID 2
→ Hamming Code
→ ECC 사용
```

특징:

```text
복구용 ECC 정보를 별도 Disk에 저장
→ Disk 오류 발생 시 데이터 재생성
```

핵심:

```text
RAID 2
→ Hamming Code
→ ECC
```

---

# 6. RAID 3

RAID 3은 **Parity ECC**를 사용한다.

```text
RAID 3
→ Byte 단위 I/O
→ Parity 정보를 별도 Disk에 저장
```

특징:

```text
1개 Disk 장애
→ Parity를 이용하여 복구 가능
```

장점:

```text
RAID 0 방식의 Striping
→ I/O 성능 향상
```

단점:

```text
Parity 계산
+
Parity Disk 저장

→ Write 성능 저하
```

핵심:

```text
RAID 3
→ Byte 단위
→ 별도 Parity Disk
```

---

# 7. RAID 4

RAID 4도 Parity 정보를 별도 Disk에 저장한다.

```text
RAID 4
→ Block 단위 I/O
→ Parity 별도 Disk
```

특징:

```text
데이터
→ Block 단위로 분산 저장

1개 Disk 장애
→ Parity로 복구 가능
```

RAID 3과의 차이:

```text
RAID 3
→ Byte 단위

RAID 4
→ Block 단위
```

---

# 8. RAID 5

RAID 5는 **Parity 분산 저장** 방식이다.

```text
RAID 5
→ Parity를 여러 Disk에 분산 저장
```

특징:

```text
분산 Parity
→ 안정성 향상
```

필요 Disk:

```text
최소 3개
→ 일반적으로 4개로 구성
```

핵심:

```text
RAID 5
→ 분산 Parity
→ 최소 3개 Disk
```

---

# 9. RAID 6

RAID 6은 RAID 5의 안정성을 더 높인 방식이다.

```text
RAID 6
→ RAID 5 기반
→ Parity 다중화
```

특징:

```text
복수의 Parity 저장
→ 추가 Disk 장애에도 대응
```

교재 설명:

```text
대용량 System에서
Disk 복구 도중 추가 장애가 발생할 경우의 문제를 해결
```

핵심:

```text
RAID 6
→ Parity 다중화
→ RAID 5보다 안정성 향상
```

---

# 10. RAID 비교

| RAID | 핵심 방식 | 복구/특징 |
|---|---|---|
| RAID 0 | Striping | 복구 불가 |
| RAID 1 | Mirroring | 복구 가능, 비용 큼 |
| RAID 2 | Hamming Code ECC | ECC 사용 |
| RAID 3 | Byte 단위 + 별도 Parity | 1개 Disk 장애 복구 |
| RAID 4 | Block 단위 + 별도 Parity | 1개 Disk 장애 복구 |
| RAID 5 | 분산 Parity | 최소 3개 Disk |
| RAID 6 | Parity 다중화 | 추가 Disk 장애 대응 |

---

# 시험 직전 암기

```text
RAID 0
→ Striping
→ 최소 2개
→ 복구 불가
```

```text
RAID 1
→ Mirroring
→ 완전 이중화
→ 복구 가능
→ 비용 큼
```

```text
RAID 2
→ Hamming Code
→ ECC
```

```text
RAID 3
→ Byte 단위
→ 별도 Parity Disk
```

```text
RAID 4
→ Block 단위
→ 별도 Parity Disk
```

```text
RAID 5
→ Parity 분산 저장
→ 최소 3개 Disk
```

```text
RAID 6
→ Parity 다중화
→ 추가 장애 대응
```

## 자주 헷갈리는 부분

```text
RAID 0
→ 빠름
→ 복구 X
```

```text
RAID 1
→ Mirroring
→ 같은 데이터 복제
```

```text
RAID 3
→ Byte

RAID 4
→ Block
```

```text
RAID 5
→ Parity 분산

RAID 6
→ Parity 다중화
```
