---
title: 衍生角色
description: 在Marketo Optimizer中使用衍生角色來鎖定人員清單和歷程路徑。 瞭解預設角色對應和衍生角色篩選器。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# 衍生角色

角色分類將原始客戶資料轉換為語意購買者瞭解AI可用於產生內容，並推動每個管道和歷程的個人化決策。 此統一的設定檔可讓：

* _歷程分支_ — 依角色、參與深度和角色分割路徑路由銷售機會
* _歷程仲裁_ — 決定潛在客戶目前屬於哪個Nurture歷程，避免並行程式間的訊息衝突
* _內容個人化_ — 角色特定敘述的內容（「適用於高階主管」或「適用於從業人員」）
* _Sales Qualifier內容_ — 業務開發代表(BDR)會收到單熒幕摘要，其中顯示個人身分、其興趣及其在購買者歷程中的目前階段

## 預設角色 {#default-ersonas}

在Marketo Optimizer的Beta版本中，系統會根據職稱屬性定義下列預設角色：

| 人物誌 | 職稱 |
| ------- | ---------- |
| [!UICONTROL CXO / EVP] | CEO、CIO、CTO、CMO、CFO、策略執行副總裁 |
| [!UICONTROL SVP / VP] | 行銷副總裁、銷售副總裁、營運副總裁、產品副總裁、IT副總裁 |
| [!UICONTROL 資深經理/經理] | 資深行銷經理、IT經理、營運經理、銷售經理、人力資源經理 |
| [!UICONTROL 個人貢獻者] | 客戶主管、軟體工程師、行銷專家、客戶成功代表 |
| [!UICONTROL 分析人員] | 業務分析師、資料分析師、市場研究分析師、財務分析師、營運分析師 |
| [!UICONTROL 開發人員] | 前端開發人員、後端開發人員、完整棧疊開發人員、行動應用程式開發人員、DevOps工程師 |
| [!UICONTROL 專業員工] | 人力資源專家、法律顧問、法規遵循人員、專案經理、採購專家 |
| [!UICONTROL 顧問] | 管理顧問、IT顧問、業務流程顧問、行銷顧問 |
| [!UICONTROL 其他] | 產業專家、獨立顧問、自由顧問、主題專家 |

>[!NOTE]
>
>在即將發行的「一般可用性」版本中，您可以根據組織的需求編輯這些預設角色中的任何一個。 它也會支援自訂角色定義和對應。

## 依衍生角色篩選 {#derived-persona-filter}

[!DNL Marketo Optimizer]會根據定義的角色評估記錄屬性，以衍生每個人員記錄的角色。 定義人員清單的對象或在人員歷程中分段時，您可以使用推斷的結果（_衍生角色_）作為篩選器。

_[!UICONTROL 衍生角色]_&#x200B;篩選器會顯示在&#x200B;**[!UICONTROL 人員屬性]**&#x200B;類別下的篩選器面板中。

### 人員清單 {#people-lists}

管理[靜態人員清單](./people-lists.md#static-lists)中的成員，或定義[動態人員清單](./people-lists.md#dynamic-lists)的規則時，您可以依&#x200B;_衍生角色_&#x200B;篩選，以鎖定其屬性符合特定設定角色的所有人員。

![人員清單的衍生角色篩選](./assets/derived-persona-filter-people-list.png){width="750" zoomable="yes"}

**靜態清單 — 新增成員**

1. 開啟靜態清單，然後按一下右上方的&#x200B;**[!UICONTROL 新增人員]**。

1. 在篩選對話方塊中，展開&#x200B;**[!UICONTROL People屬性]**&#x200B;並將&#x200B;**[!UICONTROL 衍生角色]**&#x200B;拖曳到畫布上。

1. 在篩選條件中，選擇&#x200B;**[!UICONTROL 是]**，然後從清單中選取一或多個角色。

1. 按一下&#x200B;**[!UICONTROL 完成]**&#x200B;以套用篩選，並將相符的人員限定在清單中。

**動態清單 — 設定成員資格規則**

1. 開啟動態清單並選取&#x200B;**[!UICONTROL 規則]**&#x200B;標籤。

1. 按一下&#x200B;**[!UICONTROL 編輯規則]**。

1. 在篩選對話方塊中，展開&#x200B;**[!UICONTROL People屬性]**&#x200B;並將&#x200B;**[!UICONTROL 衍生角色]**&#x200B;拖曳到畫布上。

1. 在篩選條件中，選擇&#x200B;**[!UICONTROL 是]**，然後從清單中選取一或多個角色。

1. 按一下&#x200B;**[!UICONTROL 完成]**&#x200B;以儲存規則。

   當根據規則評估人員記錄時，會自動更新成員資格。

### 個人歷程 {#person-journeys}

當您在&#x200B;[_分割路徑_&#x200B;節點](../marketing/split-merge-paths-nodes.md)中設定人員歷程的區段時，您可以使用衍生角色作為人員設定檔篩選器，以控制哪些人員進入歷程路徑。

分割路徑條件的![衍生角色篩選](./assets/derived-persona-filter-split-path.png){width="750" zoomable="yes"}

1. 按一下歷程畫布中的&#x200B;**[!UICONTROL 分割路徑]**&#x200B;節點。

1. 在右側的節點屬性面板中，按一下路徑的&#x200B;**[!UICONTROL 套用條件]**&#x200B;或&#x200B;**[!UICONTROL 編輯條件]**。

1. 在篩選對話方塊中，展開&#x200B;**[!UICONTROL People屬性]**&#x200B;並將&#x200B;**[!UICONTROL 衍生角色]**&#x200B;拖曳到畫布上。

1. 在篩選條件中，選擇&#x200B;**[!UICONTROL 是]**，然後從清單中選取一或多個角色。

1. 按一下&#x200B;**[!UICONTROL 完成]**&#x200B;以儲存路徑的篩選器。

