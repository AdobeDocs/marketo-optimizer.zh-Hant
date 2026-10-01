---
title: 資料架構
description: 瞭解Marketo Optimizer和Marketo Engage如何共用資料，包括實體同步方向和延遲、活動資料流程以及基於沙箱的資料隔離。
role: User, Admin
autotag-review: '2026-10-01T18:40:38.362Z'
TQID: 'https://experienceleague.adobe.com/oelEtys81g6TzM8bi-qy1nuWw6scOBry7tbZkMkZ6u0'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 1%
---

# 資料架構

[!DNL Adobe Marketo Optimizer]與[!DNL Adobe Marketo Engage]整合，以提供B2B銷售機會的完整檢視。 雙向信任同步可讓兩個產品保持一致，以便共用人員、公司、自訂物件和活動的單一檢視。 [!DNL Marketo Engage]仍然是個人資料的權威來源。 每個[!DNL Marketo Optimizer]執行個體都與一個[!DNL Marketo Engage]執行個體配對。

## 資料基礎 {#data-foundation}

[!DNL Marketo Optimizer]和[!DNL Marketo Engage]共用一個共同資料基礎，在饋送下游分析時會保持同步化。

![Marketo Optimizer和Marketo Engage架構圖表，顯示這兩個產品的服務、執行階段和資料存放區如何跨Microsoft Azure和AWS連線](./assets/marketo-optimizer-architecture.svg)

概言之：

* **[!DNL Marketo Engage]**&#x200B;是潛在客戶和自訂物件資料的確定來源，可確保擷取點上的資料完整性。
* **資料代理人層**&#x200B;會協調資料在兩個產品之間的移動方式。 它會將共用和複製的資料彙總到可以使用的作業資料庫中。 整個Exchange會在單一Aurora MySQL叢集中執行。
* **[!DNL Marketo Optimizer]**&#x200B;是所執行歷程活動的權威來源。

## 實體同步 {#entity-sync}

每個實體型別都會以最能保護資料完整性的方向和速度進行同步。

| [!DNL Marketo Engage]實體 | 同步方向 | 延遲性 |
| --- | --- | --- |
| 商機 | 雙向 | 1秒以下 |
| 公司 | 雙向 | 1秒以下 |
| 自訂物件 | 單向 | 5秒以下 |
| 活動 | 單向 | 5秒以下 |
| 計畫會籍 | 未同步 | 不適用 |
| 資產 | 未同步 | 不適用 |

同步化的運作方式有兩種：

* **潛在客戶、公司和標準物件：** [!DNL Marketo Engage]擁有人員資料表，並透過讀取和寫入資料庫檢視來共用它。 一個產品中的更新會立即出現在另一個產品中，且不會建立重複的復本。
* **自訂物件：**&#x200B;資料會在數秒內從[!DNL Marketo Engage]復寫。 [!DNL Marketo Engage]中的結構描述更新可立即供使用中的歷程使用。

[!DNL Marketo Engage]和[!DNL Marketo Optimizer]未同步處理方案成員資格或資產。 此排除保留系統速度和完整性。

>[!NOTE]
>
>與[!DNL Marketo Optimizer]和資料倉儲同步處理的資料最終是一致的。 計時取決於基礎變更資料擷取、批次或串流機制。

這種近乎即時的設計可為您提供歷程與報表中的目前資料。 您可以快速追蹤高優先順序的潛在客戶。 您也可以在歷程決定變更時使用B2B內容資料，例如產品使用情況和意圖。

## 活動資料流程 {#activity-flow}

活動會遵循與其他實體不同的路徑。 每個活動會經過五個階段：

1. **主要擷取：** [!DNL Marketo Engage]會將活動寫入其共用資料庫，並在Apache SOLR中編制索引，以便在[!DNL Marketo Engage]內進行快速搜尋。
1. **跨產品感知度：** [!DNL Marketo Engage]已發佈活動到活動管道，因此[!DNL Marketo Optimizer]會立即收到。
1. **分析轉換：**&#x200B;歷程執行階段會處理活動並將其寫入Snowflake，以將作業資料轉換為可分析的資料。 目前在Amazon Web Services (AWS)中執行的所有階段。
1. **下游目的地：** [!DNL Marketo Optimizer]已將活動復寫至[!DNL Adobe Experience Platform]個資料集。
1. **報告：**&#x200B;資料集摘要內嵌[!DNL Adobe Customer Journey Analytics]報告。 [!DNL Customer Journey Analytics]可以在Microsoft Azure或AWS上託管。 您也可以使用[!DNL Query Service]查詢資料集。 檢視[Experience Platform資料集](./reports/aep-datasets.md)。

歷程和事件對象可同時使用[!DNL Marketo Optimizer]個活動和[!DNL Marketo Engage]個活動的子集。 這兩個集合的使用方式相同。 [!DNL Marketo Optimizer]個活動未傳回[!DNL Marketo Engage]。

使用表單填寫、網站造訪和電子郵件參與等活動來觸發、篩選和分支人員歷程：

* [監聽事件節點的事件觸發程式](./marketing/listen-for-event-nodes.md#event-triggers)
* [監聽事件節點的事件篩選器](./marketing/listen-for-event-nodes.md#event-filters)
* [分割路徑節點的相符人員篩選器](./marketing/split-merge-paths-nodes.md#matched-person-filters)
* [事件型對象](./audiences/event-based-audiences.md)

## 資料隔離和沙箱 {#data-isolation}

[!DNL Marketo Engage]、[!DNL Marketo Optimizer]和[!DNL Experience Platform]在此架構中共用客戶資料。 Adobe會使用[!DNL Experience Platform]沙箱，以邏輯方式將您的資料與其他租使用者隔離。 資料會透過安全、加密的通道移動。 Adobe會將其儲存在Adobe Managed Services中，並使用業界標準的加密和存取控制。

每個[!DNL Marketo Optimizer]執行個體在[!DNL Adobe Admin Console]中都有一個專用產品卡和一個專用沙箱。 Adobe會自動布建二者，因此您不會建立沙箱。 沙箱名稱使用模式`mktoaep<prefix>`，其中首碼是您的[!DNL Marketo Engage]首碼。 如果您搭配多個[!DNL Marketo Engage]執行個體使用[!DNL Marketo Optimizer]，則每個執行個體都有自己的產品卡和沙箱。

[!DNL Marketo Optimizer]僅在此沙箱中可用，即使您的組織有其他沙箱。

布建不會指派沙箱存取權。 角色通常具有預設`prod`沙箱的存取權，但[!DNL Marketo Optimizer]未使用它。 明確指派專用沙箱給每個[!DNL Experience Platform]角色，否則使用者無法在[!DNL Marketo Optimizer]中工作。 使用使用者群組來新增和移除使用者，而不重複角色設定。 如需完整程式，請參閱[使用者存取權和許可權](./start/user-management.md)。

[!DNL Marketo Optimizer]也在背景使用[!DNL Experience Platform]服務。 這些包括結構描述登入、付費媒體匯出的目的地、存取控制以及[!DNL Customer Journey Analytics]。 您未設定結構描述或名稱空間。 [!DNL Marketo Optimizer]不需要[!DNL Real-Time Customer Data Platform]、即時客戶設定檔或分段。

>[!WARNING]
>
>請勿刪除專用的[!DNL Marketo Optimizer]沙箱。 刪除是永久性的，無法復原。 重新布建[!DNL Marketo Optimizer]以復原。
