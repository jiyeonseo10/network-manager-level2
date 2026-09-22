# IIS Web Server Installation

네트워크관리사 2급 NOS 파트의 **IIS 웹 서버 설치** 내용을 정리한다.

---

## 1. IIS 웹 서버 개요

Windows Server에서는 **IIS(Internet Information Server)** 라는 웹 서버를 설치해서 사용할 수 있다.

IIS는 Microsoft의 웹 서버 프로그램으로 다음과 같은 특징이 있다.

- 웹 서버 역할 수행
- ASP(Active Server Page) 스크립트 지원
- .NET Framework 기반으로 개발
- Windows 환경에서 사용

```text
IIS
→ Internet Information Server
→ Microsoft 웹 서버
→ Windows에서 사용
→ ASP 지원
→ .NET Framework 기반
```

---

## 2. 웹 서버

웹 브라우저는 HTML 문서를 보여주는 프로그램이다.

웹 서버는 웹 브라우저와 HTML 형식의 문서를 송수신하는 프로그램이며 이때 사용하는 통신 프로토콜은 **HTTP**이다.

웹 서버는 여러 사용자의 웹 브라우저 연결을 관리해야 하므로 세션(Session)도 관리한다.

대표적인 웹 서버는 다음과 같다.

| 운영체제 | 웹 서버 |
|---|---|
| Windows | IIS |
| Linux | Apache |

```text
웹 브라우저
→ HTML 문서 표시

웹 서버
→ HTML 문서 송수신
→ HTTP 사용
→ 세션 관리

Windows → IIS
Linux → Apache
```

---

## 3. IIS 웹 서버 설치

Windows Server의 **서버 관리자(Server Manager)** 를 이용하여 IIS를 설치할 수 있다.

설치 과정은 다음과 같다.

```text
서버 관리자
→ 관리
→ 역할 및 기능 추가
→ 역할 기반 또는 기능 기반 설치
→ 대상 서버 선택
→ 웹 서버(IIS) 선택
```

---

## 4. 서버 역할 선택

서버 역할 목록에서 **웹 서버(IIS)** 를 선택하면 IIS를 설치할 수 있다.

필요한 경우 같은 화면에서 다음과 같은 서버 역할도 선택할 수 있다.

- Active Directory
- DHCP 서버
- DNS 서버

```text
IIS 설치
→ 서버 역할에서 웹 서버(IIS) 선택
```

---

## 5. ASP.NET 지원

ASP를 지원하기 위해서는 기능 선택 화면에서 **ASP.NET**을 선택한다.

```text
ASP 지원
→ ASP.NET 선택
```

---

## 6. IIS 역할 서비스

IIS 역할 서비스에서 웹 서버에 필요한 기능을 선택할 수 있다.

책에서 제시된 주요 기능은 다음과 같다.

- 정적 콘텐츠
- 기본 문서
- 디렉터리 검색
- HTTP 오류
- Windows 인증
- 요청 필터링
- 정적 콘텐츠 압축
- IIS 관리 콘솔

FTP 서버를 구축하려면 역할 서비스에서 **FTP 서버**를 선택한다.

```text
웹 서버 기능
→ 필요한 IIS 역할 서비스 선택

FTP 구축
→ FTP 서버 선택
```

---

## 7. IIS 설치 확인

IIS 설치가 완료되면 Windows의 앱 목록에서 IIS 인터넷 정보 서비스를 확인할 수 있다.

웹 브라우저에서 다음 주소로 접속한다.

```text
localhost
```

또는

```text
127.0.0.1
```

IIS 기본 홈페이지가 정상적으로 나타나면 IIS 웹 서버가 정상적으로 설치된 것이다.

```text
localhost
= 127.0.0.1

IIS 기본 페이지 표시
→ IIS 정상 설치
```

---

## 8. 시험 직전 암기

```text
IIS
→ Internet Information Server
→ Microsoft 웹 서버
→ Windows에서 사용
→ ASP 지원
→ .NET Framework 기반

웹 서버
→ HTML 문서 송수신
→ HTTP 사용
→ 세션 관리

Windows 웹 서버
→ IIS

Linux 웹 서버
→ Apache

IIS 설치
→ 서버 관리자
→ 관리
→ 역할 및 기능 추가
→ 역할 기반 또는 기능 기반 설치
→ 웹 서버(IIS) 선택

ASP 지원
→ ASP.NET 선택

FTP 구축
→ FTP 서버 선택

설치 확인
→ localhost
→ 127.0.0.1
→ IIS 기본 페이지가 나오면 정상
```
