---
demo:
  course: 'PL-300, DP-605'
  title: Power BI에서 DAX를 사용하여 측정값 만들기
  module: Create measures using DAX in Power BI
---
# Power BI에서 DAX를 사용하여 측정값 만들기

> **팁**: 모든 계산은 D:\Allfiles\Demo\Resources\Snippets-Demo-05.txt 파일에서 복사할 수 있습니다.

## 계산된 테이블 만들기

1. 다음 식을 사용하여 계산된 테이블을 만듭니다.

```dax
Date = CALENDARAUTO()
```

1. 데이터 뷰로 전환하여 날짜 열 1개가 있는 테이블을 검토합니다.

계산 열 만들기

1. Date 테이블에 계산된 열을 추가합니다.

```dax
Year = "CY" & YEAR('Date'[Date])
```

1. Date 테이블에 계산된 열을 하나 더 추가합니다.

```dax
Month = FORMAT('Date'[Date], "YYYY-MM")
```

1. 모델 뷰에서 Date 테이블 Date 열을 Sales 테이블 OrderDate 열로 끌어 관계를 만듭니다.

1. Sales 테이블 OrderDate 열을 숨깁니다.

1. Date 테이블에서 Year 및 Month 수준을 사용하여 Calendar 계층 구조를 만듭니다.

1. 보고서 뷰에서 Date 열을 사용하여 Date 테이블을 날짜 테이블로 표시합니다.

1. 행렬 시각적 개체에서 Products 계층 구조를 제거한 후 Calendar 계층 구조로 바꿉니다.

1. Sales 테이블에 계산된 열을 추가합니다.

```dax
Cost = 'Sales'[Quantity] * RELATED('Product'[Cost])
```

1. Cost 열의 서식을 소수점 두 자리로 지정합니다.

## 빠른 측정 만들기

1. Profit 열의 값에서 Cost 열의 값을 빼는 빠른 측정을 Sales 테이블에 추가합니다.

1. 측정 이름을 Profit으로 바꿉니다.

1. 측정에서는 모델에 데이터를 저장하지 않음을 설명합니다.

일반 측정 만들기

1. Sales 테이블에 측정을 추가합니다.

```dax
Profit Margin = DIVIDE([Profit], SUM('Sales'[Sales]))
```

1. Profit Margin 열의 서식을 백분율로 지정합니다.

1. Sales 테이블에 다른 측정을 추가합니다.

```dax
Sales YTD = TOTALYTD(SUM('Sales'[Sales]), 'Date'[Date])
```

1. Sales YTD 열의 서식을 소수점 두 자리로 지정합니다.

## 행렬 시각적 개체를 사용하여 계산 유효성 검사

1. 행렬 시각적 개체에 Cost, Profit, Profit Margin 및 Sales YTD 필드를 추가합니다.

1. Power BI Desktop 파일을 저장합니다.

1. 이후 데모에서 사용할 수 있도록 Power BI Desktop 파일을 열어 둡니다.
