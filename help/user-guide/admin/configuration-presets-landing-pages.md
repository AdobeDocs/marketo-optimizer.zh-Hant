---
title: 登陸頁面設定
description: 預留位置
TQID: 'https://experienceleague.adobe.com/wowFSf32UsmDemN6Iy5-IgGOPmuocHHLRb4vvTUDt0U'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: a659ad61-de21-559d-a901-02e2fb329ff5id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 971
ht-degree: 21%

---


# 登陸頁面設定

管理員應確保為製作和發佈這些頁面的行銷人員設定登陸頁面。 有兩種設定型別需要用來打造能有效反映品牌並追蹤參與度的登入頁面：

* **_子網域_** — 設定託管登入頁面的位置。 管理登陸頁面子網域以委派、設定或取消委派網域設定。
* **_預設集_** — 定義可重複使用的設定（包括子網域和其他管道設定），讓行銷人員可以一致地建立和管理登入頁面。

## 子網域 {#lp-subdomains}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp_header"
>title="委派登陸頁面子網域"
>abstract="設定用於登陸頁面的子網域。 您可以使用已委派給 Adobe 的子網域，或設定另一個子網域。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_subdomain_lp"
>title="委派登陸頁面子網域"
>abstract="您必須先設定登陸頁面子網域，才能建立登陸頁面預設集。 您可以使用已委派給 Adobe 的子網域，或設定新的子網域。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain"
>title="建立登陸頁面預設集"
>abstract="若要建立登陸頁面預設集，請確定您至少已設定一個登陸頁面子網域，以便從子網域名稱清單中進行選擇。"

若要檢閱設定的登入頁面子網域，請移至&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 管道]**。 在導覽窗格中的&#x200B;_[!UICONTROL 登陸頁面]_&#x200B;下方，選取&#x200B;**[!UICONTROL 登陸頁面子網域]**。

<!-- ![Channel configurations - landing page subdomains](./assets/config-channels-landing-pages-subdomains.png){width="800" zoomable="yes"} -->

**狀態**&#x200B;欄提供子網域建立和委派程式的資訊：

* _[!UICONTROL 草稿]_：子網域委派已儲存為草稿。 按一下子網域名稱以繼續建立程式。
* _[!UICONTROL 正在處理]_：子網域正在透過數個組態檢查進行中，必須先進行這些檢查才能使用。
* _[!UICONTROL 成功]_：順利通過檢查的子網域，可用於傳遞訊息。
* _[!UICONTROL 失敗]_：提交子網域委派後，一或多個檢查失敗。

>[!NOTE]
>
>在您[建立登陸頁面預設集](#lp-presets)之前，您必須設定要用於登陸頁面的子網域。 您可以使用已委派給Adobe的子網域，也可以設定另一個子網域。

登陸頁面子網域設定是&#x200B;**所有環境通用**。 因此：

* 若要存取及編輯登陸頁面子網域，您必須對生產沙箱具有&#x200B;**[!UICONTROL 管理登陸頁面子網域]**&#x200B;許可權。

* 對登陸頁面子網域所做的任何修改也會影響生產沙箱。

<!-- 
### Use an existing subdomain {#lp-existing-subdomain}

To use a subdomain that is already delegated to Adobe:

1. Click **[!UICONTROL Set up landing page subdomain]**.

    ![](assets/lp_set-up-subdomain.png)

1. For _[!UICONTROL Configuration type]_, choose **[!UICONTROL Use delegated domain]**.

    ![](assets/lp_use-delegated-subdomain.png)

1. Enter the prefix that you want to display in the landing page URL.

    Only alpha-numeric characters and hyphens are allowed.

    >[!CAUTION]
    >
    >Do not use `cdn` or `data` prefixes as these are reserved for internal use. You should also avoid other restricted or reserved prefixes, such as `dmarc` or `spf`.

1. Select a delegated subdomain from the list.

    You cannot select a subdomain that is already used as landing page subdomain.
    
    ![](assets/lp_prefix-and-subdomain.png)

    You cannot use multiple delegated subdomains of the same parent domain. For example, if 'marketing1.yourcompany.com' is already delegated to Adobe for your landing pages, you cannot use 'marketing2.yourcompany.com'. However, when multi-level subdomains are supported for landing pages, you may proceed using a subdomain of 'marketing1.yourcompany.com' (such as 'email.marketing1.yourcompany.com'), or a different parent domain.

    >[!CAUTION]
    >
    >If you select a domain that was delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), you must create the DNS record on your hosting platform. To generate the DNS record, the process is the same as when you configure a new landing page subdomain.

1. Click **[!UICONTROL Submit]**.

   The subdomain is displayed in the list with the _[!UICONTROL Processing]_ status. For more on subdomains' statuses, see TBD.

    ![](assets/lp_subdomain-processing.png)

   >[!IMPORTANT]
   >
   >The subdomain is not ready for use until Adobe performs the required checks, which can take **_up to 4 hours_**.

   When the checks are successful, the subdomain is listed with the _[!UICONTROL Success]_ status and it is ready to use for creating landing page presets.
-->

### 設定新的子網域 {#lp-new-subdomain}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_lp_subdomain_dns"
>title="產生相符的 DNS 記錄"
>abstract="若要設定新的登陸頁面子網域，您需要複製 Journey Optimizer B2B 介面中顯示的 Adobe 名稱伺服器資訊，並將其貼到您的網域託管解決方案中，以產生相符的 DNS 記錄。 檢查成功後，即可使用該子網域來建立登陸頁面預設集。"

1. 按一下&#x200B;**[!UICONTROL 設定登陸頁面子網域]**。

1. 針對&#x200B;_[!UICONTROL 設定型別]_，請選擇&#x200B;**[!UICONTROL 新增您自己的網域]**。

1. 指定要委派的子網域。

   >[!IMPORTANT]
   >
   >* 您無法使用現有的登陸頁面子網域。
   >
   >* 子網域中不允許使用大寫字母。

   <!-- ![Landing page subdomain set up](./assets/config-channels-landing-pages-subdomain-setup.png){width="500" zoomable="yes"} -->

   不允許將無效的子網域委派給Adobe。 請務必輸入貴組織所擁有的有效子網域，例如marketing.yourcompany.com。

   對於登入頁面，支援多層級子網域。 例如，您可以使用`email.marketing.yourcompany.com`。

1. 複製顯示的記錄或下載CSV檔案，然後導覽至您的網域託管解決方案，以產生相符的DNS記錄。

   將會顯示要放置在DNS伺服器中的記錄。

1. 請確定DNS記錄已產生到您的網域託管解決方案中。

   如果所有專案皆已正確設定，請選取確認核取方塊，然後按一下&#x200B;**[!UICONTROL 提交]**。

   <!-- ![Landing page subdomain set up with DNS records](./assets/config-channels-landing-pages-subdomain-setup-dns.png){width="500" zoomable="yes"} -->

   當您設定新的登陸頁面子網域時，它一律會指向CNAME記錄。

   提交子網域委派時，子網域會顯示在狀態為&#x200B;_[!UICONTROL 處理中]_&#x200B;的清單中。

   >[!IMPORTANT]
   >
   >在Adobe執行必要的檢查之前，子網域尚未就緒，最多可能需要&#x200B;**_4小時_**。

   檢查成功後，子網域會以&#x200B;_[!UICONTROL Success]_&#x200B;狀態列出，而且可以用來建立登陸頁面預設集。

   如果您未在託管解決方案上建立驗證記錄，則子網域會標示為&#x200B;_[!UICONTROL 失敗]_。

### 取消委派子網域 {#undelegate-subdomain}

1. 在[!DNL Journey Optimizer]中，取消發佈與子網域關聯的所有登入頁面。

1. 如果登陸頁面子網域指向CNAME記錄，請從您的託管解決方案中刪除CNAME記錄（不刪除原始電子郵件子網域，如果有的話）。

   <!--
    >[!NOTE]
    >
    >A landing page subdomain can point to a CNAME record because it was either an [existing subdomain](#lp-use-existing-subdomain) delegated to Adobe using the [CNAME method](../configuration/delegate-subdomain.md#cname-subdomain-setup), or a [new landing page subdomain](#lp-configure-new-subdomain) that you configured. 
    -->

1. 請聯絡您的Adobe代表，提供您要取消委派的子網域。

Adobe處理您的請求後，子網域詳細目錄頁面不再顯示未委派網域。

<!-- 
old marketo way for Prime?

A landing page subdomain should help to identify the content type, product name, or campaign, and reinforce the page authenticity. Before you configure the subdomains, define one or more CNAMEs to use for your landing pages. For example:

* **product**.[CompanyDomain].com
* **go**.[CompanyDomain].com
* **signup**.[CompanyDomain].com

In these examples, the first part (in bold) is the `LandingPageCNAME`.

Add a new subdomain for each unique brand URL that you want to host on Adobe Journey Optimizer B2B Edition. You can add a maximum number of 50 subdomains.

>[!IMPORTANT]
>
>Delegating an invalid subdomain to Adobe is not allowed. Make sure you enter a valid subdomain that your organization owns, such as _marketing.yourcompany.com_.

To review your subdomains and add new ones, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. Under _[!UICONTROL Landing Pages]_ in the navigation panel, select **[!UICONTROL Subdomains]**.

![Landing page subdomains](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

_To add a landing page subdomain:_

1. Click **[!UICONTROL Add subdomain]** at the top right.

1. In the _[!UICONTROL Subdomain details]_, enter the subdomain information:

   * **[!UICONTROL Subdomain]** - The subdomain URL to use, such as `marketing.yourcompany.com`
   * **[!UICONTROL Default page]** - The URL for the default subdomain page, such as `marketing.yourcompany.com/products`
   * **[!UICONTROL Fallback page]** - The URL for the fallback page to be used if a landing page on the subdomain is not active, such as `marketing.yourcompany.com/expired`

   ![Add landing page subdomain](./assets/config-landing-pages-add-subdomain.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

-->

## 預設集 {#lp-presets}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_admin_config_lp_subdomain_header"
>title="建立登陸頁面預設集"
>abstract="為了建立登陸頁面並透過 Journey Optimizer B2B Edition 加以利用，您必須建立一個包含要使用的子網域的登陸頁面預設集。"

行銷人員建立登陸頁面時，必須選取登陸頁面預設集，才能建立登陸頁面並透過[!DNL Journey Optimizer B2B Edition]運用。 預設集包含用於登陸頁面的子網域。

在設定預設集之前，請確定至少有一個已設定的登陸頁面子網域具有&#x200B;_[!UICONTROL 成功]_&#x200B;狀態。

若要檢閱設定的登入頁面預設集，請前往&#x200B;**[!UICONTROL 管理]** > **[!UICONTROL 管道]**。 在導覽窗格中的&#x200B;_[!UICONTROL 登陸頁面]_&#x200B;下方，選取&#x200B;**[!UICONTROL 登陸頁面預設集]**。

<!-- ![Channel configurations - landing page presets](./assets/config-channels-landing-pages-presets.png){width="800" zoomable="yes"} -->

按一下任何預設集名稱，以存取登陸頁面預設集詳細資訊。

### 建立登陸頁面預設集 {#lp-create-preset}

1. 按一下&#x200B;**[!UICONTROL 建立登陸頁面預設集]**。

1. 輸入預設集的名稱和說明。

   名稱必須以字母(A-Z)開頭，且僅包含英數字元、底線`_`、點`.`和連字型大小`-`字元。

1. 選取登陸頁面子網域。

   <!-- ![Landing page preset with name, description, and subdomain](./assets/config-channels-landing-pages-preset-create.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >若要能夠選取子網域，請確定您先前已設定至少一個登陸頁面子網域。

   與所選子網域對應的設定隨即顯示。

1. 您可以核取&#x200B;**[!UICONTROL 與登陸頁面子網域相同]**&#x200B;選項，以選取&#x200B;**[!UICONTROL 追蹤URL]**&#x200B;的登陸頁面子網域。

   <!-- [Learn more about tracking](../email/message-tracking.md) -->

   <!-- ![Landing page preset with subdomain settings](./assets/config-channels-landing-pages-preset-subdomain-settings.png){width="500" zoomable="yes"} -->

   例如，如果登陸頁面URL是`pages.mail.luma.com`，而追蹤URL是`data.mail.luma.com`，您可以選擇使用`pages.mail.luma.com`做為追蹤子網域。

   <!-- 
    >[!CAUTION]
    >
    >The selected landing page subdomain is used to specify the **[!UICONTROL Tracking URL]**and **[!UICONTROL Image Delivery URL]** if that subdomain was created using an [existing subdomain](#use-an-existing-subdomain).
    >
    >If the subdomain was created using the [Add your own domain](#configure-a-new-subdomain) option, the primary subdomain (such as the first delegated subdomain) is used instead. We don't have the existing option right now.
    -->

1. 按一下&#x200B;**[!UICONTROL 提交]**&#x200B;以確認建立登陸頁面預設集。

   <!--You can also save the preset as draft and resume its configuration later on.-->

   建立登入頁面預設集後，預設集會顯示在&#x200B;_[!UICONTROL 作用中]_&#x200B;狀態的清單中，且已準備好用來建立登入頁面。