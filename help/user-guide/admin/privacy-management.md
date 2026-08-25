---
title: 隱私權管理
description: 瞭解如何在Marketo Optimizer中遵守GDPR、CCPA和其他隱私權法規，並使用Adobe Privacy Service提交請求。
feature: Setup
role: Admin
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 75b481faf0d66210329f95c8afabdfa59e7bcb79
workflow-type: tm+mt
source-wordcount: 630
ht-degree: 5%

---


# 隱私權管理 {#privacy-management}

[Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/privacy/home){target="_blank"}提供RESTful API和使用者介面，協助您管理客戶資料請求。 透過[!DNL Adobe Privacy Service]，您可以提交存取和刪除Adobe CX Enterprise應用程式中的個人客戶資料請求，協助自動遵守法律和組織隱私權法規。

[!DNL Adobe Marketo Optimizer]提供這些隱私權工具，以便您符合全域資料保護需求。 使用[!DNL Privacy Service]提交並管理[!DNL Marketo Optimizer]收集並儲存之資料的存取和刪除要求。

您可以透過兩種方式提交個別請求，以從[!DNL Adobe Marketo Optimizer]存取和刪除消費者資料：

* [!DNL Privacy Service] UI
* [!DNL Privacy Service] API

## 支援的隱私權法規 {#regulations}

[!DNL Marketo Optimizer]隱私權工具可協助您透過[!DNL Privacy Service]遵守法規。 如果您保留相關區域中人員的資料，則每個規則都適用。

如需支援法規的最新清單，請參閱Privacy Service檔案中的&#x200B;[_隱私權法規概述_](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/privacy/regulations/overview){target="_blank"}。

## 請求型別 {#access-and-delete-requests}

[!DNL Marketo Optimizer]支援兩種隱私權要求型別：

* **資料存取** — 個人可以要求確認其個人資料正在處理中，並接收該資料的免費電子復本。
* **資料刪除** — 也稱為&#x200B;_被遺忘的權利_，個人可以要求您清除其個人資料並停止進一步處理。

## 檢視及管理隱私權請求 {#view-manage-requests}

>[!BEGINSHADEBOX]

![AEP許可權圖示](../assets/do-not-localize/icon_permissions-outline.svg)這些步驟需要您在Experience Platform中指派的使用者角色的[!DNL Privacy Service]產品設定檔和下列[許可權](../start/user-management.md#permissions)：

* **[!UICONTROL Privacy Service許可權]** - `Privacy Read Permission`和`Privacy Write Permission`
* **[!UICONTROL 資料控管]** - `View Privacy Console`

請參閱[!DNL Privacy Service]指南中的&#x200B;[_管理Privacy Service的許可權_](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/permissions){target="_blank"}以取得詳細資訊。

>[!ENDSHADEBOX]

若要檢視[!DNL Marketo Optimizer]中的隱私權要求工作，請展開&#x200B;**[!UICONTROL 隱私權]**&#x200B;並選取&#x200B;**[!UICONTROL 要求]**。

使用右上角的&#x200B;**[!UICONTROL 法規型別]**&#x200B;選項，變更您要管理工作或提交請求的法規的顯示頁面。

![隱私權要求工作，請選取法規型別](./assets/privacy-requests.png){width="800" zoomable="yes"}

### 提交請求 {#submit-a-request}

1. 按一下&#x200B;**[!UICONTROL 建立請求]**。

1. 針對&#x200B;**[!UICONTROL 工作型別]**，選取要求型別：

   * **[!UICONTROL 存取]**

     當您提交包含[!DNL Marketo Optimizer]的&#x200B;**_存取_**&#x200B;要求時，[!DNL Privacy Service]會傳回：

     * 與潛在客戶相關聯的[!DNL Marketo Engage]活動。
     * 與個人或帳戶相關聯的[!DNL Marketo Optimizer]活動。

   * **[!UICONTROL 刪除]**

     當您提交[!DNL Marketo Engage]和[!DNL Marketo Optimizer]的&#x200B;**刪除**&#x200B;要求時，下列記錄會被移除：

     * [!DNL Marketo Engage]中的關聯銷售機會。
     * 在[!DNL Marketo Optimizer]中建立的人員和帳戶記錄。
     * 參照個人資訊的同事交談記錄。

1. 針對&#x200B;**[!UICONTROL 產品]**，請選取&#x200B;**[!UICONTROL Marketo]**。

   ![為Marketo Engage和Marketo Optimizer建立GDPR存取隱私權請求](./assets/privacy-request-create-gdpr.png){width="450" zoomable="yes"}

   此選取範圍包含來自[!DNL Marketo Optimizer]和您的[!DNL Marketo Engage]執行個體的資料。

1. 捲動至對話方塊底部，並輸入您要存取或刪除其資料之人員的電子郵件地址。

1. 若要提交要求，請按一下[建立]。****

   [!DNL Privacy Service]傳回要求ID，可用來檢查要求的狀態。

### API要求 {#api-requests}

您也可以使用[!DNL Privacy Service] API提交隱私權請求。 如需一般API參考，請參閱[Privacy Service API檔案](https://developer.adobe.com/experience-platform-apis/references/privacy-service){target="_blank"}。

>[!PREREQUISITES]
>
>在提交請求之前收集下列資訊：
>
>* 您組織的IMS組織ID （以`@AdobeOrg`結尾的24個字元英數字串）。 如果您不知道您的IMS組織ID，請透過`gdprsupport@adobe.com`聯絡Adobe支援。
>* 您要存取或刪除其資料之人員的電子郵件地址。

在您的請求中使用下列欄位值：

| 欄位 | 值 |
|---|---|
| `companyContexts.namespace` | `imsOrgID` |
| `companyContexts.value` | 您的IMS組織ID |
| `users.action` | `access`或 `delete` |
| `users.userIDs.namespace` | `Email` |
| `include` | `marketo`以包含[!DNL Marketo Optimizer]和[!DNL Marketo Engage]資料 |
| `regulation` | 範例： `ccpa` <br/>某些規則值正在變更以包含狀態縮寫（例如，`ucpa_ut_usa`）。 較舊的值在轉換期間仍有效。 在針對這些值建置整合之前，請先參閱目前清單的[隱私權法規總覽](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/privacy/regulations/overview){target="_blank"}。 |

下列範例提交包含[!DNL Marketo Optimizer]資料的GDPR刪除請求。

```json
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "1231659F56A68A8B7F000101@AdobeOrg"
    }
  ],
  "users": [
    {
      "action": ["delete"],
      "userIDs": [
        {
          "namespace": "Email",
          "type": "standard",
          "value": "john.doe@adobe.com"
        }
      ]
    }
  ],
  "include": ["marketo"],
  "regulation": "gdpr"
}
```

[!DNL Privacy Service]傳回類似下列的回應。

```json
{
  "requestId": "16331241037112570RX-245",
  "totalRecords": 1,
  "jobs": [
    {
      "jobId": "997b01e3-9568-402c-904b-b4e60a437875",
      "customer": {
        "user": {
          "action": ["delete"],
          "userIDs": [
            {
              "namespace": "Email",
              "value": "john.doe@adobe.com",
              "type": "standard",
              "namespaceId": 6,
              "isDeletedClientSide": false
            }
          ]
        }
      }
    }
  ]
}
```
