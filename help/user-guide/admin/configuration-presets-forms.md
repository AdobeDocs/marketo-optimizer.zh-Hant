---
title: Forms設定
description: 預留位置
TQID: 'https://experienceleague.adobe.com/7X5-67hfrjRjWbGjq9duLu7mVjgfCs7tpAQLV8u6YKE'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
  - id: d4203578-d294-5145-b397-f26f4488a904
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 541
ht-degree: 16%

---

# Forms設定

產品管理員必須先建立一或多個專用預設集，行銷人員才能建立並發佈表單以用於其登陸頁面。 每個預設集都會定義用來傳送表單提交資料的連線端點，以及用來儲存所擷取資料的資料集。

當資料登陸串流端點時，會與資料集資訊連結。 然後會使用產生的來源/目標連線和來源流程，將資料推送至資料集。

>[!BEGINSHADEBOX]

## 先決條件

若要使用網路表單，您必須在Adobe Experience Platform中定義一或多個&#x200B;_&#x200B;**HTTP API串流連線**&#x200B;_。 請確定您要使用的每個連線都符合下列需求：

* 資料型別必須設定為XDM （非原始資料）
* 必須停用驗證（未驗證的連線）

如需建立串流來源連線的詳細資訊，請參閱&#x200B;[_Experience Platform檔案_](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/ui-tutorials/create/streaming/http)。

<!-- 
permissions coming in GA

Forms channel configuration in Journey Optimizer B2B Edition requires the following [permissions](../start/user-management.md#b2b-product-permissions):

* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL View Forms Presets]_ - Required to view forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Manage Forms Presets]_ - Required to create, update, and delete forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Publish Forms Presets]_ - Required to publish forms preset configurations.
-->

>[!ENDSHADEBOX]

## 表單預設集設定指南

建立預設集時：

* 您可以使用不同的資料集和串流連線組合，設定多個預設集。

* 您可以跨多個預設集重複使用相同的資料集或串流連線。

* 每個串流連線都會自動產生資源，例如：

  * _Source連線_ — 資料來源。
  * _目標連線_ — 資料儲存或使用的位置。
  * _Source流程_ — 將資料從來源連線移入Experience Platform的管道。 它會處理對應、轉換和驗證。

## 建立表單預設集 {#create-preset}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_connection"
>title="選取要使用的端點"
>abstract="定義在提交表單時傳送資料的串流端點。"
>additional-url="https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/ui-tutorials/create/streaming/http" text="建立 HTTP API 串流連線"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_dataset"
>title="選取資料集"
>abstract="定義將會儲存並反映表單回應的資料集。 輸入文字以搜尋特定資料集，或從清單中進行選取。"

1. 在左側導覽列中，移至&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 管道]**。

1. 在導覽面板中的&#x200B;_[!UICONTROL 表單設定]_&#x200B;下，選取&#x200B;**[!UICONTROL 表單預設集]**。

   <!-- ![Access the form configurations](./assets/config-channels-forms.png){width="800" zoomable="yes"} -->

1. 按一下&#x200B;**[!UICONTROL 建立表單預設集]**。

1. 輸入組態的唯一的&#x200B;**[!UICONTROL 名稱]** （必要）和&#x200B;**[!UICONTROL 描述]** （選用）。

   >[!NOTE]
   >
   >名稱必須以字母(A-Z)開頭，並且只能包含英數字元。 您也可以使用底線`_`、點`.`和連字型大小`-`字元。

1. 選取&#x200B;**[!UICONTROL 串流連線]**。

   此連線是串流端點，用於在Web檢視器提交表單時傳送資料。 如果需要的串流連線未出現在清單中，請驗證是否符合要求。

1. 按一下「_選取資料集_」（![選取資料集圖示](../assets/do-not-localize/icon-select-data.svg)）圖示，將資料集與表單連結。

   資料集是儲存及反映表單回應的位置。 您可以輸入文字字串來搜尋特定資料集，或從清單中選取它。

   <!-- ![Select datasets dialog](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >目前只能選取已啟用設定檔和未啟用設定檔的[Adobe Experience Platform資料集](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/catalog/datasets/overview)。 您可以一次選取一個資料集。 系統資料集無法用來儲存表單資料。

   選取資料集的核取方塊，然後按一下&#x200B;**[!UICONTROL 選取]**。

1. 按一下&#x200B;**[!UICONTROL 另存為草稿]**。

## 發佈表單預設集

1. 按一下表單預設集名稱以開啟設定頁面。

   您可以視需要對草稿進行任何調整。

1. 按一下&#x200B;**[!UICONTROL 發佈]**。

   當表單預設集以&#x200B;_已發佈_&#x200B;狀態列出時，可用於建立表單。
