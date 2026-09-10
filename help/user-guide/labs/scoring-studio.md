---
title: 評分工作室
description: 瞭解Adobe Marketo Optimizer中的Scoring Studio，包括模型清單、畫布、維度欄、訊號卡、潛在客戶區段和發佈。
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
source-git-commit: 96a923c923a6290b9d90e4ffc8e161d78f029c47
workflow-type: tm+mt
source-wordcount: 897
ht-degree: 2%

---


# 評分工作室

Scoring Studio包含模型清單、每個模型的可編輯畫布以及[同事聊天介面](../agents/chat-interface.md)。 使用畫布直接檢閱或調整維度和訊號，而Co-worker會繼續與您一起提出自然語言變更。 如需從提示建立模型的相關資訊，請參閱&#x200B;[_建立自訂評分模型_](../agents/lead-scoring-model.md)。

## 模型清單 {#model-list}

模型清單是Scoring Studio的登陸檢視。 它會將[!DNL Marketo Optimizer]執行個體中的每個評分模型顯示為表格中的列，或是如果您切換至格線檢視則顯示為卡片。

| 欄 | 說明 |
| --- | --- |
| 名稱 | 選取模型名稱以在畫布上開啟它。 |
| 狀態 | _[!UICONTROL 作用中]_、_[!UICONTROL 草稿]_&#x200B;或&#x200B;_[!UICONTROL 已封存]_。 |
| 維度 | 模型中的尺寸數量。 |
| 訊號 | 模型中的訊號數。 |
| 上次修改日期 | 上次變更模型的日期。 |
| 上次修改者 | 上次變更模型的人員。 |
| 建立日期 | 建立模型的日期。 |
| 建立者 | 建立模型的人員。 |

![Scoring Studio模型清單會顯示作用中評分模型及其維度、訊號和上次修改的詳細資料。](./assets/scoring-studio-ui.png){width="800" zoomable="yes"}

使用搜尋欄位可依名稱尋找模型，或依狀態篩選清單。 選取資料列的&#x200B;**[!UICONTROL 更多功能表]**&#x200B;至&#x200B;**[!UICONTROL 編輯]**、**[!UICONTROL 複製]**、**[!UICONTROL 封存]**&#x200B;或&#x200B;**[!UICONTROL 刪除]**&#x200B;模型。

作用中的模型是唯讀的。 若要變更，請複製它並編輯副本。 接著，封存原始檔案並發佈修改後的副本。

## 模型畫布 {#model-canvas}

選取模型名稱會在畫布上開啟它。 每個開啟的模型都會顯示為其本身的標籤，因此您可以跨多個模型操作。 畫布已組織成標籤，包括&#x200B;**[!UICONTROL 規則]**&#x200B;和&#x200B;**[!UICONTROL 銷售機會]**。

在&#x200B;**[!UICONTROL 規則]**&#x200B;標籤上，模型中的每個維度都是畫布上的欄。 每個欄標題都會顯示維度名稱及其頂端的點總計，例如`20 / 30 pts`，其進度列會填滿作為其訊號貢獻點。

![「規則」標籤畫布會顯示三個維度欄：「電子郵件參與」、「設定檔符合」和「最近活動」，每個欄都有訊號卡和點。](./assets/scoring-studio-model-rules-tab.png){width="700" zoomable="yes"}

在每個維度內，每個訊號都會顯示為卡片，顯示其名稱、點值以及符合頻率（例如，`1 time / day`）或不相依於活動的屬性型訊號`Static`。

當Co-worker偵測到多個活動中的模式時，它可以將它們合併為單一複合訊號卡，以摘要說明每個條件。

## 設定訊號 {#configure-signal}

若要檢閱或變更訊號，請遵循下列步驟。

1. 選取&#x200B;**[!UICONTROL 編輯草稿]**。

1. 在畫布上選取訊號卡。

   屬性面板會在畫布右側開啟。

   ![規則標籤畫布會顯示選取的訊號卡及其屬性面板，其中包含訊號型別、活動型別、條件和點。](./assets/scoring-studio-model-selected-signal.png){width="700" zoomable="yes"}

1. 選取&#x200B;**[!UICONTROL 編輯]**&#x200B;圖示（![編輯圖示](../assets/do-not-localize/icon-react-edit.svg) ），然後更新訊號屬性：

   * 在&#x200B;**[!UICONTROL 訊號]**&#x200B;底下，確認訊號型別（活動或屬性），以及分數的特定活動或屬性。

   * 在&#x200B;**[!UICONTROL 於]**&#x200B;引發此專案，設定必須符合的條件。

     新增要使用的專案，例如特定頁面，以及條件必須是&#x200B;**[!UICONTROL Any of]**&#x200B;或&#x200B;**[!UICONTROL All of]**。

   * 在&#x200B;**[!UICONTROL 點]**&#x200B;下，設定訊號貢獻了多少點。

     可選擇設定&#x200B;**[!UICONTROL 上限]**&#x200B;以限制每人可貢獻的點數。 Co-worker會根據模型中的其他訊號顯示建議的點範圍。

   * 對於活動型訊號，請在訊號獎勵點之前設定所需的&#x200B;**[!UICONTROL 頻率]**。

     選擇性地設定&#x200B;**[!UICONTROL 耗損]**&#x200B;百分比，減少指定天數後訊號的點數。

   * 啟用&#x200B;**[!UICONTROL 避免將相同動作評分兩次]**&#x200B;選項，即無論該活動發生多少次，每人僅會獲得一次點數。

     停用在每次活動發生時獎勵點的選項。 此設定預設為開啟。

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以套用您的變更並返回畫布。

## 潛在客戶區段 {#lead-segment}

每個評分模型都會對一個潛在客戶區段評分，此參考資料會參照現有人員清單，而非您在Scoring Studio內定義的規則。 Co-worker建立模型時，會選取相符的清單或建立新清單。

若要變更清單，請選取&#x200B;**[!UICONTROL 銷售機會]**&#x200B;標籤，然後選取銷售機會區段旁的&#x200B;**[!UICONTROL 變更]**。

![「銷售機會」標籤會顯示銷售機會區段卡片，其中含有參照的人員清單、「檢視人員清單」連結以及「變更」連結。](./assets/scoring-studio-model-lead-tab.png){width="700" zoomable="yes"}

潛在客戶區段使用下列兩種清單型別之一：

* **靜態清單** — 建立清單時擷取的固定人員集。
* **智慧清單** — 每當模型執行時都會重新評估其成員資格規則的清單，因此區段一律會反映清單條件。

模型預覽會顯示區段名稱、其成員計數，以及直接開啟清單的&#x200B;**[!UICONTROL 檢視人員清單]**&#x200B;連結。 如需管理清單的詳細資訊，請參閱&#x200B;[_人員清單_](../audiences/people-lists.md)。

如果參照的清單為空白或稍後移除，則模型會停止評分，而非退回給整個對象。 在您指派有效的非空白清單之前，系統不會為任何銷售機會評分。

在潛在客戶區段下方，**[!UICONTROL 分數欄位名稱]**&#x200B;卡片會顯示模型寫入其分數的潛在客戶屬性。 依預設，欄位名稱會符合模型的名稱。 選取&#x200B;**[!UICONTROL 編輯]**&#x200B;以重新命名。

## 發佈與排程 {#publish-schedule}

當您的模型準備就緒時，請選取&#x200B;**[!UICONTROL 發佈]**。 選擇模型給對象評分的頻率：每日、每週或每月。

如需完整發佈程式，包括[!DNL Marketo Optimizer]如何自動布建評分欄位，請參閱&#x200B;[_發佈評分模型_](../agents/lead-scoring-model.md#publish-model)。
