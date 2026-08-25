---
title: 高階架構
description: 瞭解連線Marketo Optimizer和Marketo Engage的資料架構，包括雙向同步、實體延遲和租使用者資料隔離。
role: User, Admin
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 2%

---


# 高階架構

[!DNL Adobe Marketo Optimizer]與[!DNL Adobe Marketo Engage]整合，提供B2B銷售機會的360度檢視。 雙向的受信任同步可讓Marketo Engage和Marketo Optimizer保持一致，並為兩個平台提供人員、公司、自訂物件和活動的單一共用檢視。 高效能、近乎即時的資料流程可確保記錄保持最新且易於操作，因此行銷活動和歷程可以在潛在客戶參與時做出回應。

## 資料基礎

[!DNL Marketo Optimizer]和[!DNL Marketo Engage]共用一個共同資料基礎，可讓兩個平台在饋送下游分析時保持同步。

![Marketo Optimizer和Marketo Engage架構圖表，顯示這兩個產品的服務、執行階段和資料存放區如何跨Microsoft Azure和AWS連線](./assets/marketo-optimizer-architecture.svg)

概言之：

* **Marketo Engage Core**&#x200B;是潛在客戶和自訂物件資料的確定來源，確保擷取時的資料完整性。
* **資料代理人層**&#x200B;可協調資料在Marketo Engage和Marketo Optimizer之間的移動方式，將共用和複製的資料彙總到可操作、可立即使用的環境中。 此整個交換會在單一共用AWS Aurora執行處理中執行，形成高階B2B協調流程的封閉回圈基礎。
* **活動**&#x200B;會依循定義的路徑：會先將活動寫入Marketo Engage資料庫，並在Apache SOLR中編列索引，以快速進行產品內搜尋，然後再發佈至活動管道，讓Marketo Optimizer立即生效。 Journey Runtime會處理該活動並將其寫入Snowflake，將營運資料轉換為可立即進行分析的狀態。 之後，系統會將活動復寫至AEP資料集和CJA，以支援報表。
* 不同的實體型別會以不同的速度和方向同步處理，以平衡新鮮度與系統完整性：

| Marketo Engage實體 | 同步方向 | 延遲性 |
| --- | --- | --- |
| 商機 | 雙向 | &lt; 1秒 |
| 公司 | 雙向 | &lt; 1秒 |
| 自訂物件 | 單向 | &lt; 5秒 |
| 活動 | 單向 | &lt; 5秒 |
| 計畫會籍 | 未同步 | — |
| 資產 | 未同步 | — |

潛在客戶與公司會立即雙向更新，不會建立重複的資料復本。 自訂物件會在數秒內複製，因此Marketo Engage中的結構描述更新可在使用中的歷程中立即操作。 程式成員資格和Assets會刻意排除在同步之外，以保留系統速度和完整性。

這種近乎零延遲的設計意味著，分析儀表板和下游系統以近乎即時的方式提供，使得活動最佳化即時發生，並對高優先順序的潛在客戶進行快速後續追蹤。

### 資料隔離與租用

* 客戶資料會在Marketo Engage、Marketo Optimizer和Experience Platform之間共用，作為產品資料同步和Analytics架構的一部分。
* 資料會依租使用者進行邏輯隔離，並受到Adobe安全性控制的保護。
* 資料會透過安全、加密的通道傳輸，並使用業界標準的加密和存取控制儲存在Adobe管理的服務中。
* 根據資料型別，資訊可能會在Marketo Engage和Marketo Optimizer之間同步化，或複製到Experience Platform以支援報告和分析功能，同時維持安全性和租使用者隔離。
