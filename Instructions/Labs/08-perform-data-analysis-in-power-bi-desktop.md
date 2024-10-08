---
lab:
  title: AI 시각적 개체로 고급 분석 수행
  module: Perform Data Analysis in Power BI
---

# Power BI에서의 데이터 분석 수행

## 랩 사례

이 랩에서는 **판매 탐색** 보고서를 만듭니다.

이 랩에서는 다음 작업을 수행하는 방법을 알아봅니다.

- 애니메이션 분산형 차트 만들기
- 시각적 개체를 사용한 값 예측

**이 랩은 약 30분 정도 소요됩니다.**

## 시작하기

이 연습을 완료하려면 먼저 웹 브라우저를 열고 다음 URL을 입력하여 zip 폴더를 다운로드합니다.

`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/08-perform-data-analysis-in-power-bi-desktop/08-perform-analysis.zip`

**C:\Users\Student\Downloads\08-perform-analysis** 폴더로 폴더를 추출합니다.

1. **08-Starter-Sales Analysis.pbix** 파일을 엽니다.

> ***참고**: **취소**를 선택하여 로그인을 해제할 수 있습니다. 다른 정보 창을 모두 닫습니다. 변경 사항을 적용하라는 메시지가 표시되면 **나중에 적용**을 선택합니다.*

## 애니메이션 분산형 차트 만들기

이 작업에서는 애니메이션을 적용할 수 있는 분산형 차트를 만듭니다.

1. 새 페이지를 만들고 이름을 **분산형 차트**로 지정합니다.

1. 보고서 페이지에 **분산형 차트** 시각적 개체를 추가한 다음 전체 페이지를 채우도록 크기를 조정하여 배치합니다.

    > 필드가 **재생 축** 웰/영역에 추가되면 차트를 애니메이션화할 수 있습니다.

     ![그림 18](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image15.png)

     ![그림 75](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image16.png)

1. 다음 필드를 시각적 개체 웰/영역에 추가합니다.

    > *랩에서는 약식 표기법을 사용하여 필드를 참조합니다. 다음과 같이 표시됩니다. **재판매인** **\|** **비즈니스 유형**. 이 예에서 **Reseller**는 테이블 이름이고 **Business Type**은 필드 이름입니다.*

     - X축: **판매 \| 판매**
     - Y축: **판매 \| 이익률**
     - 범례: **재판매인 \| 비즈니스 유형**
     - 크기: **판매 \| 수량**
     - Play Axis: **날짜 \| 분기**

1. **필터** 창에서 **이 페이지의 필터** 웰/영역에 **제품 \| 범주** 필드를 추가합니다.

1. 필터 카드에서 **자전거**를 기준으로 필터링합니다.

1. 차트에 애니메이션을 적용하려면 왼쪽 하단에서 **재생**을 선택합니다.

    ![그림 41](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image19.png)

1. **FY2018 Q1**부터 **FY2020 Q4**까지의 전체 애니메이션 주기를 봅니다.

    > 분산형 차트에서는 측정값을 동시에 해석할 수 있습니다. 여기에서는 주문 수량, 판매 수익, 이익률을 동시에 해석할 수 있습니다.
    > 
    > 각 거품형은 재판매인 비즈니스 유형을 나타냅니다. 거품형 크기는 증가 또는 감소한 주문 수량을 반영하여 변경됩니다. 수평 이동은 판매 수익의 증가/감소를 나타내며 수직 이동은 수익성의 증가/감소를 나타냅니다.

1. 애니메이션이 중지되면 거품형 중 하나를 선택하여 시간에 따른 추적을 표시합니다.

1. 해당 시점에서 재판매인 유형에 대한 측정값을 설명하는 도구 설명을 표시하려면 거품형 위에 커서를 놓습니다.

1. **필터** 창에서 **Clothing**만을 기준으로 필터링하면 매우 다른 결과가 생성되는 것을 확인할 수 있습니다.

1. Power BI Desktop 파일을 저장합니다.

## 예측 만들기

이 작업에서는 예상되는 향후 판매 수익을 판단하는 예측을 만듭니다.

1. 새 페이지를 추가하고 페이지 이름을 **예측**으로 변경합니다.

1. 보고서 페이지에 **꺾은선형 차트** 시각적 개체를 추가한 다음 전체 페이지를 채우도록 크기를 조정하여 배치합니다.

     ![그림 19](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image21.png)

     ![그림 74](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image22.png)

1. 다음 필드를 시각적 개체 웰/영역에 추가합니다.

     - X축: **날짜 \| 날짜**
     - Y축: **판매 \| 판매**

1. **필터** 창에서 **이 페이지의 필터** 웰/영역에 **날짜 \| 연도** 필드를 추가합니다.

1. 필터 카드에서 2년을 기준으로 필터링합니다. **FY2019** 및 **FY2020**.

    > *시간대에 따라 예측하는 경우 정확하고 안정적인 예측을 생성하려면 적어도 두 개의 주기(연도)의 데이터가 필요합니다.*

1. **이 페이지의 필터** 웰/영역에 **제품 \| 범주** 필드도 추가한 다음, **자전거**를 기준으로 필터링합니다.

1. 예측을 추가하려면 **시각화** 창 아래에서 **Analytics** 창을 선택합니다.

     ![그림 20](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image26.png)

1. **예측** 섹션을 확장합니다.

    > ***예측** 섹션을 사용할 수 없는 경우 시각적 개체를 올바르게 구성하지 않았기 때문일 수 있습니다. 예측은 두 가지 조건이 충족되는 경우에만 사용할 수 있습니다. 축에는 날짜 형식의 단일 필드가 있고 값 필드가 하나만 있어야 합니다.*

1. **예측** 옵션을 **켜기**로 설정합니다.

1. 다음 예측 속성을 구성한 후 **적용**합니다.

    - 단위: **Months**
    - 예측 범위: **1개월**
    - 계절성: **365**
    - 신뢰도 간격: **80%**

    ![그림 52](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image29.png)

1. 줄 시각적 개체에서 예측은 기록 데이터를 벗어나 1개월이 연장된 것을 알 수 있습니다.

    > 회색 영역은 신뢰도를 나타냅니다. 신뢰도 영역이 넓을수록 예측 안정성이 낮아지므로 정확성이 떨어집니다.
    >
    > 주기의 길이(여기에서는 연간)를 알고 있으면 계절성 지점을 입력해야 합니다. 매주(7) 또는 매월(30)일 수도 있습니다.

1. **필터** 창에서 **Clothing**만을 기준으로 필터링하면 다른 결과가 생성되는 것을 확인할 수 있습니다.

## 랩 완료
