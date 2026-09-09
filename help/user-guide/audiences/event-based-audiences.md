---
title: 事件型對象
description: 在Marketo Optimizer中使用事件型受眾，根據Marketo Engage活動近乎即時地觸發人員歷程專案。
TQID: 'https://experienceleague.adobe.com/pnXkfVhy4qJ4nsQJLjAXJR6cZA-1edr9LFpyvBo27Xo'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 320
ht-degree: 0%

---

# 事件型對象

在[!DNL Adobe Marketo Optimizer]中，_事件型對象_&#x200B;可讓您在[!DNL Marketo Engage]活動發生時，近乎即時地將對象成員新增到即時[個人歷程](../marketing/person-journeys.md)。 您可以在歷程畫布的「對象」節點設定事件型對象：

* 選取一或多個[!DNL Marketo Engage]活動（標準或自訂）作為符合資格的事件。
* 選擇性地新增人員設定檔篩選器（例如產業、地區或生命週期階段），以縮小可輸入的人員範圍。
* 選擇性地定義活動屬性限制（例如特定表單、URL或程式），以縮小每個活動符合條件的發生次數。

當合格活動登入[!DNL Marketo Engage]潛在客戶並復寫到[!DNL Adobe Marketo Optimizer]時，系統會根據您設定的篩選器和限制評估對應的人員記錄。 如果符合條件，人員會立即透過受眾節點進入歷程。

若要定義人員歷程的事件型對象(_T):_

1. 選取&#x200B;[_個人對象_&#x200B;節點](../marketing/person-audience-node.md)。

1. 在右側的節點屬性中，選擇&#x200B;**[!UICONTROL 事件對象]**&#x200B;作為專案型別。

   ![個人對象歷程節點設定為事件型對象](./assets/event-based-audience-node.png){width="400"}

1. 按一下&#x200B;**[!UICONTROL 新增事件條件]**。

1. 在&#x200B;_[!UICONTROL 編輯事件條件]_&#x200B;對話方塊中，新增一或多個[!DNL Marketo Engage]活動作為合格事件，例如：

   * _出席網路研討會_
   * _電子郵件已傳遞_
   * _點按電子郵件中的連結_

   >[!NOTE]
   >
   >您也可以選取在相關[!DNL Marketo Engage]執行個體中定義的自訂活動。

   設定每個活動的相符運運算元和值。

   事件型對象的![活動觸發程式](./assets/event-based-audience-triggers.png){width="700" zoomable="yes"}

   當這些已設定的活動中有任何一項記錄給該潛在客戶時，即表示該人員符合歷程資格。

1. （選用）若要針對對象資格使用事件和篩選器組合，請新增人員層級篩選器。

   * 選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;索引標籤。
   * 拖曳每個篩選器並設定符合條件。

   事件型對象的![人員篩選器](./assets/event-based-audience-filters.png){width="700" zoomable="yes"}

   如果您新增篩選器，則人員必須至少滿足一個已設定的活動條件和已設定的篩選器。

1. 按一下&#x200B;**[!UICONTROL 儲存]**。