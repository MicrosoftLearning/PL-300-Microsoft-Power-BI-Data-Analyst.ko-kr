---
lab:
  title: Power BI Desktop에서 데이터 로드
  module: '3 - Clean, Transform, and Load Data in Power BI'
---

# Power BI Desktop에서 데이터 로드

**이 랩의 예상 완료 시간은 45분입니다.**

이 랩에서는 이전 랩에서 만든 각 쿼리에 변환을 적용합니다. 그런 다음에는 쿼리를 적용하여 각 항목을 데이터 모델에 테이블로 로드합니다.

이 랩에서는 다음 작업을 수행하는 방법을 알아봅니다.

- 다양한 변환 적용
- 쿼리를 적용하여 데이터 모델에 로드

## **랩 사례**

이 랩은 데이터 준비부터 보고서 및 대시보드로 게시에 이르기까지 전체 사례로 고안된 랩 시리즈 중 하나입니다. 어떤 순서로든 랩을 완료할 수 있습니다. 그러나 여러 랩을 진행하려는 경우 다음 순서를 따르는 것이 좋습니다.

1. Power BI Desktop에서 데이터 준비
1. **Power BI Desktop에서 데이터 로드**
1. Power BI에서 데이터 모델 디자인
1. Power BI Desktop DAX 계산 만들기
1. Power BI Desktop 고급 DAX 계산 만들기
1. Power BI Desktop 보고서 디자인
1. Power BI Desktop 보고서 향상
1. Power BI에서의 데이터 분석 수행
1. Power BI 대시보드 만들기
1. 행 수준 보안 적용

## **연습 1: 데이터 로드**

이 연습에서는 이전 랩에서 만든 각 쿼리에 변환을 적용합니다.

### **작업 1: 시작하기**

이 작업에서는 랩에 대한 환경을 설정합니다.

*중요: 동일한 VM에서 이전 랩을 완료한 경우 다음 작업으로 건너뜁니다.*

1. Power BI Desktop을 엽니다.
    
    *팁: 기본적으로 시작 대화 상자가 Power BI Desktop 앞에 열립니다. 로그인을 선택한 다음 팝업을 닫을 수 있습니다.*

    ![Power BI Desktop 아이콘](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. 시작 Power BI Desktop 파일을 열려면 **파일 > 보고서 열기 > 보고서 찾아보기를** 선택합니다.

1. **열기** 창에서 **D:\PL300\Labs\02-load-data-with-power-query-in-power-bi-desktop\Starter** 폴더로 이동하고 **Sales Analysis** 파일을 엽니다.

1. 열려 있는 정보 창을 모두 닫습니다.

1. 리본 아래에서 노란색 경고 메시지를 확인합니다. 

    *이 메시지는 쿼리가 모델 테이블로 로드에 적용되지 않았다는 사실을 경고합니다. 이 랩의 뒷부분에서 쿼리를 적용합니다.*
    
    경고 메시지를 해제하려면 노란색 경고 메시지의 오른쪽에 있는 **X**를 선택합니다.

1. 파일의 복사본을 만들려면 **파일 > 다른 이름으로 저장으로** 이동하여 **D:\PL300\MySolution** 폴더에 저장합니다.

1. 변경 내용을 적용할지 묻는 프롬프트가 표시되면 **나중에 적용**을 선택합니다.

### **작업 2: Salesperson 쿼리 구성**

이 작업에서는 Power Query 편집기 사용하여 **Salesperson** 쿼리를 구성합니다.

*중요: 열 이름을 바꿀 때는 반드시 설명을 정확하게 따라야 합니다.*

1. **Power Query 편집기** 창을 열려면 **홈** 리본 탭의 **쿼리** 그룹 내에서 **데이터 변환** 아이콘을 선택합니다.

     ![홈 리본 메뉴의 데이터 변환](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image10.png)

1. **파워 쿼리 편집기** 창의 **쿼리** 창에서 **DimEmployee** 쿼리를 선택합니다.

     ![그림 1](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image11.png)

1. 쿼리 이름을 바꾸려면 (오른쪽에 있는) **쿼리 설정** 창의 **이름** 상자에서 텍스트를 **Salesperson**으로 바꾸고 **Enter**키를 누릅니다. 그런 다음 **, 쿼리** 창에서 이름이 업데이트되었는지 확인합니다.
    
    *쿼리 이름은 모델 테이블 이름을 결정합니다. 간결하고 사용자에게 친숙한 이름을 정의하는 것이 좋습니다.*

1. 특정 열을 찾으려면 **홈** 리본 탭에서 **열 관리** 아래쪽 화살표를 선택하고 **열 선택** 아래쪽 화살표를 선택한 다음 **열로 이동을** 선택합니다.
    
    *열로 이동은 많은 열이 있는 유용한 기능입니다. 그렇지 않으면 찾기 열을 가로로 스크롤할 수 있습니다.*

     ![열 관리 > 열 선택 > 열로 이동](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image13.png)

1. **열로 이동** 창에서 열 이름으로 목록을 정렬하려면 **AZ** 정렬 단추를 선택한 다음 **이름** 및 **SalesPersonFlag를** 선택합니다. **확인**을 클릭합니다.

     ![열 정렬 옵션으로 이동](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image14.png)

1. **SalesPersonFlag** 열 머리글을 선택한 다음 아래쪽 화살표, **FALSE**를 차례로 선택하고 **확인을** 클릭합니다.
    
    *이 작업은 행을 필터링하여 영업 사원인 직원만 검색합니다.*

1. **쿼리 설정** 창의 **적용된 단계** 목록에 **필터링된 행** 단계가 추가됩니다.
    
    *만드는 각 변환은 다른 단계 논리로 결과를 생성합니다. 단계를 편집하거나 삭제할 수 있습니다. 쿼리 변환의 해당 단계에서 쿼리 결과를 미리 보는 단계를 선택할 수도 있습니다.*

     ![적용된 단계](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image17.png)

1. 열을 제거하려면 **홈** 리본 탭에서 **열 관리** 그룹을 선택하고 **열 선택 아이콘을 선택합니다** .

1. **열 선택** 창에서 모든 열을 선택 취소하려면 **(모든 열 선택)** 항목을 선택 취소합니다.

1. 다음 6개 열을 선택하여 열을 포함합니다.

    - EmployeeKey
    - EmployeeNationalIDAlternateKey
    - FirstName
    - LastName
    - Title
    - EmailAddress

1. **적용된 단계** 목록에서 다른 쿼리 단계가 추가됩니다.

     ![다른 열 제거 단계](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image21.png)

1. 단일 이름 열을 만들려면 먼저 **FirstName** 열 머리글을 선택합니다. **Ctrl** 키를 누른 상태에서 **LastName** 열을 선택합니다.

     ![두 열을 다중 선택하여 단일 열 만들기](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image22.png)

1. 선택한 열 헤더 중 하나를 마우스 오른쪽 단추로 클릭한 다음 컨텍스트 메뉴에서 **열 병합**을 선택합니다.
    
    대부분의 일반적인 변환은 열 머리글을 마우스 오른쪽 단추로 클릭한 다음, 컨텍스트 메뉴에서 선택하면 적용할 수 있습니다. 하지만 리본에서 더 많은 변환을 사용할 수 있습니다.

1. **열 병합** 창의 **구분 기호** 드롭다운 목록에서 **공백을**선택합니다.

1. **새 열 이름** 상자에서 텍스트를 **Salesperson**으로 바꿉니다.

1. **EmployeeNationalIDAlternateKey** 열의 이름을 바꾸려면 **EmployeeNationalIDAlternateKey** 열 머리글을 두 번 클릭하고 텍스트를 **EmployeeID**로 바꾼 다음 Enter 키를 누릅니**다**.

1. 이전 단계를 사용하여 **EmailAddress** 열의 이름을 **UPN**으로 변경합니다.
    
    *UPN은 User Principal Name(사용자 계정 이름)의 약자입니다.*

1. 왼쪽 아래 상태 표시줄에서 쿼리에 열이 5개, 행이 18개 있는지 확인합니다.

### **작업 3: SalespersonRegion 쿼리 구성**

이번 작업에서는 **SalespersonRegion** 쿼리를 구성합니다.

1. **쿼리** 창에서 **DimEmployeeSalesTerritory** 쿼리를 선택합니다.

1. **쿼리 설정** 창에서 쿼리 이름을 **SalespersonRegion**으로 바꿉니다.

1. 마지막 열 2개를 제거하기 위해 먼저 **DimEmployee** 열 머리글을 선택합니다.

1. **Ctrl** 키를 누른 상태에서 **DimSalesTerritory** 열 머리글을 선택합니다.

1. 선택한 열 헤더 중 하나를 마우스 오른쪽 단추로 클릭한 다음 컨텍스트 메뉴에서 **열 제거**를 선택합니다.

1. 상태 표시줄에서 쿼리에 두 개의 열과 39개의 행이 있는지 확인합니다.

### **작업 4: Product 쿼리 구성**

이번 작업에서는 **Product** 쿼리를 구성합니다.

*중요: 자세한 지침이 이미 제공된 경우 랩 단계에서는 보다 간결한 지침을 제공합니다. 자세한 지침이 필요한 경우 이전 작업의 단계를 다시 참조할 수 있습니다.*

1. **DimProduct 쿼리를** 선택하고 쿼리 이름을 Product로 바꿉**니다**.

1. **FinishedGoodsFlag** 열의 위치를 찾은 다음, 열을 필터링하여 완제품인(즉 TRUE인) 제품을 검색합니다.

1. 다음을 **제외한** 모든 열을 제거합니다.

    - ProductKey
    - EnglishProductName
    - StandardCost
    - Color
    - DimProductSubcategory

1. **DimProductSubcategory** 열은 관련 테이블을 나타냅니다(**값** 링크가 포함됨).

1. **DimProductSubcategory** 열 머리글의 열 이름 오른쪽에서 확장 단추를 선택합니다.

    ![열 확장 아이콘](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image31.png)

1. 열의 전체 목록을 참조한 다음 **, 모든 열 선택** 상자를 선택하여 모든 열의 선택을 취소합니다.
2. **EnglishProductSubcategoryName** 및 **DimProductCategory를** 선택하고 **확인을** 선택하기 전에 **원래 열 이름을 접두사로 사용** 확인란의 선택을 취소합니다.
    
    두 열을 선택하면 변환이 **DimProductSubcategory** 테이블에 대한 조인에 적용되어 두 열이 포함됩니다. **DimProductCategory** 열은 데이터 원본의 또 다른 관련 테이블입니다.
    
    쿼리 열 이름은 언제나 고유해야 합니다. 이 체크박스를 선택한 상태로 유지하면 각 열의 이름에 확장된 열 이름이 접두사로 추가됩니다(이 경우 **DimProductSubcategory**). 선택한 열 이름이 **제품** 쿼리의 열 이름과 충돌하지 않음이 확인되었으므로 옵션은 선택 취소했습니다.

1. 변환 결과로 두 개의 열이 추가되고 두 **DimProductSubcategory** 열이 제거된 것을 알 수 있습니다.

1. **DimProductCategory** 열을 확장하고 수강생들에게 **EnglishProductCategoryName** 열만 설명합니다.

1. 다음 네 가지 열의 이름을 바꿉니다.

    - **EnglishProductName**을 **Product**로
    - **StandardCost**를 **Standard Cost**로(공백 포함)
    - **EnglishProductSubcategoryName**을 **Subcategory**로
    - **EnglishProductCategoryName**을 **Category**로

1. 상태 표시줄에서 쿼리에 열이 6개, 행이 397개 있는지 확인합니다.

### **작업 5: Reseller 쿼리 구성**

이 작업에서는 **재판매** 인 쿼리를 구성합니다.

1. **DimReseller** 쿼리를 선택하고 이름을 **Reseller**로 바꿉니다.

1. 다음을 **제외한** 모든 열을 제거합니다.

    - ResellerKey
    - BusinessType
    - ResellerName
    - DimGeography

1. **DimGeography** 열을 확장하여 다음 세 개의 열**만** 포함합니다.

    - City
    - StateProvinceName
    - EnglishCountryRegionName

1. **비즈니스 유형** 열 머리글에서 아래쪽 화살표를 선택한 다음 고유한 열 값을 검토하고 **Warehouse** 및 **Ware House** 값을 모두 확인합니다.

1. **비즈니스 유형** 열 헤더를 마우스 오른쪽 단추로 클릭한 다음 **값 바꾸기**를 선택합니다.

1. **값 바꾸기** 창에서 다음 값을 구성합니다.

    - **찾을 값** 상자에 **Ware House**를 입력
    - **바꿀 항목** 상자에 **Warehouse**를 입력

     ![값 바꾸기 대화 상자](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image40.png)

1. 다음 네 가지 열의 이름을 바꿉니다.

    - **BusinessType**을 **Business Type**으로(공백 포함)
    - **ResellerName**을 **Reseller**로
    - **StateProvinceName**을 **State-Province**로
    - **EnglishCountryRegionName**을 **Country-Region**으로

1. 상태 표시줄에서 쿼리에 6개의 열과 701개의 행이 있는지 확인합니다.

### **작업 6: Region 쿼리 구성**

이번 작업에서는 **Region** 쿼리를 구성합니다.

1. **DimSalesTerritory 쿼리를** 선택하고 쿼리 이름을 **Region**으로 바꿉니다.

1. 값 0(영)을 제거하려면 **SalesTerritoryAlternateKey** 열에 필터를 적용합니다.
    
    *이렇게 하면 한 행이 제거됩니다.*

1. 다음을 **제외한** 모든 열을 제거합니다.

    - SalesTerritoryKey
    - SalesTerritoryRegion
    - SalesTerritoryCountry
    - SalesTerritoryGroup

1. 다음 세 가지 열의 이름을 바꿉니다.

    - **SalesTerritoryRegion**을 **Region**으로
    - **SalesTerritoryCountry**를 **Country**로
    - **SalesTerritoryGroup**을 **Group**으로

1. 상태 표시줄에서 쿼리에 열이 4개, 행이 10개 있는지 확인합니다.

### **작업 7: Sales 쿼리 구성**

이 작업에서는 **Sales** 쿼리를 구성합니다.

1. **FactResellerSales 쿼리를** 선택하고 **이름을 Sales**로 바꿉니다.

1. 다음을 **제외한** 모든 열을 제거합니다.

    - SalesOrderNumber
    - OrderDate
    - ProductKey
    - ResellerKey
    - EmployeeKey
    - SalesTerritoryKey
    - OrderQuantity
    - UnitPrice
    - TotalProductCost
    - SalesAmount
    - DimProduct
        
        *참고: **Power BI Desktop 랩의 데이터 준비에서** **FactResellerSales** 행의 작은 비율에 **TotalProductCost** 값이 누락된 것을 기억할 수 있습니다. **DimProduct** 열은 누락된 값을 수정하는 데 도움이 되도록 제품 표준 비용 열을 검색하기 위해 포함되었습니다.*

1. **DimProduct** 열을 확장한 다음 모든 열을 선택 취소하고 **StandardCost** 열만 포함합니다.

1. 사용자 지정 열을 만들려면 **열 추가** 리본 탭의 **일반** 그룹 내에서 **사용자 지정 열을** 선택합니다.

     ![그림 5664](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image47.png)

1. **새 열 이름** 상자의 **사용자 지정 열** 창에서 텍스트를 **비용**으로 바꿉니다.

1. **사용자 지정 열 수식** 상자에서 다음 식을 등호 뒤에 입력합니다.
    - ***D:\PL300\Labs\02-load-data-with-power-query-in-power-bi-desktop\Assets\Snippets.txt** 파일에서 식을 복사할 수 있습니다.*
    - *이 식은 **TotalProductCost** 값이 없는지 테스트합니다. 누락된 경우 **OrderQuantity** 값을 **StandardCost** 값으로 곱하여 값을 생성합니다. 그렇지 않으면 기존 **TotalProductCost** 값을 사용합니다.*
    

    `
    if [TotalProductCost] = null then [OrderQuantity] * [StandardCost] else [TotalProductCost]
    `

1. 다음 두 열을 제거합니다.

    - TotalProductCost
    - StandardCost

1. 다음 세 가지 열의 이름을 바꿉니다.

    - **OrderQuantity**를 **Quantity**로
    - **UnitPrice**를 **Unit Price**로(공백 포함)
    - **SalesAmount**를 **Sales**로

1. 열 데이터 형식을 수정하려면 **수량** 열 머리글의 열 이름 왼쪽에서 **1.2** 아이콘을 선택한 다음 **정수를** 선택합니다.
    
    올바른 데이터 형식 구성은 대단히 중요합니다. 또한 열에 숫자 값이 있으며 수학적 계산을 수행할 예정이라면 반드시 올바른 형식을 선택해야 합니다.

     ![그림 5667](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image50.png)

1. 다음 세 개의 열 데이터 형식을 **고정 10진수**로 수정합니다.
    
    *고정 10진수 데이터 형식은 19자리를 허용하며 반올림 오류를 방지하기 위해 보다 정밀하게 사용할 수 있습니다. 고정 10진수 형식을 재무 가치 또는 금리(예: 환율)에 사용하는 것이 중요합니다.*

    - Unit Price
    - Sales
    - 비용

1. 상태 표시줄에서 쿼리에 열이 10개, 행이 999개 이상 있는지 확인합니다.
    
    *쿼리별 미리 보기 데이터에는 행이 1,000개까지 로드됩니다.*

### **작업 8: Targets 쿼리 구성**

이번 작업에서는 **Targets** 쿼리를 구성합니다.

1. **ResellerSalesTargets 쿼리를** 선택하고 이름을 대상으로 바꿉**니다**.

1. 12개월 열(**M01**-**M12**)을 피벗 해제하기 위해 먼저 **연도** 및 **EmployeeID** 열 머리글을 다중 선택합니다.

1. 선택한 열 헤더 중 하나를 마우스 오른쪽 단추로 클릭한 다음 컨텍스트 메뉴에서 **다른 열 피벗 해제**를 선택합니다.

1. 열 이름이 이제 **특성** 열에 나타나고 값이 **값** 열에 나타납니다.

1. **값** 열에 필터를 적용하여 하이픈(-) 값을 제거합니다.

    *원본 CSV 파일에서 하이픈 문자를 사용하여 영(0)을 나타내는 것을 기억하실 것입니다.*

1. 다음 두 열의 이름을 바꿉니다.

    - **MonthNumber****에 대한 특성**(공백 없음)
    - **Value**를 **Target**으로

1. **MonthNumber** 열 값을 준비하려면 **MonthNumber** 열 헤더를 마우스 오른쪽 단추로 클릭한 다음 **값 바꾸기**를 선택합니다.
        
    이제 변환을 적용하여 날짜 열을 생성합니다. 날짜는 **Year** 및 **MonthNumber** 열에서 파생됩니다. **예제의 열** 기능을 사용하여 열을 만들게 됩니다.

1. **값 바꾸기** 창의 **찾을 값** 상자에 **M**을 입력하고 **바꾸기를 비**워 둡니다.

1. **MonthNumber** 열 데이터 형식을 **정수**로 수정합니다.

1. **열 추가** 리본 탭의 **일반** 그룹 내에서 **예제에서 열 아이콘을** 선택합니다.

    ![그림 5675](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image59.png)

1. 첫 번째 행은 **2017**년, 월 번호 **7**입니다.

1. **Column1** 열의 첫 번째 표 셀에서 **7/1/2017**을 입력한 다음 **Enter**키를 누릅니다.
    
    *가상 머신은 미국 지역 설정을 사용하므로 이 날짜는 실제로 2017년 7월 1일입니다. 다른 지역 설정에는 날짜 전에 **0** 이 필요할 수 있습니다.*

1. 그리드 셀이 예측된 값으로 업데이트됩니다.
    
    *이 기능은 **Year** 및 **MonthNumber** 열의 값을 결합한다고 정확하게 예측했습니다.*

1. 쿼리 그리드 위에 표시되는 수식에도 주목하세요.

     ![그림 5679](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image60.png)

1. 새 열의 이름을 바꾸려면 **병합된** 열 머리글을 두 번 클릭하고 열 이름을 **TargetMonth**로 바꿉니다.

1. 다음 열을 제거합니다.

    - Year
    - MonthNumber

1. 다음 열 데이터 형식을 수정합니다.

    - **Target**을 고정 10진수로
    - **TargetMonth**를 날짜로

1. **대상** 값을 1000으로 곱하려면 **대상** 열 머리글을 선택한 다음 **변환** 리본 탭의 **숫자 열** 그룹 내에서 **표준을** 선택한 다음 **곱**하기를 선택합니다.
    
    *목표 값이 수천 단위로 저장된 것을 기억하실 수 있습니다.*

     ![그림 5682](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image63.png)

1. **곱하기** 창의 **값** 상자에 **1000을** 입력하고 **확인을** 선택합니다.

1. 상태 표시줄에서 쿼리에 세 개의 열과 809개의 행이 있는지 확인합니다.

### **작업 9: ColorFormats 쿼리 구성**

이번 작업에서는 **ColorFormats** 쿼리를 구성합니다.

1. **ColorFormats 쿼리를** 선택하고 첫 번째 행에 열 이름이 포함되어 있음을 확인합니다.

1. **홈** 리본 탭의 **변환** 그룹 내에서 **첫 번째 행을 머리글로 사용을** 선택합니다.

     ![그림 5688](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image68.png)

1. 상태 표시줄에서 쿼리에 세 개의 열과 10개의 행이 있는지 확인합니다.

### **작업 10: Product 쿼리 업데이트**

이번 작업에서는 **ColorFormats** 쿼리를 병합하여 **Product** 쿼리를 업데이트합니다.

1. **Product** 쿼리를 선택합니다.

1. **ColorFormats 쿼리를** 병합하려면 **홈** 리본 탭**에서 결합 아래쪽** 화살표를 선택한 다음 **쿼리 병합을** 선택합니다.
    
    쿼리를 병합하면 데이터를 통합할 수 있는데, 이 경우에는 다양한 데이터 원본(SQL Server 및 CSV 파일)의 데이터를 통합할 수 있습니다.

     ![그림 5654](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image71.png)

1. **제품** 쿼리 표의 **병합** 창에서 **Color** 열 헤더를 선택합니다.

     ![그림 5655](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image72.png)

1. **제품** 쿼리 표 아래의 드롭다운 목록에서 **ColorFormats** 쿼리를 선택합니다.

     ![그림 21](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image73.png)

1. **ColorFormats** 쿼리 표에서 **Color** 열 헤더를 선택합니다.

1. **개인 정보 수준** 창이 열리면 두 데이터 원본 각각에 대해 해당 드롭다운 목록에서 **조직**, **저장**을 차례로 선택합니다.
    
    *데이터 원본에 대해 개인 정보 수준을 구성하여 원본 간에 데이터를 공유할 수 있는지 여부를 결정할 수 있습니다. 각 데이터 원본을 **조직**으로 설정하면 필요한 경우 데이터를 공유할 수 있습니다. 프라이빗 데이터 원본은 다른 데이터 원본과 공유할 수 없습니다. 프라이빗 데이터를 공유할 수 없다는 의미는 아닙니다. 즉, Power Query 엔진은 원본 간에 데이터를 공유할 수 없습니다.*

     ![그림 5691](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image74.png)

1. **병합** 창에서 기본 **조인 종류** - 왼쪽 외부의 선택을 유지 관리하고 **확인을** 선택합니다.

1. 다음 두 개의 열을 포함하도록 **ColorFormats** 열을 확장합니다.

    - Background Color Format
    - 글꼴 색 형식

1. 상태 표시줄에서 쿼리에 이제 8개의 열과 397개의 행이 있는지 확인합니다.

### **작업 11: ColorFormats 쿼리 업데이트**

이번 작업에서는 **ColorFormats**를 업데이트하여 로드를 비활성화합니다.

1. **ColorFormats** 쿼리를 선택합니다.

1. **쿼리 설정** 창에서 **모든 속성** 링크를 선택합니다.

     ![그림 322](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image80.png)

1. **보고서에** 로드 **사용 확인란을 실행** 선택 취소합니다.
    
    *로드를 사용하지 않도록 설정하면 데이터 모델에 테이블로 로드되지 않습니다. 이 작업은 쿼리가 데이터 모델에 로드할 수 있는 **Product** 쿼리와 병합되었기 때문에 수행됩니다.*

     ![그림 323](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image81.png)

### **작업 12: 완료**

이번 작업에서는 랩을 마무리합니다.

1. 다음과 같이 이름이 올바르게 지정된 쿼리 8개가 있는지 확인합니다.

    - Salesperson
    - SalespersonRegion
    - Product
    - Reseller
    - Region
    - Sales
    - 대상
    - ColorFormats(데이터 모델에 로드되지 않음)

1. 데이터 모델을 로드하기 위해 **파일** Backstage 보기에서 **닫기 및 적용**을 선택합니다.
    
    *이제 로드를 활성화한 모든 쿼리가 데이터 모델에 로드됩니다.*

     ![그림 326](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image83.png)

1. **필드** 창(오른쪽에 위치)에서 데이터 모델에 로드된 7개의 테이블을 확인합니다.

     ![그림 3](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image84.png)

1. Power BI Desktop 파일을 저장합니다.

**Power BI Desktop에서 데이터 모델링** 랩에서 데이터 모델 테이블과 관계를 구성합니다.
