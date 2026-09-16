---
title: 報告
description: 瞭解Adobe Marketo Optimizer中的「報表」索引標籤，包括其報表區段、匯出和排程選項，以及如何變更日期範圍。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 32017a2577b7f31632080215ba91b9454c51b9ef
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 2%
---

# 報告

[!UICONTROL 報表]索引標籤會提供[!DNL Adobe Marketo Optimizer]的績效深入分析，包括歷程參與、電子郵件績效和網頁活動。 在左側導覽列中，選取&#x200B;**[!UICONTROL 報表]**&#x200B;以開啟。

每個報告都建立在[!DNL Adobe Customer Journey Analytics]上並直接內嵌在[!DNL Marketo Optimizer]中。 按一下&#x200B;_清單_&#x200B;圖示（![清單圖示](../assets/do-not-localize/icon-table-of-contents.svg)）以使用左側的&#x200B;**[!UICONTROL 目錄]**&#x200B;面板在區段之間跳轉。

![報告頁面列出個人歷程概觀、參與、電子郵件參與和網頁參與區段](./assets/reports-table-of-contents.png){width="800" zoomable="yes"}

## 報表區段 {#report-sections}

[!UICONTROL 報告]索引標籤將預先建立的報告組織成四個區段。 每個區段都有一或多個可下載的專案，以及其專屬的檔案頁面，其中包含量度和視覺效果的詳細資料。

| 區域 | 可下載的專案 | 報告頁面 |
| --- | --- | --- |
| [!UICONTROL 個人歷程總覽] | 作用中歷程的數量 | [個人歷程概觀報告](./person-journey-overview-report.md) |
| [!UICONTROL 參與] | 依人員的參與度，一段時間內個人的參與度 | [參與度報告](./engagement-report.md) |
| [!UICONTROL 電子郵件參與] | 電子郵件參與 | [電子郵件參與報告](./email-engagement-report.md) |
| [!UICONTROL Web參與] | 排名最高的頁面檢視次數 | [Web Engagement報告](./web-engagement-report.md) |

## 個別記錄報告 {#individual-record-reports}

有些報表著重於單一記錄而非全區段檢視，並可從應用程式的不同區域存取。

* 若要取得電子郵件傳送時間最佳化效能，請從[!UICONTROL 同事]聊天介面開啟報表。 如需相關步驟，請參閱[電子郵件傳送時間最佳化](../marketing/email-send-time-optimization.md#reporting)。
* 如需個人在單一歷程中的進度，請從該歷程開啟報告。

## 匯出報告 {#export-a-report}

選取報表頁面頂端的&#x200B;**[!UICONTROL 共用]**&#x200B;以匯出或排程其資料的傳送。

![使用「下載CSV」、「下載PDF」、「排程匯出」和「管理排程」選項共用功能表](./assets/reports-share-menu.png){width="500"}

* **[!UICONTROL 下載CSV]** — 將報表資料匯出為純文字值。

* **[!UICONTROL 下載PDF]** — 將報表中的所有可見表格和視覺效果匯出為PDF檔案。

* **[!UICONTROL 排程匯出]** — 設定週期性匯出報告，每週或每月以CSV或PDF檔案傳送。

* **[!UICONTROL 管理排程]** — 檢閱和管理現有的排程匯出。 選項會顯示執行中的排程計數，例如`3/10`，這些排程已用於您組織的限制。

>[!NOTE]
>
>您的組織可以每週或每月頻率在所有報告中最多有10個排程匯出。 如果您不是管理員，則只能管理您自己的排程匯出。 管理員可檢視及管理組織內的每個排程匯出。

## 在[!DNL Customer Journey Analytics]中分析報告 {#analyze-a-report-in-cja}

>[!AVAILABILITY]
>
>如果您的組織已獲得[!DNL Adobe Customer Journey Analytics]的授權，且您已被指派產品設定檔，則可使用此功能。

在任何報表區段上選取「**[!UICONTROL 在CJA中分析]**」，以在[!DNL Adobe Customer Journey Analytics] Workspace中開啟它，除了內嵌報表中可用的視覺效果之外，您還可以在其中建立自訂視覺效果。

## 變更日期範圍 {#change-the-date-range}

每個報表區段都會顯示特定日期範圍的資料，並顯示在區段的右上角。 按一下日期範圍欄位，以顯示日期選取工具並選取日期範圍。 您可以選擇不同的預設集或定義自訂範圍。

![日期範圍選擇器，包含兩個月行事曆、開始和結束日期欄位，以及預設集選項](./assets/reports-date-range.png){width="600"}
