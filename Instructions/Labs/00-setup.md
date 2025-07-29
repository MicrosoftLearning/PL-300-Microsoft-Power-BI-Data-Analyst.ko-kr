---
lab:
  title: 환경 직접 설정
  module: Set up your own environment
---

# 로컬 랩 환경 설정

호스트된 랩 환경에서 이러한 랩을 완료하는 것이 가장 좋습니다. 사용자의 개인 컴퓨터에서 완료하려면 다음 소프트웨어를 설치하여 완료하면 됩니다.

- 모든 설정 및 리소스 파일은 [GitHub에서 다운로드](https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/AllfilesDownload.zip)할 수 있습니다.
  - 'AllFilesDownload' 폴더를 D:/로 추출하고 이름을 'D:\Allfiles\'로 바꿉니다.

***개인 환경 사용 시에는 예기치 않은 대화 상자가 표시되거나 동작이 수행될 수 있습니다. 다양한 로컬 구성이 가능하기 때문에 과정 팀은 사용자 환경에서 발생할 수 있는 문제를 지원할 수 없습니다.***

## Windows 11 사용 지침

> 아래 지침은 Windows 11용입니다. 다른 OS에서 연결해도 동일한 환경이 발생하지 않을 수 있습니다.

### Power BI Desktop

1. Microsoft Store에서 다운로드하여 설치합니다. Microsoft Store에 액세스할 수 없는 경우 [웹](https://www.microsoft.com/download/details.aspx?id=58494)에서 다운로드합니다. Power BI Desktop은 이러한 랩의 기본 애플리케이션입니다.

    - 설치 관리자에서 기본 옵션을 사용합니다.

### Microsoft 365 개발자 계정

일부 연습의 경우 조직 계정으로 Power BI에 로그인해야 합니다. 사용자 고유의 계정을 사용할 수 있지만 액세스 권한이 없는 경우 무료 [Microsoft 365 개발자 계정](https://developer.microsoft.com/microsoft-365/dev-program)을 만들 수 있습니다.

### SQL Server 데이터베이스 엔진

1. 랩은 localhost SQL Server 인스턴스에 연결합니다. 다음 지침은 SQL Server를 설치하고 기본 옵션을 구성하는 데 도움이 됩니다. 데이터베이스 엔진 기능만 설치하면 됩니다.

    - [설치 미디어의 개발자 복사본](https://www.microsoft.com/sql-server/sql-server-downloads?SilentAuth=1&f=255&MSPPError=-2147217396&rtc=1) 무료 다운로드
    - [설치 마법사에서 SQL Server 설치(설치 프로그램)](https://learn.microsoft.com/sql/database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup)

> 로컬 버전을 설치하는 대신 액세스 권한이 있는 경우 기존 SQL Server 인스턴스를 사용할 수 있습니다. 그러나 연결 문자열을 “localhost”에서 인스턴스 이름으로 수정해야 합니다.

### Microsoft Edge

1. 최신 버전의 [Microsoft Edge](https://microsoft.com/edge)를 설치하여 온라인으로 Power BI 서비스에 액세스합니다.
