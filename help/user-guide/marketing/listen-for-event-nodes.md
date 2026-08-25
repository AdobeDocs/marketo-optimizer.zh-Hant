---
title: 接聽事件節點
description: 設定在Marketo Optimizer中接聽事件節點 — 設定事件觸發器、套用選用篩選器，並在活動或資料變更發生時提升人員。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 5%

---

# 接聽事件節點

新增&#x200B;_接聽事件_&#x200B;節點，以便在事件發生時，將您的對象移至歷程的下一個步驟。

## 事件觸發程式 {#event-triggers}

您可以針對[!DNL Marketo Engage]個活動建置觸發程式，例如：

* 填寫表單 — 當使用者在您的登陸頁面上提交[!DNL Marketo Engage]表單時引發。
* 造訪網頁 — 潛在客戶檢視追蹤的網頁時引發（您可以指定確切URL或使用萬用字元）。
* 點按連結 — 當行銷電子郵件中的追蹤連結被點按時引發。
* 資料值變更 — 在個人記錄上更新特定欄位（例如銷售機會狀態、分數或產業）時引發。
* 已要求Campaign — 通常用於API或webhook整合，此觸發器會在其他方案或網站服務呼叫促銷活動時啟動促銷活動。
* 分數已變更 — 當個人的潛在客戶分數超過特定臨界值而增加或減少時引發。
* 行動推播已點選 — 當推播通知在裝置上互動時，會在行動行銷智慧行銷活動中觸發。

## 事件篩選器 {#event-filters}

| 篩選器 | 說明 |
| ------- | ----------- |
| 活動歷史記錄>電子郵件 | 根據使用一或多封所選電子郵件訊息評估的條件，以電子郵件活動為基礎： <li>電子郵件中已點選的連結 <li>開啟電子郵件 |
| 活動歷史記錄>資料值已變更 | 針對選取的人員屬性，發生值變更。 這些變更型別包括： <li>新值 <li>上一個值 <li>原因 <li>來源 <li>活動日期 <li> 最低 次數 |

## 新增事件節點 {#add-event-node}

1. 導覽至歷程畫布。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 接聽事件]**。

   ![按一下歷程路徑上的新增圖示](./assets/person-journey-canvas-add-node.png){width="200"}

1. 在右側的節點屬性中，按一下&#x200B;**[!UICONTROL 新增事件條件]**。

1. 在&#x200B;_[!UICONTROL 編輯事件]_&#x200B;對話方塊中，新增要觸發的事件。

   ![編輯事件 — 事件觸發程式](./assets/edit-event-triggers.png){width="600" zoomable="yes"}

1. （選擇性）在對話方塊中選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;索引標籤，並為觸發程式新增篩選准則。

1. 按一下&#x200B;**[!UICONTROL 編輯事件]**&#x200B;並定義事件的詳細資料。

   ![編輯事件 — 事件篩選](./assets/edit-event-filters.png){width="600" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

<!--
1. If needed, set the **[!UICONTROL Timeout]** option to limit the time period to listen for the event.

   >[!NOTE]
   >
   >The journey ends after a timeout unless you define a timeout path, where you can add other nodes.

   Enable the **[!UICONTROL Timeout]** option and select the duration for which the journey waits for an event to occur before it times out.

   You can choose to end the path here or take a different course of action by setting another path. To create a new path in the journey where you can add actions and events applicable to accounts when the event does not occur, select the **[!UICONTROL Set timeout path]** check box.

   ![Journey event node - set timeout path](assets/node-event-timeout-set-path.png){width="700" zoomable="yes"}
-->

>[!NOTE]
>
>監聽事件節點的逾時功能目前無法運作。 已規劃於更高版本中推出。

