---
lab:
  "\_\_ title": 'Clean, transform, and load data in Power BI'
  "\_\_ module": 'Clean, transform, and load data in Power BI'
---
# Power BI에서 데이터 정리, 변환 및 로드

## 쿼리 변환 내용 적용

1. 먼저 Product 쿼리의 변환 내용을 적용합니다.

1. RetailPrice, Photo 및 Sales 열을 제거합니다.

1. Channels 열의 데이터 형식을 정수로 변경합니다.

1. 다음과 같이 열 이름을 변경합니다.

    - ProductSKU -> SKU

    - ProductName -> Product

    - ProductCategory -> Category

    - ItemGroup -> Item Group

    - KitType -> Kit Type

1. 다음으로 Sales 쿼리의 변환 내용을 적용합니다.

1. 다음을 제외한 모든 열을 제거합니다.

    - OrderDate

    - ProductID

    - 수량

    - 단가

1. UnitPrice 열의 데이터 형식을 고정 10진수로 변경합니다.

1. UnitPrice 열의 이름을 Unit Price로 바꿉니다.

1. Quantity 및 Unit Price 열을 함께 선택하고 두 열을 곱한 결과를 표시할 새 열을 추가합니다.

1. 새 열의 이름을 Sales로 바꿉니다.

## 쿼리 통합

1. Excel 커넥터를 사용하여 새 쿼리를 만든 후 D:\PL300\Demo\Data\ProductCost.xlsx 파일에 연결합니다.

1. Product 열을 제거합니다.

1. ProductCost 열의 데이터 형식을 고정 10진수로 변경합니다.

1. Product 쿼리를 선택한 다음 SKU 열의 관계를 설정하여 ProductCost 쿼리와 병합합니다.

1. 개인 정보 수준 창에서 D:\의 개인 정보 수준을 조직으로 설정합니다.

1. ProductCost 열(ProductCost 쿼리)을 포함하도록 ProductCost 열을 확장합니다.

1. 새 열의 이름을 Cost로 바꿉니다.

## 데이터 모델에 쿼리 사용 안 함 및 로드

1. 쿼리 창에서 ProductCost 쿼리를 사용하지 않도록 설정합니다.

1. 홈 리본 탭에서 닫기 & 적용 아이콘을 클릭합니다.

1. Power BI Desktop 데이터 창에서 두 테이블을 가리킵니다.

1. Power BI Desktop 파일을 저장합니다.

1. 다음 데모에서 사용할 수 있도록 Power BI Desktop 파일을 열어 둡니다.
