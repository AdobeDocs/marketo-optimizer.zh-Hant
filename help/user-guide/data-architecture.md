---
title: 高階架構
description: 瞭解連線Marketo Optimizer和Marketo Engage的資料架構，包括雙向同步、實體延遲和租使用者資料隔離。
role: User, Admin
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3c1de303-7a7c-59a6-abca-8c534730e19cid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d00e9f03-e50b-4162-b143-0c0817c937c2id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 1%

---


# 高階架構

[!DNL Adobe Marketo Optimizer]與[!DNL Adobe Marketo Engage]整合，提供B2B銷售機會的360度檢視。 雙向信任同步可讓[!DNL Marketo Engage]和[!DNL Marketo Optimizer]保持一致，讓兩個平台都擁有使用者、公司、自訂物件和活動的單一共用檢視。 高效能、近乎即時的資料流程可確保記錄保持最新且易於操作，因此行銷活動和歷程可以在潛在客戶參與時做出回應。

## 資料基礎

[!DNL Marketo Optimizer]和[!DNL Marketo Engage]共用一個共同資料基礎，在饋送下游分析時會保持同步化。

![Marketo Optimizer和Marketo Engage架構圖表，顯示這兩個產品的服務、執行階段和資料存放區如何跨Microsoft Azure和AWS連線](./assets/marketo-optimizer-architecture.svg)

概言之：

* **[!DNL Marketo Engage]Core**&#x200B;是潛在客戶和自訂物件資料的確定來源，確保擷取點上的資料完整性。
* **資料代理人層**&#x200B;協調資料在[!DNL Marketo Engage]和[!DNL Marketo Optimizer]之間的移動方式，將共用和復寫資料彙總到可操作、隨時使用的環境中。 此整個交換會在單一共用AWS Aurora執行處理中執行，形成高階B2B協調流程的封閉回圈基礎。
* **活動**&#x200B;遵循已定義的路徑：活動會先寫入[!DNL Marketo Engage]資料庫並在Apache SOLR中編列索引，以快速進行產品內搜尋，然後發佈至活動管道，讓[!DNL Marketo Optimizer]立即感知。 Journey Runtime會處理該活動並將其寫入Snowflake，將作業資料轉換為可分析狀態。 從該位置，活動已復寫到[!DNL Adobe Experience Platform]個資料集和[!DNL Adobe Customer Journey Analytics]以支援報告。
* 不同的實體型別會以不同的速度和方向同步處理，以平衡新鮮度與系統完整性：

| [!DNL Marketo Engage]實體 | 同步方向 | 延遲性 |
| --- | --- | --- |
| 商機 | 雙向 | &lt; 1秒 |
| 公司 | 雙向 | &lt; 1秒 |
| 自訂物件 | 單向 | &lt; 5秒 |
| 活動 | 單向 | &lt; 5秒 |
| 計畫會籍 | 未同步 | — |
| 資產 | 未同步 | — |

潛在客戶與公司會立即雙向更新，不會建立重複的資料復本。 自訂物件會在數秒內復寫，因此[!DNL Marketo Engage]中的結構描述更新可在使用中的歷程中立即操作。 程式成員資格和Assets會刻意排除在同步之外，以保留系統速度和完整性。

這種近乎零延遲的設計意味著，分析儀表板和下游系統以近乎即時的方式提供，使得活動最佳化即時發生，並對高優先順序的潛在客戶進行快速後續追蹤。

### 資料隔離與租用

* 客戶資料會在[!DNL Marketo Engage]、[!DNL Marketo Optimizer]和[!DNL Experience Platform]之間共用，作為產品資料同步和分析架構的一部分。
* 資料會依租使用者進行邏輯隔離，並受到Adobe安全性控制的保護。
* 資料會透過安全、加密的通道傳輸，並使用業界標準的加密和存取控制儲存在Adobe管理的服務中。
* 視資料型別而定，資訊可能會在[!DNL Marketo Engage]和[!DNL Marketo Optimizer]之間同步處理，或復寫到[!DNL Experience Platform]以支援報告和分析功能，同時維持安全性與租使用者隔離。
