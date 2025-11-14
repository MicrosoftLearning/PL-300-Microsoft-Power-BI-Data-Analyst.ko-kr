---
demo:
  title: Power BI에서 행 수준 보안 적용
  module: Secure data access in Power BI
---

# Power BI에서 행 수준 보안 적용

## 모델에 보안 테이블 추가

1. Power BI Desktop에서 Power Query 편집기 창을 엽니다.

1. `D:\Demo\Data\**ManagerCategory**.xlsx` 파일을 기반으로 새 쿼리를 추가합니다.

1. 파일에서**ManagerCategory** 테이블을 사용합니다.

1. **Manager** 열을 제거합니다.

1. 세미콜론 구분 기호로**Category** 열을 여러 행으로 분할합니다(고급 옵션).

1. **Email** 열에서**<ty-johnston@tailspintoys.com>** 값을 MySettings.txt 파일의 받는 사람 계정으로 바꿉니다.

1. 이 사용자는**Collective pitch, Trainer, Warbird**의 3개 제품 범주를 볼 수 있음을 지적합니다.

1. 쿼리를 닫고 적용합니다.

1. 모델 뷰에서**Category** 열의 관계를 설정하여**ManagerCategory**와 Product 테이블 간의 관계를 만듭니다.

1. 교차 필터 방향을 단일(**ManagerCategory**가 Product를 필터링)로 설정합니다.

1. **ManagerCategory** 테이블을 숨깁니다.

## 역할 추가

1. 보고서 뷰에서 역할 관리를 열고**Manager** 역할을 만듭니다.

1. 역할에서**ManagerCategory** 테이블 Email 주소 열을 다음과 같이 필터링합니다.

  ```dax
   [Email] = USERPRINCIPALNAME()
   ```

1. **저장**합니다.

## 역할 유효성 검사

1. 표시 방법을 열고 다음 설정을 구성합니다.

    - 다른 사용자: 선택하고 받는 사람 계정 입력

    - Manager 역할: 검사

1. 필터 시각적 개체에는 3개 제품 범주만 표시됨을 설명합니다.

1. 표시 방법 옵션을 사용하여 보고서를 확인하는 작업을 중지합니다.

1. Power BI Desktop 파일을 저장합니다.

1. Power BI Desktop 파일을 작업 영역에 게시하고 서비스의 의미 체계 모델 및 보고서를 덮어씁니다.

1. Power BI Desktop을 닫습니다.

## 의미 체계 모델 보안 구성

1. 강사용 Power BI 서비스의 탐색 창에서**Sales Analysis** 의미 체계 모델의 보안 페이지를 엽니다.

1. **멤버** 섹션에서 받는 사람 계정(Ty Johnston의 계정)을 입력합니다.

1. 추가 및 저장합니다.

## 앱에서 행 수준 보안 테스트

1. 받는 사람용 Power BI 서비스에서 대시보드(이전 데모에서 열어 둔 대시보드)를 새로 고칩니다.

1. **Profit Margin** 대시보드 타일에서 3개의 제품 범주만 볼 수 있음을 확인합니다.
