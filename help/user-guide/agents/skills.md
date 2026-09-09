---
title: 同事技能
description: 在Marketo Optimizer中檢閱CX Enterprise Co-worker技能 — 適用於計畫、歷程、對象、評分、內容和傳送時間最佳化的封裝工作流程。
TQID: 'https://experienceleague.adobe.com/nNFB9UEghfqVvnBrNtTDnpnLUKKKMAU2nY1Pqt0KkUQ'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 581
ht-degree: 5%

---

# 同事技能

_技能_&#x200B;是同事知道如何執行的封裝工作流程 — `/`功能表和自然語言請求背後的建置組塊。 每個技能都隨附逐步指示和一個工作所需的特定工具（例如「發佈歷程」、「比較兩個人清單」、「建立評分模型」）。

>[!NOTE]
>
>每個技能都根據技能是否改變[!DNL Marketo Optimizer]或[!DNL Marketo Engage]狀態（**寫入**）、僅查詢/分析/產生（**讀取**），或具有同等的查詢+變異函式（**讀取+寫入**）進行分類。

## 方案與規劃 {#programs-planning}

| 技能 | 作用 | 存取權 | 產品表面 | 影響/資料流程 |
|---|---|---|---|---|
| `falco-program-creation` | 端對端[!DNL Marketo Optimizer]方案建立 — 方案、子資料夾、權杖、清單、歷程。 <p>請參閱&#x200B;_[從簡報建立方案](./program-from-brief.md)_。 | 寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer]。 |
| `adapt-program` | 從[!DNL Marketo Engage]個程式產生移轉劇本以進行[!DNL Marketo Optimizer]改寫。 | 讀取 | [!DNL Marketo Optimizer] | 讀取[!DNL Marketo Engage]，寫入[!DNL Marketo Optimizer] |
| `folder-creation` | 在資產樹狀結構中建立組織資料夾。 | 寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `program-creation` *（建置程式）* | 從行銷活動簡報建立Marketo方案。 | 寫入 | [!DNL Marketo Engage] | 讀取+寫入[!DNL Marketo Engage] |
| `program-planning` *（計畫行銷活動）* | 將簡報轉換為設定/實作檔案。 | 讀取 | [!DNL Marketo Engage] | 讀取[!DNL Marketo Engage] |
| `program-qa` *（驗證程式）* | 驗證/稽核方案（僅限規則、測試計畫或簡報）。 | 讀取 | [!DNL Marketo Engage] | 讀取[!DNL Marketo Engage] |

## 歷程 {#journeys}

| 技能 | 作用 | 存取權 | 產品 | 後端（資料流程） |
|---|---|---|---|---|
| `journey-creation` | 從自然語言建立及編輯個人歷程。 | 寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `journey-edit-dates` | 變更歷程的開始/結束日期，而不發佈。 | 寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `journey-publish` | 發佈/啟動/排程人員歷程。 | 寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `journey-stop` | 中止、關閉、停止、停止或終止歷程。 | 寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `journey-reentry` | 設定重新進入：允許/不允許、關閉、專案數上限。 | 寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `journey-trafficcontrol` | 執行顯示設定檔路由的流量控制模擬。 | 讀取 | [!DNL Marketo Optimizer] | 讀取[!DNL Marketo Optimizer] （模擬） |
| `journey-observability` | 偵錯/監視進度 — 路徑、時間、分割、停頓、停頓。 <p>檢視&#x200B;_[偵錯並監視歷程進度](./journey-observability.md)_。 | 讀取 | [!DNL Marketo Optimizer] | 讀取[!DNL Marketo Optimizer] + [!DNL Marketo Engage] （靜態清單檢查） |

## 對象和人員 {#audiences-people}

| 技能 | 作用 | 存取權 | 產品 | 後端（資料流程） |
|---|---|---|---|---|
| `audience-creation` | 調整[!DNL Marketo Engage]智慧清單、建立人員清單或新增/更新規則。 <p>請參閱&#x200B;_[建立方案的對象](./audience-creation.md)_。 | 寫入 | [!DNL Marketo Optimizer] | 讀取[!DNL Marketo Engage] +讀取/寫入[!DNL Marketo Optimizer]。 |
| `people-list-comparison` | 比較兩個人員清單並顯示重疊的成員。 | 讀取 | [!DNL Marketo Optimizer] | 讀取[!DNL Marketo Optimizer] |
| `import-leads` | 檢查CSV資料品質並將匯入認可至[!DNL Marketo Engage]。 | 讀取+寫入 | 兩者 | 讀取+寫入[!DNL Marketo Engage] |
| `lead-investigation` *（調查銷售機會）* | 調查銷售機會的活動、評分、資格、生命週期。 | 讀取 | [!DNL Marketo Engage] | 讀取[!DNL Marketo Engage] |

## 內容和頻道 {#content-channels}

| 技能 | 作用 | 存取權 | 產品 | 後端（資料流程） |
|---|---|---|---|---|
| `content-personalization` | 瀏覽/預覽範本及編輯內容/產生變體。 | 讀取+寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer]。 請參閱&#x200B;_[依角色個人化電子郵件內容](./personalize-content.md)_。 |
| `asset-tokens` | 程式/資料夾/歷程上的完整權杖CRUD。 | 讀取+寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `fcs-channels` | 管道查詢和CRUD +發佈/停止/刪除。 | 讀取+寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |

## 評分和訊號 {#scoring-signals}

| 技能 | 作用 | 存取權 | 產品 | 後端（資料流程） |
|---|---|---|---|---|
| `scoring-studio` | 列出/取得評分模型並建置/發佈。 <p>請參閱&#x200B;_[建立自訂評分模型](./lead-scoring-model.md)_。 | 讀取+寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] （評分服務）；讀取[!DNL Marketo Engage]潛在客戶欄位/活動型別。 |
| `engagementconfiguration` | 顯示參與設定和編輯/更新權重。 | 讀取+寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `intentconfiguration` | 顯示意圖設定和設定/更新權重。 | 讀取+寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `intent-query` | 依人員/區段/清單查詢及說明意圖分數。 | 讀取 | [!DNL Marketo Optimizer] | 讀取[!DNL Marketo Optimizer] |

## 傳送時間最佳化 {#sto}

| 技能 | 作用 | 存取權 | 產品 | 後端（資料流程） |
|---|---|---|---|---|
| `send-time-optimization` | 檢查STO狀態，並在電子郵件節點上啟用/停用。 | 讀取+寫入 | [!DNL Marketo Optimizer] | 讀取+寫入[!DNL Marketo Optimizer] |
| `send-time-report` | 擷取/顯示STO效能報表。 | 讀取 | [!DNL Marketo Optimizer] | 讀取[!DNL Marketo Optimizer] |

## 知識 {#knowledge}

| 技能 | 作用 | 存取權 | 產品 | 後端（資料流程） |
|---|---|---|---|---|
| `product-knowledge` | 從Experience League上的[!DNL Marketo Optimizer]份檔案回答操作說明/概念問題。 | 讀取 | 兩者 | 讀取外部檔案 — 無產品資料 |

## 跨後端 {#cross-backend}

這些技能跨越多個後端：

- **`adapt-program`** — `gather_program_assets`讀取[!DNL Marketo Engage] (`get_program`， `get_smart_campaign`， `list_emails`)，然後透過`falcomcp_create_journey`寫入 — 傳統跨後端。
- **`audience-creation`** — 讀取[!DNL Marketo Engage]個智慧清單(`get_smart_list` / `get_smart_campaign`)，然後寫入[!DNL Marketo Optimizer]個人清單。
- **`journey-observability`** — [!DNL Marketo Optimizer]讀取加上`check_lead_in_marketo_static_list` [!DNL Marketo Engage]讀取。
- **`scoring-studio`** — 同時讀取[!DNL Marketo Engage]個銷售機會欄位/活動型別和[!DNL Marketo Optimizer]計分服務。

所有`falco-mcp_*`和歷程/權杖/評分/STO/FCS工具點選[!DNL Marketo Optimizer]服務；CSV/方案/潛在客戶工具點選[!DNL Marketo Engage]。
