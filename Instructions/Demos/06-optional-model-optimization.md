---
lab:
  "\_\_ title": (Optional) Optimize model performance in Power BI
  "\_\_ module": Optimize model performance in Power BI
---

# (선택 사항) 모델 성능 최적화

## DirectQuery 모델 디자인 검토

> **참고**: 이 데모에서는 다른 Power BI Desktop 파일을 사용합니다.

1. D:\PL300\Demo\Resources\AW Sales Analysis.pbix 파일을 엽니다.

1. 데이터 원본에 연결하라는 메시지가 표시되면 연결을 클릭합니다.

1. 데이터 모델의 오른쪽 아래 모서리에 DirectQuery 테이블이 있음을 언급합니다.

1. D:\PL300\Demo\MySolution 폴더에 Power BI Desktop 파일을 저장합니다.

1. 모델 뷰에서 관련 테이블 2개가 포함된 모델 디자인을 소개합니다.

1. 보고서 뷰에서 회계 연도 슬라이서의 다른 항목을 선택하는 방식으로 보고서와 상호 작용해 봅니다.

1. 임의의 월 열에서 드릴스루하여 주문 세부 정보를 표시합니다.

1. 판매 요약 페이지로 돌아옵니다.

## 쿼리 성능 검토

1. 보기 리본 탭에서 성능 분석기 창을 표시합니다.

1. 시각적 개체를 새로 고친 다음 슬라이서 및 월별 판매 시각적 개체를 확장합니다.

1. DirectQuery 모드를 사용했음을 지적합니다(데이터 원본에서 데이터가 요청됨).

## 이중 스토리지 테이블 구성

1. 모델 뷰에서 Date 테이블을 선택하고 스토리지 모드를 이중으로 선택합니다.

1. 데이터 가져오기가 완료되면 보고서 뷰로 전환하고 성능 분석기 창에서 시각적 개체를 새로 고칩니다.

1. 이제 모델 캐시에서 Date 테이블을 쿼리함을 설명합니다.

## 집계 만들기

1. Power Query 편집기 창의 쿼리 창에서 Reseller Sales 쿼리를 복제합니다.

1. 새 쿼리의 이름을 Reseller Sales Agg로 바꿉니다.

1. 다음과 같이 그룹화 방법 변환을 적용합니다.

    - 그룹화 방법: OrderDate

    - 새 열: Sales. 이 열의 값은 SalesAmount 열 값의 합입니다.

1. 쿼리를 닫고 적용합니다.

1. 모델 뷰에서 Reseller Sales Agg 테이블의 스토리지 모드를 가져오기로 설정합니다.

1. Date 테이블 Date 열에서 Reseller Sales Agg 테이블 OrderDate 열로의 관계를 만듭니다. 이때 열 카디널리티는 Date 테이블이 "1" 쪽인 일대다로 설정됩니다.

1. Reseller Sales Agg 테이블의 집계를 관리합니다.

    - OrderDate: Reseller Sales테이블 OrderDate 열을 기준으로 그룹화합니다.

    - Sales: Reseller Sales 테이블 SalesAmount 열의 값을 합합니다.

1. 이제 집계 테이블이 숨겨졌음을 설명합니다.

1. 보고서 뷰로 돌아와 성능 분석기 창에서 시각적 개체를 새로 고칩니다.

1. 이제 모델 캐시에서 Sales by Month 테이블을 쿼리함을 설명합니다.

1. 임의의 월에서 드릴스루한 다음 데이터 원본에서 테이블의 세부 정보를 DirectQuery로 요청함을 설명합니다.

1. Power BI Desktop 파일을 저장합니다.

1. Power BI Desktop을 닫습니다.

> **참고**: 이 Power BI Desktop 솔루션을 다시 사용하지 않습니다.
