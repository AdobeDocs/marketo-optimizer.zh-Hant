---
title: 新增電子郵件至歷程
description: 將電子郵件動作節點新增至個人歷程，並建立新的電子郵件，以便在Marketo Optimizer中進行目標式通訊。
feature: Email Authoring, Person Journeys
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 7%

---

# 新增電子郵件至歷程

[!DNL Adobe Marketo Optimizer]為B2B行銷人員帶來現代的企業級電子郵件撰寫和傳遞體驗。

>[!NOTE]
>
>如果您是第一次傳送電子郵件，請確定已設定[電子郵件傳遞能力](../start/email-deliverability.md)和所需的[電子郵件通道](../admin/email-channel-configuration.md)。

<!-- 
* **Email channel configurations** - Manage the sender identity, reply behavior, marketing vs. transactional message types, and tracking.
* **Email deliverability controls** - Set up your email deliverability channel, including subdomain delegation (Fully Delegated and CNAME methods), DMARC, SPF/DKIM auto-configuration, and shared IP pool support.
* **Send Email action** - From a journey, add a _Send email_ action node, including personalization using profile attributes (Handlebars syntax).
* **Visual drag-and-drop email design tools** -  Design your email content with structures, content components, themes, dark-mode support, and reusable visual fragments.
* **Marketo Design Studio assets** — Choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas.
* **Reusable templates and fragments** — Save common headers, footers, CTAs, and full email layouts and reuse them across journeys.
* **Role-Based Access Control (RBAC)** — Apply granular permissions for creating, editing, approving, and sending email. 
-->

## 目前限制 {#limitations}

* **測試設定檔、模擬內容和傳送校樣**&#x200B;在此版本中無法使用。 Litmus呈現和基於SpamAssassin的垃圾郵件報告都在GA藍圖上。
* **此版本中無法使用帳戶層級的個人化和自訂物件資料**。 使用設定檔屬性。
* 正式發行時，現有Marketo Engage範本的&#x200B;**Velocity-to-Handlebars自動移轉**。
* 即將發行的版本中會提供&#x200B;**電子郵件**&#x200B;上的註解與共同作業（內嵌註解、@mentions、請求檢閱工作流程）。
* **AEM Assets、AEM內容片段和Adobe Express**&#x200B;整合在&#x200B;_快速後續追蹤_&#x200B;藍圖上。

## 重要概念 {#key-concepts}

在為人員歷程建立電子郵件並編寫電子郵件內容之前，請先檢閱以下概念：

| 概念 | 在[!DNL Adobe Marketo Optimizer] |
| ------- | ---------------------- |
| **_電子郵件設計空間_** | 用於撰寫電子郵件內容的視覺畫布和設計工具。 其中包含拖放式版面配置元件、範本、片段、主題和個人化編輯器。 |
| **_範本_** | 可重複使用的電子郵件配置，可用於建立新電子郵件。 範本可以是Adobe提供的內建範例範本，也可以是您的團隊建立的自訂範本。 |
| **_視覺片段_** | 可重複使用的內容區塊（例如頁首、頁尾、CTA、法律免責宣告），可插入多封電子郵件中。 更新片段會將變更傳播到使用它的每封電子郵件。 |
| **_佈景主題_** | 可在電子郵件中套用的可重複使用樣式預設集（顏色、印刷樣式、間距、按鈕樣式）。 |
| **_Personalization Token_** | Handlebars運算式（例如`{{profile.firstName}}`）在傳送時使用每個收件者的設定檔資料解析。 |
| **_傳送電子郵件動作_** | 歷程動作節點，使用通道設定和電子郵件內容來傳遞電子郵件。 |

## 從歷程新增電子郵件

若要從歷程傳送電子郵件，請[新增&#x200B;_採取動作_&#x200B;節點](action-nodes.md#add-an-action-node)，並將其設定為傳送電子郵件。

1. 在歷程畫布中，按一下&#x200B;**+**&#x200B;圖示並選取&#x200B;**[!UICONTROL 執行動作]**。

1. 在右側的節點屬性中，將動作設定為&#x200B;**[!UICONTROL 傳送電子郵件]**。

   ![採取動作 — 傳送電子郵件](./assets/person-action-node-send-email.png){width="500"}

1. 選擇電子郵件來源：

   * **建立/編輯電子郵件** — 選擇此選項可定義電子郵件內容，包括電子郵件設計空間中的主旨列、寄件者資訊和電子郵件內文。

   * **[!UICONTROL 使用AI個人化電子郵件]** - （_不適用於Beta_）選擇此選項可在電子郵件設計空間中調整AI_generated電子郵件。 這些電子郵件已最佳化，因此AI輔助收件匣使用者端可在您的選件和行動號召中建立其摘要和答案。

1. 按一下&#x200B;**[!UICONTROL 建立電子郵件]**。

1. 在&#x200B;_[!UICONTROL 建立電子郵件]_&#x200B;對話方塊中，輸入唯一的&#x200B;**[!UICONTROL 名稱]** （必要）和&#x200B;**[!UICONTROL 描述]** （選用）。

   ![建立電子郵件對話方塊](./assets/email-channel-create-email-dialog.png){width="400"}

1. 按一下&#x200B;**[!UICONTROL 建立]**。

針對選用的[傳送時間最佳化](email-send-time-optimization.md)，請在建立電子郵件之後設定歷程動作節點。

## 定義電子郵件屬性和動作 {#define-email-properties}

當您建立&#x200B;_[!UICONTROL 傳送電子郵件]_&#x200B;節點的電子郵件時，會開啟電子郵件頁面。 您也可以在建立電子郵件之後，按一下右側節點屬性中的&#x200B;**[!UICONTROL 編輯電子郵件]**&#x200B;來存取此頁面。

1. （選擇性）在&#x200B;**[!UICONTROL 屬性]**&#x200B;索引標籤中，輸入您要擷取的電子郵件任何描述性資訊。

1. 選取&#x200B;**[!UICONTROL 動作]**&#x200B;標籤，並完成電子郵件的功能設定：

   * **[!UICONTROL 電子郵件]** — 選取或建立要使用的&#x200B;**[!UICONTROL 電子郵件通道設定]**。

     這是一組可重複使用的電子郵件傳送設定，可定義寄件者身分、回覆位址、子網域、IP集區、電子郵件型別（行銷或異動）以及追蹤。 按一下&#x200B;_檢視_&#x200B;圖示以檢閱所選組態的設定。

     管理員在[電子郵件通道設定](../admin/email-channel-configuration.md)中建立設定。

   * **[!UICONTROL 商業規則]** - （選擇性）選取規則集，將上限或無訊息時數規則套用至您的電子郵件動作。

     如需有關商業規則以及如何定義及啟用通道通訊規則集的詳細資訊，請參閱&#x200B;[_商業規則_](../admin/business-rules.md)。

   * **[!UICONTROL 動作追蹤]** — 選取您要追蹤電子郵件之動作的核取方塊。

   ![電子郵件頻道 — 動作索引標籤](./assets/email-channel-actions-tab.png){width="600" zoomable="yes"}

1. 按一下「**[!UICONTROL 編輯內容]**」，或選取「**[!UICONTROL 內容]**」標籤。

1. 輸入要顯示在電子郵件主旨欄位中的&#x200B;**[!UICONTROL 主旨列]**&#x200B;文字。

   按一下「_個人化_」圖示（「![個人化圖示](../assets/do-not-localize/icon-personalize.svg)」）以在欄位中使用個人化權杖。

1. （選用）選取&#x200B;**[!UICONTROL 最佳化HTML大小]**&#x200B;核取方塊，在發佈程式期間縮小電子郵件HTML的大小。

   這樣可以避免在 Gmail 一類用戶端中發生電子郵件內容截斷的狀況，因為用戶端會截斷超過 100 KB 大小的郵件。 如需詳細資訊，請參閱&#x200B;[_最佳化電子郵件HTML大小_](#optimize-html-size)。

1. 按一下&#x200B;**[!UICONTROL 編輯電子郵件內文]**&#x200B;以存取視覺化設計工具並開始[建立您的內容](../content/email-authoring.md)。

   或者，您可以按一下&#x200B;**[!UICONTROL 代碼編輯器]**，以純HTML編碼您自己的內容。 如果您有現有的HTML可重複使用您的電子郵件設計，您可以將其複製並貼到編輯器中。

### 檢查警報 {#alerts}

[!DNL Adobe Marketo Optimizer]在電子郵件頁面的右上角出現問題。 在啟用歷程之前解決所有錯誤。 警告僅為建議。

**錯誤** （防止歷程啟用）：

* 寄件者名稱是空的
* 缺少主旨列
* 電子郵件內容是空的

**警告** （建議）：

* 電子郵件內文中沒有選擇退出連結
* HTML的文字版本為空白
* 偵測到空連結
* 電子郵件超過100 K

## 最佳化電子郵件 HTML 大小 {#optimize-html-size}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_email_minification"
>title="縮減 HTML 大小"
>abstract="啟用此選項可移除不必要的空白字元、縮排及非必要的註解，以便在發佈時壓縮電子郵件 HTML。 這樣可以避免在 Gmail 一類用戶端中發生電子郵件內容截斷的狀況，因為用戶端會截斷超過 100 KB 大小的郵件。"

[!DNL Marketo Optimizer]可讓您移除不必要的空白字元、縮排及不必要的註解，在發佈程式期間壓縮電子郵件HTML版本。 保持HTML小型化可協助您：

* 避免&#x200B;**電子郵件剪輯** — 某些使用者端（例如Gmail）會截斷大於~100 KB的郵件，使收件者無法檢視完整內容。
* 改善收件者收件匣中的&#x200B;**電子郵件載入時間**。
* 改善&#x200B;**傳遞能力**&#x200B;並減少頻寬使用量。

此最佳化不會自動套用 — 您必須在&#x200B;_[!UICONTROL 內容]_&#x200B;索引標籤中啟用它。

<!-- ![](assets/email-optimize-html-size.png) -->

>[!IMPORTANT]
>
> HTML大小縮減僅適用於發佈時。

最佳化是電子郵件使用者端安全：

* 它會保留MSO/Outlook條件式註解。
* 這不會改變您的實際內容、影像或視訊。

>[!NOTE]
>
>電子郵件大小的縮減取決於電子郵件原始HTML結構。 如果內容已壓縮或電子郵件承載非常大，縮減量可能極小，並且可能在所有情況下都無法完全防止剪輯。

<!-- 
Proof and simulate workflows are not available in this release. See [Current limitations](#limitations).

### Test HTML size optimization {#optimize-html-proof}

If you have enabled the [HTML size optimization](#optimize-html-size) option, you can evaluate its impact before publishing when sending proofs. Follow the following steps.

1. In the email design space, click the _Issues_ icon on the top right. If the rendered email size exceeds 100 KB, a message is displayed to warn you that this may cause truncation in some email clients.

1. Click **[!UICONTROL Simulate content]**.

1. To test the optimized version, click the **[!UICONTROL Send proof]** button and select the **[!UICONTROL Optimize HTML size]** option. This will send a proof with the reduced HTML size to your test recipients.

    >[!NOTE]
    >
    >This setting is independent from the email editor — the proof reflects what you select in the proof, regardless of whether the option is enabled or disabled in the email itself.

1. Select the test recipients and click **[!UICONTROL Send proof]**.

1. Back in the **[!UICONTROL Simulate]** screen, click the **[!UICONTROL View Proof]** button.

1. Click the _Information_ icon next to the status of the proof.

   The optimization details are displayed in a pop-up window, including the original HTML size, the optimized HTML size, and the size reduction percentage.
    
    Use this information to validate the optimized output and confirm the email stays within the recommended 100 KB threshold before publishing.

-->
