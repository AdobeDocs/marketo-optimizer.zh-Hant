---
title: 個人受眾歷程節點
description: 在Journey Optimizer B2B中設定「人員」對象節點，指定哪些設定檔會使用動態人員清單或事件型對象來進入歷程。
TQID: 'https://experienceleague.adobe.com/WqM-yLPadt6lBFtqJOGUxDtk0fm6n6S29wQTRSWB8fY'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 215
ht-degree: 0%

---

# 個人受眾節點

_個人對象_&#x200B;節點會指定哪些人員設定檔進入歷程。 當您[建立個人歷程](./person-journeys.md)時，歷程一律以定義其輸入的個人對象節點開始。 「人員」對象節點可以有下列兩種對象輸入型別之一：動態人員清單或事件觸發器。

如果您需要的人員歷程動態人員清單不存在，請[建立人員清單](../audiences/people-lists.md#create-a-people-list)，然後設定人員對象節點。

設定歷程對象(_T):_

1. 按一下&#x200B;**[!UICONTROL 個人對象]**&#x200B;節點。

   此動作會在右側顯示節點屬性。

   ![個人受眾歷程節點](./assets/person-audience-node-properties.png){width="600" zoomable="yes"}

1. 對個人對象使用下列其中一個對象設定選項：

   * **[!UICONTROL 動態清單]** — 使用以規則為基礎的動態人員清單。 清單規則會在歷程執行階段進行評估，以符合歷程成員的資格。 之後不符合動態清單資格的人不會從歷程中移除。 請參閱&#x200B;_[動態清單](../audiences/people-lists.md#dynamic-lists)_。

   * **[!UICONTROL 事件對象]** — 使用事件對象，根據合格事件定義歷程對象。 使用個人資料篩選定義對象成員，並使用事件條件觸發歷程專案。 請參閱&#x200B;_[事件型對象](../audiences/event-based-audiences.md)_。