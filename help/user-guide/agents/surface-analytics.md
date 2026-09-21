---
title: 產生Analytics報表
description: 瞭解如何在同事聊天中使用Surface Analytics技能，以從自然語言提示產生活動、電子郵件、銷售機會、區段和歷程報告。
autotag-review: '2026-09-21T14:58:26.479Z'
TQID: 'https://experienceleague.adobe.com/BSDEihjdpz-YZjMWrYTmIuyjqtcjRHRrJdz4xPFZbHU'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 3c1de303-7a7c-59a6-abca-8c534730e19c
    internal-label: Reporting
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 1dcc3bcdc59114c7fc1e16178db8921ae173b955
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%
---
# 產生分析報表

[!DNL Adobe Marketo Optimizer]中的&#x200B;[_Surface Analytics_&#x200B;技能](./skills.md#analytics-reporting)回答有關您資料的自然語言問題。 在[同事聊天介面](./chat-interface.md)中使用它來探索活動趨勢、電子郵件績效、潛在客戶與帳戶資料、區段與清單成員資格，以及歷程量度。 結果會以圖表和表格形式傳回，因此您不需要手動建立查詢或控制面板。

* **技能** - `surface-analytics`
* **引動** — 以自然語言提出問題，或使用斜線命令執行Surface Analytics技能。 例如： _&quot;顯示過去30天的每日活動計數。&quot;_
* **從**&#x200B;讀取 — [!DNL Marketo Optimizer]分析資料；針對同時涵蓋兩個產品的問題，讀取[!DNL Marketo Engage]分析資料

>[!NOTE]
>
>報告資料每兩小時會重新整理一次。 結果可能不會反映過去兩小時的活動。

## 檢視活動趨勢 {#activity-trends}

詢問每日或每週活動計數，並按活動型別或產品區域劃分結果。

* _&quot;顯示過去30天的每日活動計數。&quot;_
* _「本週最受歡迎的活動型別為何？」_
* _「依應用程式區域劃分上個月的活動。」_

## 檢查電子郵件效能 {#email-performance}

詢問您的電子郵件程式的傳送量、開啟與點按率、退回與取消訂閱等事項。

* _&quot;依據歷程的電子郵件開啟率是多少？&quot;_
* _&quot;顯示過去90天的點選率。&quot;_
* _「上週我們得到了多少個取消訂閱？」_

## 分析銷售線索與帳戶資料 {#lead-account-data}

詢問潛在客戶評分分佈、角色劃分，以及地理或實體統計。

* _&quot;顯示潛在客戶的評分分佈。&quot;_
* _「每個帳戶有多少人？」_
* _「依角色劃分銷售機會。」_

## 檢閱區段和清單成員資格 {#segment-list-membership}

詢問誰屬於特定清單或區段。

* _「Q1 Nurture清單中有多少人？」_
* _&quot;哪個區段有最多成員？&quot;_

## 探索歷程量度 {#journey-metrics}

詢問歷程成員資格、完成率、節點周遊和funnel分析。

* _「示範後續追蹤歷程的完成率是多少？」_
* _「LeadNurtureJourney的每個節點有多少人？」_

## 跨產品提出問題 {#cross-product}

Surface Analytics可在單一提示中回答同時涵蓋[!DNL Marketo Engage]和[!DNL Marketo Optimizer]資料的問題。

* _「什麼是我在LumaSecure和LumaStorage中表現最佳的電子郵件？」_

## 限制 {#limitations}

| 限制 | 詳細資料 |
|---|---|
| 編輯或建立記錄 | 不支援。 Surface Analytics只會讀取和報告現有資料。 |
| 結果中人類可讀的名稱 | 並非總是可用。 有些報表會顯示內部ID，例如歷程或電子郵件ID，而非名稱。 |
| 複製報告卡 | 一個問題偶爾會針對相同結果傳回多個報告卡。 |
