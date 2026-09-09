---
title: 計畫型別
description: 建立並管理程式型別，這些程式型別可為Marketo Optimizer中的程式定義屬性和成員狀態流程。
TQID: 'https://experienceleague.adobe.com/Eepcnc51p-P-yoyylXBr47SF0xR-3pvZab2aHf9jdew'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 389
ht-degree: 0%

---

# 計畫型別

方案型別定義[方案](../marketing/programs.md)及其成員的重要方面，並區分不同型別的行銷方案。 每個程式型別會定義以下屬性，這些屬性會繼承給使用程式型別的程式：

* **屬性** — 屬性說明程式型別的重要方面，例如事件日期和位置屬性。

* **方案狀態流程** — 每個狀態都會指派給方案型別中的步驟（例如1、2或3）。 計畫的成員只能從具有相同步驟編號的狀態（例如，從&#x200B;_No-Showed_&#x200B;到&#x200B;_Attended_）移動，或是從具有較高步驟編號的狀態（例如，從&#x200B;_Required_&#x200B;到&#x200B;_Registered_）。

  計畫狀態是互斥的且線性，因此每個計畫個人只能有一個狀態值。 在設計狀態時，請思考您想讓哪些狀態之間移動。 例如，如果某位使用者未出席網路研討會，但可選擇稍後隨選參加，則您會希望他們擁有相同的狀態編號，或將隨選設定為更高的狀態編號，以便方案成員可以進入該狀態。

>[!NOTE]
>
>如果程式型別至少由一個程式使用，則無法編輯它。

定義自訂程式型別(_T):_

1. 在[!DNL Adobe Marketo Optimizer]左側導覽中，展開&#x200B;**[!UICONTROL 管理]**&#x200B;並選取&#x200B;**[!UICONTROL 程式型別]**。

   ![存取程式型別清單](./assets/program-types-list.png){width="800" zoomable="yes"}

1. 按一下右上角的&#x200B;**[!UICONTROL 建立型別]**。

1. 輸入唯一的&#x200B;**[!UICONTROL Name]** （必要）和&#x200B;**[!UICONTROL Description]** （選用）。

   ![建立方案型別](./assets/program-type-create.png){width="600" zoomable="yes"}

   >[!TIP]
   >
   >加入說明是最佳做法，可讓您的程式型別程式庫更易於管理。

1. 按一下&#x200B;**[!UICONTROL 建立型別]**。

1. 新增程式型別的&#x200B;**[!UICONTROL 屬性]**。

   針對您要新增的每個屬性：

   * 按一下&#x200B;**[!UICONTROL 新增屬性]**。
   * 選擇&#x200B;**[!UICONTROL API名稱]**&#x200B;並輸入&#x200B;**[!UICONTROL 顯示名稱]**。
   * 按一下&#x200B;**[!UICONTROL 儲存]**。

   ![程式型別屬性](./assets/program-type-attributes.png){width="600" zoomable="yes"}

1. 定義&#x200B;**[!UICONTROL 程式狀態]**&#x200B;的步驟。

   定義要包含在流程中的每個步驟：

   * 按一下&#x200B;**[!UICONTROL 新增步驟]**。
   * 輸入狀態名稱。
   * （選擇性）按一下「新增狀態」**&#x200B;**，然後輸入要納入步驟的其他狀態名稱。

   針對您要追蹤為成功方案執行的任何步驟，選取&#x200B;**[!UICONTROL 標籤為成功]**&#x200B;核取方塊。

   ![程式型別狀態](./assets/program-type-statuses.png){width="600" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 完成]**&#x200B;以儲存您的變更並返回程式型別清單。