---
lab:
  title: Power BI 대시보드 만들기
  module: Create Dashboards
---


# **Power BI 대시보드 만들기**

## **랩 사례**

이 랩에서는 기존 보고서를 사용하여 Power BI 서비스 Sales Monitoring** 대시보드를 만듭니**다.

이 랩에서는 다음 작업을 수행하는 방법을 알아봅니다.

- 대시보드에 시각적 개체 고정
- 질문 및 답변을 사용하여 대시보드 타일 만들기

**이 랩에는 약 30분이 소요됩니다.**

## **시작 - 로그인**

이 작업에서는 Power BI에 로그인하여 랩 환경을 설정합니다.

*참고: Power BI에 이미 로그인한 경우 다음 작업으로 건너뜁니다.*

1. Microsoft Edge를 열려면 작업 표시줄에서 Microsoft Edge 프로그램 바로 가기를 선택합니다.

     ![그림 12](Linked_image_Files/08-design-report-in-power-bi-desktop-enhanced_image1.png)

1. Microsoft Edge 브라우저 창에서 **https://app.powerbi.com**으로 이동합니다.

    *팁: Microsoft Edge 즐겨찾기 표시줄에서 Power BI 서비스 즐겨찾기를 사용할 수도 있습니다.*

1. 조직 자격 증명(또는 사용자에게 제공된 자격 증명)을 사용하여 로그인 프로세스를 완료합니다. Microsoft Edge에서 로그인 상태를 유지할지 묻는 프롬프트가 표시되면 **예**를 선택합니다.

1. Microsoft Edge 브라우저 창의 Power BI 서비스 **탐색** 창에서 **내 작업 영역**을 확장합니다. Microsoft Edge 브라우저 창을 열어 둡니다.

     ![그림 22](Linked_image_Files/07-my-workspace-new.png)

## **시작 – 보고서 열기**

이 작업에서는 시작 보고서를 열어 랩에 대한 환경을 설정합니다.

*중요: 이전 랩에서 계속 진행하는 경우(해당 랩을 성공적으로 완료한 경우) 이 작업을 완료하지 마세요. 대신 다음 작업에서 계속합니다.*

1. Power BI Desktop을 실행합니다.
    
    *기본적으로 Power BI Desktop 앞에 시작 대화 상자가 열립니다. 로그인한 다음 팝업을 닫습니다.*

    ![Power BI Desktop 아이콘](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. 시작 Power BI Desktop 파일을 열려면 파일 > 보고서 열기 > 보고서** 찾아보기를 선택합니다**.

1. **열기** 창에서 D:\PL300\Labs\09-create-power-bi-dashboard\Starter** 폴더로 이동하고 **Sales Analysis** 파일을 엽니다**.

1. 열려 있는 정보 창을 모두 닫습니다.

1. 리본 아래에서 노란색 경고 메시지를 확인합니다. *이 메시지는 쿼리가 모델 테이블로 로드에 적용되지 않았다는 사실을 경고합니다. 나중에 랩에서 쿼리를 적용합니다.*
    
    *경고 메시지를 해제하려면 노란색 경고 메시지 오른쪽에서 X**를 선택합니다**.*

1. 변경 내용을 적용할지 묻는 프롬프트가 표시되면 **나중에 적용**을 선택합니다.

## **시작 - 보고서 게시**

이 작업에서는 데이터 세트를 만들어 랩에 대한 환경을 설정합니다. *데이터 세트를 이미 게시한 경우 다음 작업으로 이동하세요.*

1. Microsoft Edge 브라우저 창의 Power BI 서비스 내 작업 영역**으로 **이동합니다.

1. 업로드 > 찾아보기를** 선택합니다**.

1. **D:\PL300\Labs\09-create-power-bi-dashboard\Starter** 폴더로 이동합니다.

1. **Sales Analysis.pbix** 파일을 선택한 다음, **열기**를 선택합니다.

*데이터 세트를 바꾸라는 메시지가 표시되면 [바꾸기 **]를 선택합니다**.*

## **대시보드 만들기**

이 작업에서는 Sales Monitoring 대시보드를 **** 만듭니다. 보고서에서 시각적 개체를 고정하고 이미지 데이터 URI를 기준으로 타일을 추가하고 Q&A를 사용하여 타일을 만듭니다.

1. Power BI 서비스 판매 분석** 보고서를 엽니다**.

1. **개요** 페이지에서 **연도** 슬라이서를 **FY2020**으로 설정합니다.

    ![그림 4](Linked_image_Files/09-create-power-bi-dashboard_image17.png)

1. **지역** 슬라이서를 **모두 선택**으로 설정합니다.

    *고정된 시각적 개체는 고정 시 필터 컨텍스트를 사용하여 설정됩니다. 기본 시각적 개체가 변경되면 대시보드 타일도 업데이트해야 합니다. 시간 기반 필터의 경우 상대 날짜 슬라이서(또는 상대 시간 기반 질문을 사용하는 Q&A)를 사용하는 것이 좋습니다.*

1. 대시보드를 만들고 시각적 개체를 고정하려면 월별 영업 및 이익률 **(열/선) 시각적 개체 위에 **커서를 놓고 압정을 선택합니다.

    ![그림 43](Linked_image_Files/09-create-power-bi-dashboard_image18.png)

1. 대시보드**에 고정 창**의 **대시보드 이름** 상자에 판매 모니터링을 입력**한 다음 고정**을** 선택합니다**.

    ![그림 3](Linked_image_Files/09-create-power-bi-dashboard_image19.png)

1. **내 작업 영역을** 열고 Sales Monitoring 대시보드를 **** 엽니다.

1. 대시보드에는 단일 타일이 있습니다.

    ![그림 45](Linked_image_Files/09-create-power-bi-dashboard_image22.png)

1. 질문을 기반으로 타일을 추가하려면 대시보드의 왼쪽 위에서 **데이터에 대해 질문하기**를 선택합니다.
    
    *Q&A 기능을 사용하여 질문을 할 수 있으며 Power BI는 시각적 개체에 응답합니다.*

    ![그림 7](Linked_image_Files/09-create-power-bi-dashboard_image23.png)

1. Q&A 상자 아래의 제안된 질문 중 하나를 파란색 상자로 선택하고 응답을 검토합니다.

1. Q&A 상자에서 모든 텍스트를 제거하고 다음 **을 입력합니다. Sales YTD**

1. **(Blank)** 응답을 확인합니다.
    
    *Power BI Desktop 랩에서 **고급 DAX 계산 만들기에 **Sales YTD** 측정값을 추가한 것을 기억할 수** 있습니다. 이 측정값은 시간 인텔리전스 식이므로 결과를 생성하려면 Date** 테이블에 대한 **필터가 필요합니다.*

    ![그림 14](Linked_image_Files/09-create-power-bi-dashboard_image25.png)

1. **in year FY2020**으로 질문을 확장합니다.

1. 이제 응답으로 **$33M**이 표시됩니다.

    ![그림 13](Linked_image_Files/09-create-power-bi-dashboard_image27.png)

1. 대시보드에 응답을 고정하려면 오른쪽 위 모서리에서 시각적 개체** 고정을 선택합니다**.

    ![그림 15](Linked_image_Files/09-create-power-bi-dashboard_image28.png)

1. 타일을 대시보드에 고정할지 묻는 프롬프트가 표시되면 **고정**을 선택합니다.

1. 대시보드로 돌아가려면 왼쪽 위 모서리에서 Q&amp;A** 끝내기를 선택합니다**.

1. 회사 로고를 추가하려면 메뉴 모음에서 편집을 선택한 **다음 타일** 추가를 선택합니다**.**
    
    *이 기술을 사용하여 대시보드 타일을 추가하면 웹 콘텐츠, 이미지, 서식이 풍부한 텍스트 상자 및 비디오(YouTube 또는 Vimeo 링크 사용)를 비롯한 미디어를 통해 대시보드를 향상시킬 수 있습니다.*

1. 오른쪽에 **있는 타일** 추가 창에서 이미지** 타일을 **선택한 다음, 다음**** 을 선택합니다.

1. 이미지 타일** 추가 창**의 **URL** 상자에 D:\PL300\Resources\AdventureWorksLogo_DataURL.txt** 파일에 있는 **전체 URL을 입력한 다음 **적용합니다**.
    
    *해당 URL을 사용하여 이미지를 포함하거나 콘텐츠를 인라인으로 포함하는 데이터 URL을 사용할 수 있습니다.*

1. 로고 타일의 크기를 조정하려면 오른쪽 아래 모서리를 끌고 타일 크기를 1개 단위(너비) x 2개 단위(높이)로 조정합니다.
    
    *타일 크기는 사각형 모양으로 제한됩니다.*

1. 로고가 왼쪽 위에 표시되고 그 아래에 **Sales YTD** 타일이 표시되고 오른쪽에 **Sales, Profit Margin** 타일이 표시되도록 타일을 구성합니다.

    ![그림 52](Linked_image_Files/09-create-power-bi-dashboard_image35.png)

## **타일 세부 정보 편집**

이 작업에서는 두 타일의 세부 정보를 편집합니다.

1. 커서로 **Sales YTD** 타일을 가리킨 다음, 타일 오른쪽 위에 있는 줄임표를 선택하고, **세부 정보 편집**을 선택합니다.

    ![그림 50](Linked_image_Files/09-create-power-bi-dashboard_image36.png)

1. 오른쪽에 **있는 타일 세부 정보** 창의 자막** 상자에 FY2020**을 입력**한 다음 적용**을 선택합니다**.**

1. **Sales YTD** 타일에 부제목이 표시됩니다.

    ![그림 21](Linked_image_Files/09-create-power-bi-dashboard_image39.png)

1. Sales, Profit Margin** 타일에 **대한 타일 세부 정보를 편집합니다.

1. 타일 세부 정보 창의 기능 섹션에서 검사 **마지막 새로 고침 시간을** 표시한 다음 **적용합니다**.** ****** 

    ![그림 22](Linked_image_Files/09-create-power-bi-dashboard_image40.png)

1. 타일은 마지막 새로 고침 시간(Power BI Desktop에서 데이터 모델을 로드할 때 수행됨)을 설명합니다.

*다음 연습에서 데이터 세트를 새로 고칩니다. 데이터 및 보고서에 따라 언제든지 임시 데이터 새로 고침을 수행하거나 일정을 설정할 수 있습니다. 그러나 예약된 새로 고침에는 이 랩에 대해 구성할 수 없는 게이트웨이가 필요합니다. 따라서 Power BI Desktop에서 수동 데이터 새로 고침을 수행한 다음, 파일을 작업 영역에 업로드합니다.*

## **데이터 세트 새로 고침**

이 연습에서는 먼저 2020년 6월의 판매 주문 데이터를 **AdventureWorksDW2020** 데이터베이스로 로드합니다. 그런 다음, Power BI Desktop 파일을 열고, 데이터 새로 고침을 수행한 다음, 파일을 작업 영역에 업로드합니다.

## **랩 데이터베이스 업데이트**

이 작업에서는 PowerShell 스크립트를 실행하여 **AdventureWorksDW2020** 데이터베이스의 데이터를 업데이트합니다.

1. 파일 탐색기의 **D:\PL300\Setup** 폴더 내부에서 **UpdateDatabase-2-AddSales.ps1** 파일을 마우스 오른쪽 단추로 클릭한 다음, **PowerShell에서 실행**을 선택합니다.

    ![그림 28](Linked_image_Files/09-create-power-bi-dashboard_image46.png)

1. 실행 정책을 변경할지 묻는 프롬프트가 표시되면 **A** 키를 누릅니다.

1. 아무 키나 눌러 닫을지 묻는 메시지가 표시되면 Enter** 키를 다시 누릅니**다.

이제 **AdventureWorksDW2020** 데이터베이스에 2020년 6월 판매 주문이 포함되어 있습니다.**

## **Power BI Desktop 파일 새로 고침**

이 작업에서는 Sales Analysis** Power BI Desktop 파일을 열고**, 데이터 새로 고침을 수행한 다음, Sales Analysis** 작업 영역에 파일을 **업로드합니다.

1. Power BI Desktop 파일의 **데이터 창에서 Sales** 테이블을 마우스 오른쪽 단추로 클릭한 **다음 데이터** 새로 고침을 선택합니다****.

    ![그림 55](Linked_image_Files/09-create-power-bi-dashboard_image47.png)

1. 새로 고침이 완료되면 Power BI Desktop 파일을 저장합니다.

1. 파일을 작업 영역에 게시하려면 홈 리본 탭의 **공유** 그룹 내에서 **게시**를 선택한 **다음 게시할 선택을** 선택합니다**.**

    ![그림 59](Linked_image_Files/09-create-power-bi-dashboard_image48.png)

1. 데이터 세트를 바꿀지 묻는 프롬프트가 표시되면 **바꾸기**를 선택합니다.

1. Power BI Desktop을 닫습니다.

‘이제 Power BI 서비스의 데이터 세트에 2020년 6월 판매 데이터가 포함됩니다.’**

### **대시보드 검토**

이 작업에서는 대시보드를 검토하여 업데이트된 판매를 확인합니다.

1. Microsoft Edge 브라우저 창에서 Power BI 서비스 연 다음 내 작업 영역에서 판매 모니터링 대시보드**를** 검토**합니다**.

2. **Sales, Profit Margin** 타일에서 부제에 따라 데이터가 새로 고쳐진 **것을 확인합니다. NOW**.

3. 2020년 6월** 열**도 있습니다.
    
    2020년 6월 데이터가 표시되지 않으면 **F5** 키를 눌러 웹 브라우저를 다시 로드해야 할 수도 있습니다.**

    ![그림 33](Linked_image_Files/09-create-power-bi-dashboard_image50.png)

### **마침(Finish up)**

이번 작업에서는 랩을 마무리합니다.

1. 보고서를 저장하고 브라우저를 닫습니다.
