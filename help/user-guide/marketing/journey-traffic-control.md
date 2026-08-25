---
title: 歷程流量控制
description: 瞭解Marketo Optimizer中的Journey流量控制如何跨七個加權維度使用AI分數，以在對象重疊時只將每個人註冊到他們的最適化歷程。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1543'
ht-degree: 0%

---

# 歷程流量控制

歷程流量控制(JTC)會在對象重疊時，將個人的最佳歷程列為優先順序。 當某人符合多個啟用JTC的歷程的資格時，AI模型會針對每個候選者評估這些歷程，並將其新增至最適化歷程，以將他們隔絕於其他人。

>[!NOTE]
>
>歷程流量控制對[!DNL Journey Optimizer B2B Edition]和[!DNL Marketo Optimizer]的運作方式相同。 功能和邏輯相同；層級之間只有細微的UI差異。 此頁面中的資訊反映了[!DNL Marketo Optimizer]體驗。

當人員完成歷程後，系統會針對其仍符合資格的剩餘歷程重新評估他們。 然後JTC會將它們新增至下一個最適合的歷程，以此類推。 這可防止將同一人同時指派至多個重疊的歷程，並確保每個聯絡人都會先收到最相關的體驗。

>[!NOTE]
>
>目前，一次只能將個人置於一個JTC選取的歷程中。 未來版本計畫推出管理員設定選項，允許人員同時註冊多個歷程。

## 評分維度 {#scoring-dimensions}

模型會針對七個評分維度評估每個人的歷程組合。 系統會根據您設定的權重，獨立為每個維度評分，然後加以合併，以產生該人員和歷程的最終相符機率。 已選取具有最強相符性的歷程。

| 維度 | 其評估的內容 |
|---|---|
| 色彩比對方式 | 行為意圖訊號：關鍵字搜尋、產品頁面造訪、內容下載、電子郵件開啟/點進，以及定價頁面活動。 |
| 對象符合度 | 此人員與歷程的[目標對象](./person-audience-node.md)相符的程度。 |
| 角色符合 | 人員的角色/[角色](../audiences/personas.md)與歷程之間的對齊方式。 |
| 最適大小 | 公司層級屬性（例如產業、規模和收入）。 |
| 人口統計比對 | 個人層級人口統計屬性。 |
| 心理調整 | 以態度/偏好設定為基礎的對齊。 |
| 參與符合 | 人員[參與](../audiences/engagement-scores.md)的造訪間隔和深度。 |

系統會自動略過人員沒有資料的維度，因此永遠不會因為缺少屬性而懲罰評分。

>[!IMPORTANT]
>
>至少有兩個歷程必須啟用JTC，才能執行任何有意義的工作。 在單一歷程中啟用它是無效的，因為沒有競爭歷程可進行仲裁。 只有當兩個或多個歷程啟用了JTC時，模型才會開始解決衝突。

## 先決條件 {#prerequisites}

在歷程流量控制產生結果之前，請記住以下事項：

* **報告需要已發佈、已啟用JTC的歷程。** 在至少發佈一個已啟用歷程流量控制的歷程之前，_[!UICONTROL 報告]_&#x200B;索引標籤不會顯示任何資料。
* **執行個體中至少需要一個已發佈的歷程。** 模擬會評估已存在於即時歷程中的[設定檔](../audiences/people-lists.md)，因此它需要在執行個體中至少有一個已發佈的歷程才能從中擷取設定檔。 模擬本身不需要啟用JTC （請參閱&#x200B;[_模擬評分_](#simulate-scoring)）。

## 開始使用 {#get-started}

在左側導覽上選取&#x200B;**[!UICONTROL 歷程流量控制]**。 顯示的頁面有兩個頁簽：

* **[!UICONTROL 報告]** — 檢視流量控制執行的結果（僅在JTC已在即時歷程上執行之後填入）。
* **[!UICONTROL 組態]** — 調整評分維度、模擬結果，以及選擇參與哪些歷程。

>[!IMPORTANT]
>
>對於從未使用歷程流量控制的全新客戶，_[!UICONTROL 報告]_&#x200B;索引標籤是空的。 報告僅反映已套用流量控制且正在執行的歷程。 從&#x200B;_[!UICONTROL 組態]_&#x200B;索引標籤開始。

## 設定索引標籤 {#configuration-tab}

_[!UICONTROL 組態]_&#x200B;索引標籤有兩個區段：**[!UICONTROL 調整維度評分]**&#x200B;和&#x200B;**[!UICONTROL 選取歷程]**。

### 調整維度評分 {#adjust-dimension-scoring}

在本節中，您可以設定七個維度中的每一個對最終比對分數的貢獻度。 每個維度都可以設定為&#x200B;**[!UICONTROL 關閉]**、**[!UICONTROL 低]**、**[!UICONTROL Medium]**&#x200B;或&#x200B;**[!UICONTROL 高]**&#x200B;重要性。 每張卡片上顯示的百分比，是合併所有選取範圍後該維度的標準化貢獻 — 七個權重總是100%。 提高一個維度會自動將其他維度重新標準化，使總計保持在100%。

按一下「**[!UICONTROL 重設為等於]**」將所有維度恢復為均等加權。

![歷程流量控制 — 調整設定索引標籤上的維度評分卡](./assets/journey-traffic-control-configuration.png){width="800" zoomable="yes"}

### 模擬評分 {#simulate-scoring}

在將權重提交到生產環境之前，您可以模擬流量控制在這些變更中的行為。 模擬不需要啟用歷程流量控制。 它會評估您即時歷程中的設定檔，並將流量控制邏輯套用至設定檔，以便您判斷結果是否適合您所選的權重。

1. 選擇要模擬的設定檔數。

1. 按一下&#x200B;**[!UICONTROL 模擬評分]**。

結果標題會摘要說明執行：

* **已評估的設定檔** — 已評分的設定檔數，以及歷程數。
* **平均衝突/設定檔** — 每個設定檔的競爭歷程平均數量。
* **平均符合分數** — 所選歷程的平均信賴度。

![歷程流量控制 — 設定索引標籤 — 模擬評分結果](./assets/journey-traffic-control-configuration-simulate-scoring.png){width="700" zoomable="yes"}

在摘要下方，每個評估的設定檔都會顯示為卡片，其中顯示選取的歷程、關鍵理由、意圖訊號和比對分數。 選取要開啟詳細資料檢視的設定檔：

* **相符分數** — 整體相符專案，並依維度以色彩標示劃分。
* **決定** — 此人員符合資格的歷程、選取的歷程及原因。
* **按權重排序的Dimension分數** — 帶動決定的每個維度分數，可展開以顯示基礎訊號。

![歷程流量控制 — 模擬評分結果 — 設定檔詳細資料](./assets/journey-traffic-control-configuration-simulate-scoring-profile-details.png){width="450" zoomable="yes"}

當您對結果滿意時，您可以：

* 調整維度權重，然後按一下&#x200B;**[!UICONTROL 再次執行]**&#x200B;以重新執行模擬。

* 按一下&#x200B;**[!UICONTROL 套用至生產環境]**&#x200B;以認可權重。

  新的流量控制決定會立即使用新設定；過去的決定不會受到影響。 您測試的權重會顯示在主要&#x200B;_[!UICONTROL 組態]_&#x200B;標籤上，並用於您的即時環境中評估的任何歷程流量控制。

您也可以離開頁面而不套用權數。

<!--

This section does not appear in the staging environment

### Select journeys {#select-journeys}

The _[!UICONTROL Select journeys]_ section is where you choose which journeys participate in traffic control.

>[!IMPORTANT]
>
>Only draft journeys are available for selection. Traffic control cannot be enabled for a journey that is already live. When JTC is enabled for a journey and then that journey is published, it cannot be disabled.

-->

## 啟用歷程的流量控制 {#enable-traffic-control-journey}

當兩個或多個歷程啟用歷程流量控制並發佈時：

* 系統會根據其設定檔和歷程中繼資料，評估符合一或多個歷程資格的任何人。
* 如果人員同時符合數個啟用JTC的歷程（例如，五個）資格，則模型會判斷哪一個是當下最佳歷程，並僅將人員註冊至該歷程。 他們被拒之門外。
* 該人員會繼續進行該歷程，直到歷程完成。
* 完成後，系統會針對剩餘的合格歷程重新評估他們，並將其新增至下一個最佳歷程，重複直到沒有剩餘的合格歷程為止。

### 為草稿歷程啟用JTC {#enable-traffic-control-draft-journey}

當歷程處於&#x200B;_草稿_&#x200B;狀態時，可以直接在個別歷程上啟用歷程流量控制。<!-- This is the same setting surfaced from the admin/configuration flow — enabling it in either place keeps the two in sync. -->

1. 在左側導覽列中，展開&#x200B;**[!UICONTROL 行銷管理]**。

1. 在&#x200B;**[!UICONTROL 行銷]**&#x200B;資源清單的右側，選取&#x200B;**[!UICONTROL 個人歷程]**。

1. 按一下草稿人員歷程的名稱以開啟。

1. 按一下&#x200B;**[!UICONTROL ...其他]**&#x200B;位於右上方，然後選擇&#x200B;**[!UICONTROL 歷程流量控制設定]**。

   ![歷程流量控制 — 為草稿人員歷程啟用](./assets/journey-traffic-control-enable-journey.png){width="700" zoomable="yes"}

1. 在對話方塊中，啟用&#x200B;**[!UICONTROL 啟用歷程流量控制]**&#x200B;選項。

   此設定對話方塊會說明行為：啟用時，歷程會變成候選人，而模型會評估最適合的歷程，並建議符合多個作用中歷程資格的人員。

   ![歷程流量控制 — 啟用切換](./assets/journey-traffic-control-enable-dialog.png){width="380"}

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

>[!IMPORTANT]
>
>當歷程保持在&#x200B;_草稿_&#x200B;狀態時，可隨時變更切換。<!-- If it was already enabled from the admin section (or previously enabled by someone else), the toggle appears on. --> 在啟用JTC的情況下發佈歷程後，流量控制會評估進入該歷程的專案，您無法再停用設定。

### 最佳化歷程說明 {#optimize-journey-description}

流量控制代理能夠有效地使用歷程的中繼資料（歷程中的節點、對象名稱和類似的結構訊號）來通知其決策。 不過，豐富的描述性歷程描述可清楚說明歷程的宗旨和目標，因此受益匪淺。

強大的描述可為模型提供所需的情境，以便針對個人是否屬於該歷程或屬於競爭歷程做出更明智的決策。 當歷程非常基本時，這一點就最重要。 例如，只有少數節點的歷程提供有限的上下文，因此清楚說明其目標和目標對象有助於模型正確選擇。

>[!TIP]
>
>將歷程描述視為決策模型的輸入，而不僅僅是內部檔案。 說明歷程的目的（試圖達成的目標）、其目標以及預期對象。 說明越明確，當個人符合多個重疊歷程的資格時，流量控制就能越準確地進行仲裁，尤其是針對具有少量節點的輕量級歷程。

## 「報表」索引標籤 {#reporting-tab}

在兩個或多個歷程中啟用流量控制且執行完畢後，_[!UICONTROL 報告]_&#x200B;索引標籤會顯示結果。 有兩種檢視： **[!UICONTROL By run]**&#x200B;和&#x200B;**[!UICONTROL By journey]**。

### 依執行 {#by-run}

_[!UICONTROL By run]_&#x200B;檢視會列出每個流量控制執行。 對於每個執行，您都可以看到時間、觸發器（已排程或手動）、評估的活動歷程、評估的人員、流量控制決策、處理時間和狀態。 選取執行以開啟詳細資訊面板，其中包含執行的這些關鍵量度，以及在該執行中評估的歷程清單。

![歷程流量控制 — 「報告」標籤 — 依執行檢視](./assets/journey-traffic-control-reporting-tab-by-run.png){width="700" zoomable="yes"}

### 依歷程 {#by-journey}

使用&#x200B;_By歷程_&#x200B;檢視來檢查流量控制如何影響任何特定歷程。 此表格會顯示每個歷程中已評估、在此歷程中註冊、移至其他歷程且已處於作用中狀態的人員數量。

![歷程流量控制 — 報告標籤 — 依歷程檢視](./assets/journey-traffic-control-reporting-tab-by-journey.png){width="700" zoomable="yes"}

<!--
Selecting a journey opens a detail panel:

* **Summary** — Total people evaluated, broken down into _Enrolled in this journey_, _Moved to other journeys_, and _Already active_.
* **Competing journeys** — Every journey that had people competing with this one, and how many were enrolled in each.
* **People evaluated** — The individual people, each with an outcome (_Enrolled_, _Moved_, or _Already active_), competing journeys, and match score.

>[!TIP]
>
>The sum of enrolled people across all competing journeys always equals the _Moved to other journeys_ count in the summary. _Already active_ means the person was already in the journey when the evaluation occurred.

Selecting an individual person shows the same detail view as in simulation: the match score, the decision (competing journeys and which journey was selected and why), and the full dimension breakdown behind the selection.
-->
