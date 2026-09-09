---
title: 目的地
description: 瞭解所需的許可權、支援的目的地，以及如何在Marketo Optimizer中連線目的地，以將靜態人員清單啟用至廣告和社交平台。
TQID: 'https://experienceleague.adobe.com/u5sWVDR0JaiX-YvlQ23l7mqoI9G95xS-uiKcqANwsnc'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 643
ht-degree: 7%

---

# 目的地

目的地是預先建立的整合，可讓您從[!DNL Marketo Optimizer]將[靜態人物清單](./people-lists.md#static-lists)傳送至外部廣告或社交平台，例如LinkedIn促銷活動對象、Google客戶比對對象或Facebook自訂對象。 啟用靜態清單至目的地可保持成員資格同步：當在清單中新增或移除人員時，目標對象會相應新增或移除人員，延伸至對象摘要的任何促銷活動時，也會移除人員。

有兩種方式可將人員啟用至連線的目的地：

* **從靜態清單** — 直接從&#x200B;**_[!UICONTROL 人員清單]_**&#x200B;索引標籤啟動現有的靜態清單。 請參閱[啟用至目的地](./people-lists.md#static-list-activate)。
* **從個人歷程** — 將&#x200B;**_[!UICONTROL 啟用至目的地]_**&#x200B;動作新增至歷程路徑，讓到達該節點的任何人新增至清單並傳送至目的地。 請參閱&#x200B;[_新增動作節點_](../marketing/action-nodes.md#add-an-action-node)。

>[!BEGINSHADEBOX]

## 必要權限 {#required-permissions}

完整目的地功能需要啟用下列[!DNL Adobe Experience Platform]許可權。

| 類別 | 權限 | 必填 |
|--- |--- |--- |
| 沙箱 | 沙箱存取&#x200B;_（預設為啟用）_ | 是 |
| 儀表板 | 檢視標準儀表板 | 是 |
| 儀表板 | 管理標準儀表板 | 是 |
| 目的地 | 檢視目的地 | 是 |
| 目的地 | 管理目的地 | 是 |
| 目的地 | 啟用目的地 | 是 |
| 目的地 | 啟用區段而不進行對應 | 是 |
| 目的地 | 管理和啟用資料集目的地 | 是 |
| 目的地 | 目的地製作 | 是 |
| 資料治理 | 檢視資料使用原則 | 是 |
| 資料治理 | 管理資料使用原則 | 是 |
| 資料擷取 | 檢視來源 | 是 |
| 資料擷取 | 管理來源 | 是 |
| 輪廓管理 | 檢視設定檔設定 | 是 |
| 輪廓管理 | 管理設定檔設定 | 是 |

>[!ENDSHADEBOX]

## 支援的目的地 {#supported-destinations}

目的地必須存在於目的地目錄中，您才能啟用靜態清單。 在左側導覽列中，展開&#x200B;**[!UICONTROL 連線]**&#x200B;並選取&#x200B;**[!UICONTROL 目的地]**。 [!DNL Marketo Optimizer]目前支援下列目的地：

* **[!UICONTROL Google Customer Match]** (Advertising)
* **[!UICONTROL Facebook自訂對象]** （社交）
* **[!UICONTROL LinkedIn相符對象]** （社交）

![存取可用的聯結器型別](./assets/destinations-catalog.png){width="800" zoomable="yes"}

>[!NOTE]
>
>此目錄不是完整的[!DNL Adobe Experience Platform]目的地目錄。 如果您直接從[!DNL Experience Platform]存取目的地，您會看到較大型的目錄，但目前在[!DNL Marketo Optimizer]中只能啟用這些目的地。 未來版本計畫推出其他目的地。

## 設定目的地 {#set-up-destination}

每個支援的目的地卡片都會顯示&#x200B;**[!UICONTROL 設定新的目的地]**。 設定目的地是啟用的先決條件。

1. 在聯結器卡中，按一下&#x200B;**[!UICONTROL 設定新的目的地]**。

1. 選取&#x200B;**[!UICONTROL 現有帳戶]**&#x200B;或&#x200B;**[!UICONTROL 新帳戶]**，然後輸入帳戶詳細資料，例如帳戶名稱和描述。

   ![連線新的目的地帳戶](./assets/destinations-configure-new.png){width="500"}

1. 按一下&#x200B;**[!UICONTROL 連線到目的地]**。

   OAuth流程可讓您登入對應的帳戶：LinkedIn、Google或Facebook。

   >[!IMPORTANT]
   >
   >此時，**不要**&#x200B;輸入&#x200B;_[!UICONTROL 目的地詳細資料]_。 只需要連線。

1. 完成人員屬性與目的地所需欄位之間的任何所需欄位對應。

1. 檢閱資料控管和行銷動作設定，然後按一下[儲存]。**&#x200B;**

如需完整的設定步驟，請參閱[!DNL Experience Platform]檔案中的[建立新的目的地連線](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/destinations/ui/connect-destination){target="_blank"}。

設定後，目的地可供您在[!DNL Marketo Optimizer]中選取目的地的所有地方啟動。

## 啟用與同步 {#activation-sync}

啟用由靜態清單成員資格驅動，在清單和目的地對象之間具有雙向同步：

* 將人員新增至靜態清單會在24小時內將其啟用至目的地，新增至目的地對象，接著新增至對象摘要的任何促銷活動。
* 從靜態清單中移除人員，會導致其從目的地停用，並會從目的地對象和任何連線的行銷活動中移除。
* 同一份清單可一次啟用至多個目的地；所有目的地的成員資格都會同步。

>[!TIP]
>
>若要針對區段執行LinkedIn行銷活動，請針對您的LinkedIn相符對象目的地啟用這些人員的靜態清單。 清單中的所有人都會新增至LinkedIn中的相符對象，行銷活動可鎖定這些人，且對象會在清單變更時自動保持最新狀態。
