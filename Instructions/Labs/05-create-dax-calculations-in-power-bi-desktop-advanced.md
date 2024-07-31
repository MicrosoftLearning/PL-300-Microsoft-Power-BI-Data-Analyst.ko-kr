---
lab:
  title: Power BI Desktop에서 고급 DAX 계산 만들기
  module: Create Model Calculations using DAX in Power BI
---

# Power BI Desktop에서 고급 DAX 계산 만들기

## **랩 사례**

이 랩에서는 필터 컨텍스트 조작을 포함하는 DAX 식을 사용하여 측정값을 만듭니다.

이 랩에서는 다음 작업을 수행하는 방법을 알아봅니다.

- CALCULATE() 함수를 사용하여 필터 컨텍스트를 조작
- 시간 인텔리전스 함수를 사용

**이 랩은 약 45분 정도 소요됩니다.**

## 시작하기

이 연습을 완료하려면 먼저 웹 브라우저를 열고 다음 URL을 입력하여 zip 폴더를 다운로드합니다.


`https://github.com/MicrosoftLearning/PL-300-Microsoft-Power-BI-Data-Analyst/raw/Main/Allfiles/Labs/05-create-dax-calculations-in-power-bi-desktop-advanced/05-advanced-dax.zip`

**C:\Users\Student\Downloads\05-advanced-dax** 폴더로 폴더를 추출합니다.

**05-스타터-영업 분석.pbix** 파일을 엽니다.

> ***참고**: **취소**를 선택하여 로그인을 해제할 수 있습니다. 다른 정보 창을 모두 닫습니다. 변경 사항을 적용하라는 메시지가 표시되면 **나중에 적용**을 선택합니다.*

## 행렬 시각적 개체 만들기

이 작업에서는 새 측정값의 테스트를 지원하는 행렬 시각적 개체를 만듭니다.

1. Power BI Desktop의 **보고서 뷰**에서 새 보고서 페이지를 만듭니다.

1. **3페이지**에서 행렬 시각적 개체를 추가합니다.

    ![그림 13](Linked_image_Files/05-create-dax-calculations-in-power-bi-desktop_image23.png)

1. 전체 페이지를 채우도록 행렬 시각적 개체의 크기를 조정합니다.

1. 행렬 시각적 필드를 구성하려면 **데이터** 창에서 **Region \| Regions** 계층 구조를 끌어서 시각적 개체 안에 놓습니다.

    > 랩에서는 약식 표기법을 사용하여 필드나 계층 구조를 참조합니다. **Region \| Regions과 같이 표시됩니다**.이 예에서 **Region**은 테이블 이름이고 **Regions**은 계층 구조 이름입니다.

1. 값 웰에 **영업 \| 영업** 필드도 추가합니다.

1. 전체 계층을 확장하려면 행렬 시각적 개체의 오른쪽 위에 있는 포크 모양 이중 화살표 아이콘을 두 번 선택합니다.

    ![그림 47](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image11.png)

1. 시각적 개체의 서식을 지정하려면 **시각화** 창에서 **서식** 창을 선택합니다.

    ![그림 14](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image12.png)

1. **검색** 상자에 **레이아웃**을 입력합니다.

1. **레이아웃** 속성을 **테이블 형식**으로 설정합니다.

    ![그림 49](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image14.png)

1. 행렬 시각적 개체에 이제 4개의 열 머리글이 있는지 확인합니다.

    ![그림 50](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image15.png)

    > Adventure Works에서 판매 지역은 그룹, 국가, 지역으로 구성됩니다. 미국을 제외한 모든 국가에는 국가 이름을 따라 명명된 하나의 지역만 있습니다. 미국은 대규모 판매 지역이므로 다섯 개 판매 지역으로 나눠집니다.

이 연습에서는 여러 측정값을 만든 다음 행렬 시각적 개체에 추가하여 테스트합니다.

## 필터 컨텍스트 조작

이 작업에서는 CALCULATE() 함수를 사용하여 필터 컨텍스트를 조작하는 DAX 식으로 여러 측정값을 만듭니다.

> CALCULATE() 함수는 필터 컨텍스트를 조작하는 데 사용되는 강력한 함수입니다. 첫 번째 인수는 식 또는 측정값을 사용합니다(측정값은 단지 명명된 식입니다). 후속 인수를 사용하여 필터 컨텍스트를 수정할 수 있습니다.

1. 다음 식에 따라 **판매** 테이블에 측정값을 추가합니다.

    > **참고**: *사용자의 편의를 위해 이 랩의 모든 DAX 정의는 **C:\Users\Student\Downloads\05-advanced-dax\Snippets.txt** 파일에서 복사할 수 있습니다.*

    ```DAX
    Sales All Region =

    CALCULATE(SUM(Sales[Sales]), REMOVEFILTERS(Region))
    ```

    >
    > REMOVEFILTERS() 함수는 활성 필터를 제거합니다. 아무 인수도 사용하지 않거나 테이블, 열 또는 여러 열을 인수로 사용할 수 있습니다.
    >
    > 이 수식에서 측정값은 수정된 필터 컨텍스트에서 **Sales** 열의 합계를 평가하여 **Region** 테이블의 열에 적용된 필터를 모두 제거합니다.

1. **Sales All Region** 측정값을 행렬 시각적 개체에 추가합니다.

    ![그림 52](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image16.png)

1. **Sales All Region** 측정값은 각 지역, 국가(소계) 및 그룹(소계)의 모든 지역 매출에 대한 합계를 계산합니다.

    새 측정은 아직 유용한 결과를 제공하지 않습니다. 그룹, 국가 또는 지역의 매출이 이 값으로 나눠지면 “총계의 백분율”이라고 하는 유용한 비율이 생성됩니다.

1. **데이터** 창에서 **Sales All Region** 측정이 선택되었는지 확인하고(이 측정을 선택하면 배경이 진한 회색으로 표시됨) 수식 입력줄에서 측정값 이름과 수식을 다음 수식으로 바꿉니다.

    *팁: 기존 수식을 바꾸려면 먼저 코드 조각을 복사합니다. 그런 다음 수식 입력줄 내부를 선택하고 **Ctrl+A**를 눌러 모든 텍스트를 선택합니다. 그런 다음 **Ctrl + V**를 눌러 코드 조각을 붙여넣어 선택한 텍스트를 덮어씁니다. 그런 다음, **Enter** 키를 누릅니다.*

    ```DAX
    Sales % All Region =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region)  
     )  
    )
    ```

    측정값의 이름이 변경되어 업데이트된 수식을 정확하게 반영합니다. DIVIDE() 함수는 **Region** 테이블에 적용된 모든 필터를 제거하는 수정된 컨텍스트의 **Sales** 측정값으로 필터 컨텍스트에 의해 수정되지 않은 **Sales** 측정값을 나눕니다.

1. 행렬 시각적 개체에서 측정값의 이름이 변경되고 각 그룹, 국가 및 지역에 대해 다른 값이 표시된 것을 볼 수 있습니다.

1. **Sales % All Region** 측정값을 소수점 이하 두 자리 백분율로 지정합니다.

1. 행렬 시각적 개체에서 **Sales % All Region** 측정값의 값을 검토합니다.

    ![그림 53](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image17.png)

1. 다음 식을 기반으로 **Sales** 테이블에 다른 측정값을 추가하고 백분율로 서식을 지정합니다.

    ```DAX
    Sales % Country =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region[Region])  
     )  
    )
    ```

1. **Sales % Country** 측정값 수식은 **Sales % All Region** 측정값 수식과 약간 다릅니다.

    *차이점은 **지역** 테이블의 모든 열이 아니라 **지역** 테이블의 **지역** 열에서 필터를 제거하여 분모가 필터 컨텍스트를 수정한다는 것입니다. 즉, 그룹 또는 국가 열에 적용된 필터는 유지됩니다. 그러면 매출을 국가의 백분율로 나타내는 결과가 얻어집니다.*

1. 행렬 시각적 개체에 **Sales % Country** 측정값을 추가합니다.

1. 미국 지역에서만 100%가 아닌 값이 생성됩니다.

    ![그림 54](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image18.png)

    > *미국에만 여러 지역이 있다는 점을 기억하세요. 다른 모든 국가가 100%인 이유는 모두 단일 지역으로 구성되어 있기 때문입니다.*

1. 시각적 개체에서 이 측정값의 가독성을 향상시키기 위해 **Sales % Country** 측정값을 개선된 다음 수식으로 덮어씁니다.

    ```DAX
    Sales % Country =  
    IF(  
     ISINSCOPE(Region[Region]),  
     DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(Region[Region])  
     )  
     )  
    )
    ```

    > *IF() 함수는 ISINSCOPE() 함수를 사용하여 지역 열이 수준 계층 구조의 수준인지 여부를 테스트합니다. True로 설정되면 DIVIDE() 함수를 계산합니다. false인 경우 지역 열이 범위 내에 있지 않기 때문에 빈 값이 반환됩니다.*

1. 이제 지역이 범위 내에 있는 경우에만 **Sales % Country** 측정값이 값을 반환합니다.

    ![그림 55](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image19.png)

1. 다음 식을 기반으로 **Sales** 테이블에 다른 측정값을 추가하고 백분율로 서식을 지정합니다.

    ```DAX
    Sales % Group =  
    DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(  
     Region[Region],  
     Region[Country]  
     )  
     )  
    )
    ```

    > *매출을 그룹의 백분율로 구할 수 있도록 두 개의 열에서 필터를 효과적으로 제거하기 위해 두 개의 필터를 적용할 수 있습니다.*

1. 행렬 시각적 개체에 **Sales % Group** 측정값을 추가합니다.

1. 시각적 개체에서 이 측정값의 가독성을 향상시키기 위해 **Sales % Group** 측정값을 개선된 다음 수식으로 덮어씁니다.

    ```DAX
    Sales % Group =  
    IF(  
     ISINSCOPE(Region[Region])  
     || ISINSCOPE(Region[Country]),  
     DIVIDE(  
     SUM(Sales[Sales]),  
     CALCULATE(  
     SUM(Sales[Sales]),  
     REMOVEFILTERS(  
     Region[Region],  
     Region[Country]  
     )  
     )  
     )  
    )
    ```

1. 이제 지역 또는 국가가 범위 내에 있는 경우에만 **Sales % Group** 측정값이 값을 반환합니다.

1. 모델 뷰에서 3개의 새 측정값을 **Ratios**라는 표시 폴더에 추가합니다.

    ![그림 56](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image20.png)

1. Power BI Desktop 파일을 저장합니다.

**판매** 테이블에 추가된 측정값은 계층적 탐색을 수행하기 위해 수정된 필터 컨텍스트를 갖습니다. 소계 계산을 수행하는 패턴은 필터 컨텍스트에서 일부 열을 제거해야 하고, 총계를 계산하려면 모든 열을 제거해야 합니다.

## YTD 측정값 만들기

이 작업에서는 시간 인텔리전스 함수를 사용하여 YTD(연간 판매) 측정값을 만듭니다.

1. 보고서 뷰의 **2페이지**에서 행렬 시각적 개체에는 행에 연수와 개월이 그룹화된 다양한 측정값이 표시됩니다.

2. 다음 식을 기반으로 하는 **Sales** 테이블에 측정값을 추가하고 소수점 이하 0자리로 지정합니다.

    ```DAX
    Sales YTD =  
    TOTALYTD(SUM(Sales[Sales]), 'Date'[Date], "6-30")
    ```

    > *TOTALYTD() 함수는 지정된 날짜 열에 대한 표현식(이 경우 **영업** 열의 합계)을 평가합니다. 날짜 열은 날짜 테이블로 표시된 날짜 테이블에 속해야 합니다.*
    >
    > 또한 함수는 연도의 마지막 날짜를 나타내는 세 번째 선택적 인수를 사용할 수 있습니다. 이 날짜가 없으면 12월 31일이 연도의 마지막 날짜입니다. Adventure Works의 경우 연도의 마지막 달이 6월이므로 “6-30”이 사용됩니다.

3. 행렬 시각적 개체에 **Sales** 필드와 **Sales YTD** 측정값을 추가합니다.

4. 그러면 해당 연도의 매출이 누적됩니다.

    ![그림 59](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image21.png)

TOTALYTD() 함수는 필터 조작, 특히 시간 필터 조작을 수행합니다. 예를 들어 2017년 9월(회계연도의 세 번째 월)의 YTD 매출을 계산하기 위해 **날짜** 테이블의 모든 필터가 제거되고 연도가 시작하는 날짜 2017년 7월 1일부터 컨텍스트 내 마지막 날짜 2017년 9월 30일까지의 새 필터로 대체됩니다.

*DAX에서는 일반적인 시간 필터 조작을 지원하기 위해 많은 시간 인텔리전스 함수를 사용할 수 있습니다.*

## YoY 증가율 측정값 만들기

이 작업에서는 변수를 사용하여 전년 대비 영업 성장률 측정값을 만듭니다.

> *변수를 사용하면 수식을 단순화할 수 있으며 수식 내에서 논리를 여러 번 사용하는 경우 더 효율적입니다. 변수는 고유한 이름으로 선언되며, 측정값 표현식은 **RETURN** 키워드 뒤에 출력되어야 합니다. 다른 코딩 언어 변수와 달리 DAX 변수는 단일 수식 내에서만 사용할 수 있습니다.*

1. 다음 식을 기반으로 **Sales** 테이블에 다른 측정값을 추가합니다.

    ```DAX
    Sales YoY Growth =  
    VAR SalesPriorYear =  
     CALCULATE(  
     SUM(Sales[Sales]),  
     PARALLELPERIOD(  
     'Date'[Date],  
     -12,  
     MONTH  
     )  
     )  
    RETURN  
     SalesPriorYear
    ```

    > ***SalesPriorYear** 변수에는 PARALLELPERIOD() 함수를 사용하여 필터 컨텍스트의 각 날짜에서 12개월 뒤로 이동하는 수정된 컨텍스트에서 **Sales** 열의 합계를 계산하는 식이 할당됩니다.*

1. 행렬 시각적 개체에 **Sales YoY Growth** 측정값을 추가합니다.

1. 새 측정값은 처음 12개월 동안은 BLANK를 반환합니다(2017 회계연도 이전에 기록된 매출이 없기 때문입니다).

1. **2018년 7월**에 대한 **Sales YoY Growth** 측정값은 **2017년 7월**에 대한 **Sales** 값입니다.

    ![그림 61](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image22.png)

    > *이제 수식의 “어려운 부분”을 테스트했으므로 증가율 결과를 계산하는 최종 수식으로 측정값을 덮어쓸 수 있습니다.*

1. 측정값을 완료하려면 이 수식을 사용하여 **Sales YoY Growth** 측정값을 덮어써 서식을 소수점 이하 두 자리 백분율로 지정합니다.

    ```DAX
    Sales YoY Growth =  
    VAR SalesPriorYear =  
     CALCULATE(  
     SUM(Sales[Sales]),  
     PARALLELPERIOD(  
     'Date'[Date],  
     -12,  
     MONTH  
     )  
     )  
    RETURN  
     DIVIDE(  
     (SUM(Sales[Sales]) - SalesPriorYear),  
     SalesPriorYear  
     )
    ```

1. 수식의 **RETURN** 절에서 변수가 두 번 참조됩니다.

1. **2018 Jul**의 YoY 증가율이 **392.83%** 인지 확인합니다.

    ![그림 62](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image23.png)

    > *YoY 성장 측정을 통해 전년도 같은 기간 동안 매출이 거의 400%(또는 4배) 증가한 것으로 나타납니다.*

1. 모델 뷰에서 두 개의 새 측정값을 **Time Intelligence**라는 표시 폴더에 넣습니다.

    ![그림 63](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image24.png)

## 랩 완료
