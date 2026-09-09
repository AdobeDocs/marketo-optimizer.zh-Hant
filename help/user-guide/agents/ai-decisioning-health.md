---
title: AI-Decisioning健康狀態
description: 瞭解AI決策健康情況如何在Marketo Optimizer中檢查潛在客戶涵蓋範圍、角色分類和訊號豐富度，並標示缺少的專案。
TQID: 'https://experienceleague.adobe.com/rZy9gOQusGt2mfZ3t0iBS2blVp1PXH-R-TIW5cGWu2Y'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 5229c72e-d79b-574f-a03e-5c4bf48172c3id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 801
ht-degree: 0%

---


# AI決策健康狀態

AI-decisioning健康狀態會檢查在[!DNL Adobe Marketo Optimizer]中提供個人化支援的資料。 它會報告跨人口統計、第一類、技術類和心理分析類的潛在客戶涵蓋範圍、角色分類和故事豐富度。 然後它會標示遺失的資料，以識別從何處開始。

使用AI決策健全狀態來檢視哪些資料從[!DNL Marketo Engage]流入，以及哪些地方有間隙。 縮小這些差距可改善[AI決策](./ai-decisioning.md)對每個人評分和路由的方式。

## 開啟AI決策健康狀態 {#open}

從首頁或同事聊天中開啟報表。

* 在&#x200B;_首頁_&#x200B;頁面上，選取「快速存取」列中的&#x200B;**[!UICONTROL AI-decisioning健康狀態]**&#x200B;卡。 卡片會引領列，並顯示劇本數量和角色分類進度，例如929個劇本、32%角色分類。
* 在同事聊天方塊中，直接詢問您的個人化資料，或輸入`/`並選取&#x200B;**[!UICONTROL AI決策健康狀態]**。

![首頁上的快速存取列，首先顯示AI-decisioning健康狀態卡，然後是行銷、Assets和報告。](./assets/ai-decisioning-health-quick-access.png){width="600"}

兩個路徑都會在「同事」工作區中開啟報表。

## 聊天歡迎和後續提示 {#chat-welcome}

從聊天室開啟AI-decisioning健全狀態會顯示歡迎訊息、_[!UICONTROL *歡迎使用AI-decisioning健全狀態]_、報告檢查摘要以及用來開啟完整報告的卡片。

在卡片下方的&#x200B;_[!UICONTROL 您接下來要做什麼？]_&#x200B;下方，AI決策健康狀態會根據您自己的資料的特定間隙，建議後續提示。 例如，如果67.7%的銷售機會沒有角色分類，則一個建議的提示會顯示&#x200B;_為什麼67.7%的銷售機會未依角色分類？_ 選取建議的提示，或詢問您自己的問題，直接獲得答案而不離開聊天。

![同事聊天面板，顯示AI決策健全狀態的歡迎訊息、開啟報告的卡片，以及四個建議的後續提示。](./assets/ai-decisioning-health-highlights.png){width="800" zoomable="yes"}

## 報表概觀 {#report-overview}

工作區報告開啟時具有&#x200B;**[!UICONTROL 亮點]**&#x200B;圖說文字，以純文字列出您資料中最強和最弱的區域，例如&#x200B;_人口統計資料達到100%具有強欄位深度的銷售機會_&#x200B;或&#x200B;_67.7%的銷售機會仍未分類為任何角色_。 核取記號會標籤健康的結果，而斜圓會標籤間隙。

在亮點旁邊，雷達圖繪製六個維度的整體&#x200B;**[!UICONTROL 涵蓋範圍]**：人口統計、第一圖、技術圖、心理圖、角色和意圖。 陰影區域越大，涵蓋範圍越廣。

## 角色分類 {#persona-classification}

**[!UICONTROL 角色分類]**&#x200B;區段會顯示有多少個劇本分類為角色，例如： 929個已分類劇本中的&#x200B;_300 · 32.3%已分類· 67.7%未分類_。 棧疊長條圖會依角色劃分分類故事，圖例會顯示每個故事的故事計數和百分比。

選取角色區段，以開啟包含該角色職稱範例的詳細資訊卡。 例如，**[!UICONTROL 其他]**&#x200B;區段可能顯示： _272個故事/ 29.3%_，例如業界專家、獨立顧問、自由職業顧問和主題專家。

## 涵蓋範圍 {#coverage}

**[!UICONTROL 涵蓋範圍]**&#x200B;區段列出五個資料類別：人口統計、第一組態、技術、心理變數，以及意圖和活動。 每個類別會顯示該類別中至少有一個可用屬性的內文百分比。

選取類別以將其展開，然後選擇以下兩個標籤之一：

* **[!UICONTROL 屬性]** — 依型別分組的屬性，例如個人詳細資訊或人口統計下的位置。 每個屬性會顯示有多少內文具有值，例如： `firstName (906 stories)`。
* **[!UICONTROL 旗標]** — 該類別的特定差距，或是&#x200B;_當涵蓋範圍正常時，此類別上沒有_&#x200B;開啟的旗標。

使用類別清單上方的搜尋欄位，可依名稱直接跳至類別或屬性。

![已展開人口統計類別的「涵蓋範圍」區段，顯示「個人詳細資料」、「參與計分」和「位置」等屬性群組。](./assets/ai-decisioning-health-coverage.png){width="800" zoomable="yes"}

## 標幟 {#flags}

報表底部的&#x200B;**[!UICONTROL 旗標]**&#x200B;區段會列出所有類別中發現的每個差距，依嚴重程度排名：

* **[!UICONTROL 關鍵]** — 完全封鎖功能的間隙，例如&#x200B;_技術涵蓋範圍在所有潛在客戶_&#x200B;為0%。
* **[!UICONTROL 觀看]** — 降低效能但不會阻礙功能的差距，例如&#x200B;_心理涵蓋範圍只佔潛在客戶的7.2%_。

依嚴重性篩選清單，然後選取旗標以展開清單並讀取其業務影響的一句說明，例如： _未分類的銷售機會無法進入個人專屬歷程或接收角色專屬的訊息，從而降低行銷活動相關性和轉換率。_

![旗標區段已篩選為Watch嚴重性，顯示三個旗標，其中一個已展開，以顯示其業務影響說明。](./assets/ai-decisioning-health-flags.png){width="800" zoomable="yes"}

## 最近存取 {#recently-accessed}

如果您開啟AI決策運作狀況，然後導覽到別處，它就會重新出現在空白工作區的&#x200B;**[!UICONTROL 最近存取的]**&#x200B;下方，這樣您就可以跳回到報告而不回到首頁。

![最近存取的清單顯示AI-decisioning健康情況為最近專案，在Scoring Studio之前。](./assets/ai-decisioning-health-recently-accessed.png){width="500"}

>[!BEGINSHADEBOX]

計畫中的AI決策健全性增強功能包括：

* 同事技能目錄中的專屬專案。
* 引導式「詢問如何進行」動作，引導您修正標幟。
* 專屬的後續步驟標籤。

>[!ENDSHADEBOX]
