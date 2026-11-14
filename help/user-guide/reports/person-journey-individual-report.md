---
title: 個人歷程詳細資料報表
description: 瞭解Adobe Marketo Optimizer中的人員歷程詳細資訊報表，該報表顯示所選歷程的完成、參與和電子郵件量度。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
source-git-commit: 84abcbf4ddf114898768766d6e91ec855e3f979f
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%
---

# 個人歷程詳細資料報告

<!-- SPHR-39120: UX plans to move the Journey activity flow tile to the top of the report. Update the tile order in this page when that ships. -->

按一下&#x200B;**[!UICONTROL 檢視報表]**&#x200B;以取得即時或完成的人員歷程，以檢視其績效度量和活動流程。 開啟報告後，您可以選取多個歷程以納入報告中。

>[!PREREQUISITES]
>
>若要檢視此報告，您必須擁有&#x200B;**[!UICONTROL 檢視B2B人員歷程報告]** [許可權](../start/permissions-reference.md)。

檢視報告(_T):_

1. 從&#x200B;_[!UICONTROL 個人歷程]_&#x200B;清單開啟&#x200B;**[!UICONTROL 即時]**&#x200B;或&#x200B;**[!UICONTROL 已完成]**&#x200B;個人歷程。
1. 在歷程標題中，選取&#x200B;**[!UICONTROL 檢視報告]**。

   ![個人歷程畫布，在歷程標題中反白顯示「檢視報告」按鈕。](./assets/reports-person-journey-view-report.png){width="600" zoomable="yes"}

您可以[變更報告的日期範圍](./reports-overview.md#change-the-date-range)。

選取報表頂端的&#x200B;**[!UICONTROL 共用]**&#x200B;以下載或排程資料匯出。 請參閱報表概觀中的&#x200B;[_匯出報表_](./reports-overview.md#export-a-report)。

![個人歷程個人報告，其歷程名稱（事件）和角色（事件）篩選器高於歷程狀態、完成趨勢和參與圖磚。](./assets/reports-individual-journey.png){width="700" zoomable="yes"}

## 篩選器 {#filters}

報表最初會顯示您開啟歷程的來源。 使用報告頂端的篩選器來變更包含哪些歷程和角色。

* **[!UICONTROL 歷程名稱（事件）]** — 預先設定為您開啟報告的歷程。 開啟篩選器清單，並選取要包含的歷程。 您可以選取多個歷程。
* **[!UICONTROL 角色（事件）]** — 將報告篩選為符合特定[衍生角色](../audiences/personas.md#filter-by-derived-persona)的人員。 預設為[!UICONTROL 沒有篩選器]。

![歷程報告，其歷程名稱（事件）篩選器清單已開啟，且已選取三個歷程，連同角色（事件）篩選器。](./assets/reports-person-journey-details-filters.png){width="700" zoomable="yes"}

若要依角色篩選，請開啟報表頂端的&#x200B;**[!UICONTROL 角色（事件）]**&#x200B;篩選清單，並選取要包含的值。

選取&#x200B;**[!UICONTROL 全部重設]**&#x200B;以重設報表篩選器。

## 個人狀態和參與 {#person-status-and-engagement}

本節介紹四個圖磚：

* **[!UICONTROL 歷程中的人員狀態]** — 將歷程中的人員分成&#x200B;_[!UICONTROL 已完成]_&#x200B;和&#x200B;_[!UICONTROL 進行中]_&#x200B;類別，並使用對應的百分比。
* **[!UICONTROL 一段時間內的已完成人數]** — 追蹤選定日期範圍內完成歷程人數的折線圖。
* **[!UICONTROL 已參與和未參與的人員]** — 將歷程中的人員分為&#x200B;_[!UICONTROL 已參與]_&#x200B;和&#x200B;_[!UICONTROL 未參與]_&#x200B;類別，並提供對應的百分比。
* **[!UICONTROL 參與的人員]** — 符合參與歷程資格的總人數。

## 電子郵件績效 {#email-performance}

[!UICONTROL 電子郵件效能]表格顯示歷程中傳送之每封電子郵件的傳遞和參與量度。 如需所有歷程的相同電子郵件量度，請參閱[電子郵件參與報告](./email-engagement-report.md)。

![電子郵件效能表格顯示三封電子郵件的已傳送、已傳遞、已開啟及已點按量度。](./assets/reports-individual-journey-email-performance.png){width="700" zoomable="yes"}

[!UICONTROL 電子郵件效能]資料表資料行：

* [!UICONTROL 電子郵件名稱] — 電子郵件的名稱。
* [!UICONTROL 已傳送] — 已傳送的電子郵件數目。
* [!UICONTROL 已傳遞] — 已傳遞的電子郵件數目。
* [!UICONTROL %已傳遞] — 已傳遞電子郵件數除以已傳送數目。
* [!UICONTROL 已開啟] — 收件者開啟電子郵件的次數。
* [!UICONTROL %已開啟] — 已開啟電子郵件數除以傳遞數目。
* [!UICONTROL 已點按] — 收件者點按電子郵件中連結的次數。
* [!UICONTROL %已點按] — 已點按電子郵件數除以傳遞數目。

## 歷程活動流程 {#journey-activity-flow}

[!UICONTROL 歷程活動流程]視覺效果會顯示人員通過歷程的路徑，從&#x200B;_[!UICONTROL 將人員新增至歷程]_&#x200B;活動開始。 每個節點顯示該活動的檢視次數。

![歷程活動流量視覺效果顯示透過傳送電子郵件和電子郵件退回活動，從「新增人員」到「歷程」的路徑檢視。](./assets/reports-individual-journey-activity-flow.png){width="500" zoomable="yes"}
