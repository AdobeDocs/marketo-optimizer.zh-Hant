---
title: 監視和偵錯Journey Progression
description: 瞭解如何在同事聊天中使用歷程可觀察性技能，以偵錯和監視人員和潛在客戶如何在歷程、分割路徑決策和時間中移動。
source-git-commit: 9db94582512d95f6c07d4e978a0a27291b471900
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 0%

---

# 監視和偵錯歷程進度

[!DNL Adobe Marketo Optimizer]中的&#x200B;[_歷程可觀察性_&#x200B;技能](./skills.md#journeys)回答有關人和潛在客戶如何在歷程中移動的自然語言問題。 在[同事聊天介面](./chat-interface.md)中使用它來追蹤進度、瞭解分割路徑決策、分析歷程節點中的人員以及檢查計時量度。 您也可以詢問歷程中的行為模式。

* **技能** - `journey-observability`
* **引動** — 以自然語言提出問題，或使用斜線命令執行歷程可觀察性技能。 例如： _「demo_ lead_24@company.com如何移動LeadNurtureJourney？」_
* **從**&#x200B;讀取 — [!DNL Marketo Optimizer]歷程資料；讀取[!DNL Marketo Engage]靜態清單以檢查清單成員資格

## 檢視個人或潛在客戶詳細資訊 {#person-details}

詢問有關個人的基本唯讀詳細資訊，或在您調查其歷程之前建立上下文。 提供人員的電子郵件地址、銷售機會ID或銷售機會名稱。

* _「提供潛在客戶demo_ lead_24@company.com的基本資訊。」_
* _&quot;設定檔john.doe@company.com的職稱和國家/地區為何？&quot;_
* _&quot;顯示lead_ 01的電子郵件和角色。&quot;_

## 追蹤歷程的進度 {#journey-progression}

詢問個人或潛在客戶如何在歷程中移動，以檢視節點層級的登入、退出、持續時間及其採取的路徑。 提供人員的電子郵件地址或銷售機會ID，以及歷程名稱。

* _「demo_ lead_24@company.com如何通過LeadNurtureJourney？」_
* _「john.doe@company.com在產品示範歷程中通過哪些節點？」_

## 瞭解分割路徑決策 {#split-path-analysis}

詢問為何個人或潛在客戶在分割節點採取或未採取特定路徑。 歷程可觀察性會使用在該時間點評估的屬性值來說明決策。 提供人員的電子郵件地址或銷售機會ID、歷程名稱和分割節點ID。

* _「為什麼demo_ lead_24@company.com會在分割節點c764a9移至「高度參與」路徑？」_
* _「為什麼john.doe@company.com沒有在LeadNurtureJourney的節點ab123f採用合格路徑？」_
* _&quot;比較為什麼lead_ 01和lead_02在分割節點x99f3b處採取不同的路徑。&quot;_

## 分析歷程節點中的人員 {#node-analysis}

在歷程節點或分割路徑中要求人員或銷售機會計數和詳細資訊。 依人員、角色、位置或參與層級篩選結果。 提供節點識別碼。

* _「將目前位於節點–459c7c的「高參與度」路徑中的所有人員提供給我。」_
* _「Demo Nurture歷程的資格節點中有多少潛在客戶？」_
* _&quot;在依角色篩選的「低意圖」分割路徑中顯示銷售機會：行銷經理。&quot;_

## 識別歷程中的模式 {#pattern-recognition}

要求歷程可觀察性識別歷程中的常見路徑、流失點和重複行為。 提供歷程名稱，並可選擇提供時間範圍、角色、產品或帳戶，以縮小結果範圍。

* _「SDR在產品示範歷程中最常採取的路徑為何？」_
* _「LeadNurtureJourney中的潛在客戶通常會在哪裡流失？」_
* _「第1季Nurture歷程中是否有任何不尋常的延遲或意外的路徑？」_

## 檢查時間與作業量度 {#operational-metrics}

詢問歷程的進入時間、等待期間、轉換延遲和進度延遲。 提供歷程名稱，並可選擇提供節點ID或人員識別碼。

* _&quot;john.doe@company.com何時進入示範後續追蹤歷程？&quot;_
* _「潛在客戶通常在LeadNurtureJourney中的資格節點等待多久？」_
* _「哪些潛在客戶在示範後續追蹤歷程中停頓了七天以上？」_

## 限制 {#limitations}

| 限制 | 詳細資料 |
|---|---|
| 編輯人員或潛在客戶屬性 | 不支援。 直接在[!DNL Marketo Engage]或[!DNL Marketo Optimizer]中更新人員和潛在客戶記錄。 |
| 建立、編輯、暫停或繼續歷程 | 不支援。 請改用[歷程畫布](../marketing/person-journeys.md)或[同事技能](./skills.md#journeys)中的歷程編輯技能。 |
| 變更分割邏輯或歷程設定 | 不支援。 直接在[歷程畫布](../marketing/split-merge-paths-nodes.md)中編輯分割路徑。 |
| 購買群組構成或帳戶層級統計 | 超出範圍。 歷程可觀察性僅報告個人和潛在客戶層級。 |
| 變更歷程排程或時間 | 不支援。 |
