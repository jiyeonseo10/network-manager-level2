# NTFS File System

네트워크관리사 2급 NOS 파트의 **NTFS 파일 시스템** 내용을 정리한다.

---

## 1. NTFS 파일 시스템 개요

NTFS 파일 시스템은 기존 FAT(File Allocation Table) 파일 시스템을 개선하고,
윈도우 서버용으로 사용하기 위해 개발된 파일 시스템이다.

---

## 2. NTFS 파일 시스템의 특징

| 기능 | 설명 |
|---|---|
| USN Journal | 파일 시스템 변경 내용을 기록하여 복구(Rollback) 가능 |
| ADS | 다중 데이터 스트림 지원 |
| Sparse File | 데이터 대부분이 0일 경우 실제 데이터 기록 없이 정보만 기록 |
| 파일 압축 | LZ77의 변형된 데이터 압축 알고리즘 지원 |
| VSS | 덮어쓰기 파일과 디렉토리의 백업을 유지하고 복구 지원 |
| EFS | 대칭키 기반으로 파일 데이터 암호화 |
| Quotas | 사용자별 디스크 사용 용량 제한 |
| Unicode | 다국어 지원 |
| 동적 Bad 클러스터 할당 | Bad Sector가 발생한 클러스터 자동 재할당 |
| 대용량 지원 | 2 Tera Byte가 넘는 대용량 볼륨 지원 |

---

## 3. USN Journal

**USN = Update Sequence Number Journal**

- 저널링 기능 제공
- 파일 시스템 변경 내용을 기록
- 변경 내용을 이용하여 복구(Rollback) 가능

### 핵심

```text
USN Journal
→ 변경 내용 기록
→ Rollback 가능
