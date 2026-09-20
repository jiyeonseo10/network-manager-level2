# PowerShell

네트워크관리사 2급 NOS 파트의 **PowerShell** 내용을 정리한다.

---

## 1. PowerShell 개요

PowerShell은 리눅스에서 사용하던 셸(Shell) 기능을 Windows에서도 사용할 수 있도록 추가된 명령줄 기반 환경이다.

책 기준 특징은 다음과 같다.

- 명령 라인(Command Line) 기반
- 시스템 및 서비스 상태 모니터링 가능
- Microsoft .NET Framework 기반
- 과거 DOS와 호환성이 있어 DOS 명령 사용 가능
- 명령어를 이용해 Windows Server 관리 가능
- Windows 7부터 개인용 PC에도 PowerShell 지원

```text
PowerShell
→ Windows용 셸
→ Command Line 기반
→ .NET Framework 기반
→ DOS 명령 사용 가능
→ Windows Server 관리 가능
→ Windows 7부터 개인용 PC 지원
```

---

## 2. 파이프라인 지원

PowerShell은 파이프라인 문자 `|`를 사용하여 첫 번째 명령의 결과를 다음 명령의 입력으로 전달할 수 있다.

```text
Pipeline |
→ 앞 명령의 결과
→ 다음 명령의 입력으로 전달
```

---

## 3. 자동 완성 기능

PowerShell은 리눅스의 TAB 기능과 같이 자동 완성 기능을 지원한다.

명령어 일부를 입력한 후 `TAB` 키를 사용하여 명령어를 찾을 수 있다.

```text
TAB
→ 명령어 자동 완성
```

---

## 4. 다중 라인 입력

PowerShell에서는 세미콜론 `;`을 사용하여 여러 명령을 순차적으로 실행할 수 있다.

예시:

```powershell
ls;ipconfig
```

```text
;
→ 여러 명령을 순차적으로 실행
```

---

## 5. .NET Framework 기반 기능

PowerShell은 .NET Framework 기반으로 개발되어 동작한다.

책의 예시처럼 변수에 값을 저장하고, 변수 값을 출력하거나 메서드를 사용할 수 있다.

예시 기능:

- 변수 값 지정
- 변수 값 출력
- `ToUpper()` 메서드를 이용한 대문자 변환

```text
.NET Framework
→ 변수 사용
→ 메서드 사용 가능
→ 프로그래밍 언어처럼 활용 가능
```

---

## 6. 시험 직전 암기

```text
PowerShell
→ Windows용 셸
→ 명령줄 기반
→ .NET Framework 기반
→ DOS 명령 사용 가능
→ Windows Server 관리 가능
→ Windows 7부터 개인용 PC 지원

|
→ 파이프라인
→ 앞 명령 결과를 다음 명령 입력으로 전달

TAB
→ 자동 완성

;
→ 여러 명령 순차 실행

.NET Framework
→ 변수 / 메서드 사용 가능
```
