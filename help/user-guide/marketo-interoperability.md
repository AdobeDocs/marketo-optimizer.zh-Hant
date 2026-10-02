---
title: 與Marketo Engage的互通性
description: 瞭解Marketo Optimizer與Marketo Engage共用哪些內容（包括資料、活動和對象），以及如何在您的歷程中從任一產品傳送電子郵件。
role: User, Admin
autotag-review: '2026-10-01T18:40:01.444Z'
TQID: 'https://experienceleague.adobe.com/7TB6JG9yiUT-l0VevNW4tvwieCyFjOypZwI0SlUzmmY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
    internal-label: Audiences
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
  - id: d4203578-d294-5145-b397-f26f4488a904
    internal-label: Channels
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 518a807aeed2471772b4f0a4d6d8d525cd3e22fd
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%
---

# 與Marketo Engage的互通性

[!DNL Adobe Marketo Optimizer]和[!DNL Adobe Marketo Engage]會共用資料、某些活動和對象。 它們會將資產分開。 瞭解各產品共用的內容，以決定建置和傳送行銷的位置。

## 在產品之間共用 {#shared}

* [!DNL Marketo Engage]個銷售機會和活動會自動流入[!DNL Marketo Optimizer]。
* 歷程可以接聽[!DNL Marketo Engage]活動。
* 事件型對象可以包含執行[!DNL Marketo Engage]活動的人員。
* 歷程動作可以與[!DNL Marketo Engage]互動。 您可以在[!DNL Marketo Engage]清單中新增或移除人員，以及請求[!DNL Marketo Engage]行銷活動。
* [!UICONTROL 評分工作室]針對[!DNL Marketo Engage]和[!DNL Marketo Optimizer]活動對人進行評分。 您可以在[!DNL Marketo Engage]中使用分數。
* 這兩種產品會共用IP位址和子網域。
* 統一的對話式報告涵蓋兩種產品。

## 保持獨立 {#separate}

* **Assets：**&#x200B;電子郵件、範本、程式和影像會存放在不同的存放庫中。
* **活動：** [!DNL Marketo Optimizer]活動未共用回[!DNL Marketo Engage]。
* **欄位和限制：**&#x200B;衍生自[!DNL Marketo Optimizer]的角色欄位在[!DNL Marketo Engage]中無法使用。 每個產品會個別設定通訊限制。

如需同步處理詳細資料，請參閱[實體同步處理](./data-architecture.md#entity-sync)。

## 從Marketo Engage傳送電子郵件 {#send-from-marketo}

在[!DNL Marketo Engage]傳送每封電子郵件時，使用此方法在[!DNL Marketo Optimizer]中執行歷程、等待步驟和AI決策。

1. 在[!DNL Marketo Optimizer]中，建置包括等待步驟和AI決策的歷程。
1. 對於每個傳送步驟，新增&#x200B;**[!UICONTROL 請求Marketo Engage行銷活動]**&#x200B;動作並選取相符的[!DNL Marketo Engage]行銷活動。
1. 可選：在[!DNL Marketo Engage]中新增預設、總體方案，以彙總整個歷程的成功報告。

如需動作詳細資料，請參閱[採取動作節點](./marketing/action-nodes.md)。

[!DNL Marketo Engage]會透過您現有的頻道設定傳送電子郵件。 由於[!DNL Marketo Engage]會傳送電子郵件，因此您不會在[!DNL Marketo Optimizer]中設定頻道或電子郵件。 此外：

* 傳送、開啟和點按記錄在[!DNL Marketo Engage]中。
* [!DNL Marketo Engage]中套用取消訂閱管理和電子郵件治理。
* 電子郵件活動摘要您現有的[!DNL Marketo Engage]評分行銷活動。
* 活動觸發的Salesforce同步促銷活動如預期般執行。
* 每個傳送對應至[!DNL Marketo Engage]行銷活動，因此您可追蹤每個電子郵件行銷活動的方案會籍，並在熟悉的方案中進行報告。

## 從Marketo Optimizer傳送電子郵件 {#send-from-optimizer}

使用此方法來建立歷程，並在[!DNL Marketo Optimizer]中完整傳送電子郵件。 [!DNL Marketo Engage]仍舊是移交給客戶關係管理(CRM)系統的記錄系統。

1. 設定電子郵件頻道。 建立電子郵件範本，並設定IP位址和子網域、取消訂閱連結和登陸頁面。 檢視[電子郵件傳遞能力](./start/email-deliverability.md)。
1. 在[!DNL Marketo Optimizer]中設定通訊限制。 共用通訊限制無法使用。
1. 使用受眾、AI決策和下一個最佳路徑建立歷程。
1. 從[!DNL Marketo Optimizer]傳送電子郵件。 [!DNL Marketo Optimizer]會記錄活動。
1. 對[!UICONTROL 評分工作室]中的人員評分，以在[!DNL Marketo Engage]和[!DNL Marketo Optimizer]活動中建立一個模型。 檢視[評分工作室](./labs/scoring-studio.md)。

取消訂閱會透過共用欄位自動同步至[!DNL Marketo Engage]。 [!DNL Marketo Optimizer]電子郵件活動未傳回[!DNL Marketo Engage]，但[!UICONTROL 評分工作室]仍使用它。

### 將銷售機會交給銷售人員 {#hand-off}

[!DNL Marketo Optimizer]沒有直接的CRM整合。 使用下列其中一種方法透過[!DNL Marketo Engage]路由銷售機會：

* **以分數為基礎：**&#x200B;分數欄位會顯示在[!DNL Marketo Engage]中，而智慧型行銷活動會將潛在客戶同步至您的CRM。
* **以活動為基礎：** [!DNL Marketo Optimizer]歷程會接聽此活動，並將銷售機會新增至[!DNL Marketo Engage]智慧型行銷活動。
* **計畫成員資格：**&#x200B;歷程位於[!DNL Marketo Optimizer]計畫中，因此您會從頭到尾追蹤狀態。
