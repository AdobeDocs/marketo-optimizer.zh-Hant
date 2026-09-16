---
title: Experience Platform資料集
description: 瞭解Marketo Optimizer寫入Adobe Experience Platform的資料集，以支援Customer Journey Analytics報告和臨時查詢。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 1ebb0036699252c50f33ba6c0f4a56e8e670aacd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 4%
---

# Experience Platform資料集

[!DNL Adobe Marketo Optimizer]會將潛在客戶、歷程和活動資料復寫到[!DNL Adobe Experience Platform]個資料集。 這些資料集支援[!UICONTROL 報表]頁面和內嵌[!DNL Adobe Customer Journey Analytics]報表體驗。 您也可以使用[!DNL Query Service]直接查詢它們以進行Ad Hoc Analysis。

資料集由系統管理。 [!DNL Customer Journey Analytics]中的連線將它們連結到[!DNL Marketo Optimizer]報告使用的資料檢視，因此您不需要自己建立此連線。 當您在報告區段上選取「**[!UICONTROL 在CJA中分析]**」時，此連線與您連線的連線相同。 請參閱[在Customer Journey Analytics中分析報告](./reports-overview.md#analyze-a-report-in-cja)。

## 可用的資料集 {#available-datasets}

每個[!DNL Marketo Optimizer]執行個體皆會填入下列資料集。

>[!NOTE]
>
>每個資料集名稱都使用前置詞`AJOB2B`，表示[!DNL Marketo Optimizer]資料的系統名稱。 這是正常行為，您可以使用這些名稱在[!DNL Experience Platform]沙箱中尋找資料集。

| 資料集 | 結構描述 | 說明 |
| --- | --- | --- |
| `AJOB2B - Person` | 人員 | 標準潛在客戶屬性。 |
| `AJOB2B - PersonActivity` | 個人活動 | 與個人相關聯的活動事件。 |
| `AJOB2B - PersonActivityType` | 個人活動型別 | 與個人相關聯的活動型別。 |
| `AJOB2B - PersonActivityTypeEngagementMapping` | 人員活動型態參與對應 | 將活動型別對應至其參與分類、管道事件和方向性。 |
| `AJOB2B - Journey` | 歷程 | 歷程及其生命週期中繼資料的清單。 |
| `AJOB2B - JourneyNode` | 歷程節點 | 歷程中的節點清單及其關聯的中繼資料。 |
| `AJOB2B - EngagementAsset` | 參與資產 | 跨參與資產型別的參與資產ID和顯示名稱的統一查詢。 |

## 使用查詢服務查詢資料集 {#query-service}

當您需要在[!DNL Customer Journey Analytics]個報表之外的分析時，使用[!DNL Query Service]對這些資料集執行臨機SQL查詢。 查詢存取權需要您沙箱的適當[!DNL Experience Platform]許可權。 如需一般查詢語法和設定，請參閱[查詢服務](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/query/home){target="_blank"}。

![查詢服務編輯器針對ajob2b_journey資料集和產生的歷程記錄表格顯示SELECT查詢。](./assets/aep-query-service.png){width="800" zoomable="yes"}

>[!NOTE]
>
>這些資料集是唯讀的。 若要變更[!DNL Marketo Optimizer]擷取的資料，請更新[!DNL Marketo Optimizer]或[!DNL Marketo Engage]中的來源資料，而非直接編輯資料集。
