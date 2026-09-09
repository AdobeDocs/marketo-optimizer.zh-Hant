---
title: 電子郵件傳遞能力設定
description: 為Marketo Optimizer設定子網域委派、DMARC、SPF、DKIM和IP集區。
TQID: 'https://experienceleague.adobe.com/-7yEXTaOrGIfCFw-UzanMqA9VJ1Nk-BmdmE2JJJSoB4'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3c1de303-7a7c-59a6-abca-8c534730e19cid: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a659ad61-de21-559d-a901-02e2fb329ff5id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 2502
ht-degree: 0%

---

# 電子郵件傳遞能力

下列資訊適用於設定傳送基礎架構以支援行銷人員和電子郵件內容建立者的管理員。 它說明傳遞能力功能，以及如何設定子網域、驗證和IP集區。

[!DNL Adobe Marketo Optimizer]中的電子郵件傳遞能力是一組基礎架構和驗證設定，可協助電子郵件訊息到達收件者的收件匣，而非垃圾郵件資料夾，且不會被ISP （網際網路服務提供者）封鎖。

這會使用以下建置區塊，由管理員設定，通常依照以下順序：

1. [委派一或多個子網域](#subdomain-delegation)給Adobe。
1. [在每個子網域上設定DMARC、SPF和DKIM記錄](#dmarc-spf-dkim)。
1. [確認用於傳送子網域電子郵件的IP集區](#ip-pools)。
1. [建立一個或多個電子郵件通道設定](../admin/email-channel-configuration.md#create-email-channel-configuration)，以繫結子網域、IP集區和寄件者身分識別。

![電子郵件傳送設定Marketo Optimizer](./assets/email-deliverability-diagram.svg){width="600"}

>[!TIP]
>
>將傳遞能力與管道設定視為一次性管理員活動。 設定後，行銷人員和電子郵件作者就不需要重新造訪。
>
> 如需電子郵件通道的其他資訊，請參閱下列主題：
>
>* 正在設定電子郵件通道 — [電子郵件通道設定](../admin/email-channel-configuration.md)
>* 建立電子郵件 — [新增電子郵件至歷程](../marketing/email-channel.md)
>* 設計電子郵件內容 — [電子郵件內容製作](../content/email-authoring.md)

## 目前限制 {#limitations}

* 子網域委派的&#x200B;**自訂委派方法**&#x200B;尚無法使用。 使用完全委派或CNAME。 GA版本的目標為自訂委派。
* 在Beta中無法使用&#x200B;**專用IP集區**。 共用IP集區是唯一的選項。 GA提供專屬的IP，包括IP熱身計畫和PTR記錄管理。

## 重要概念 {#key-concepts}

在設定電子郵件之前，請檢閱這些適用於電子郵件通道傳遞能力的概念：

| 概念 | 在[!DNL Marketo Optimizer]中的意義 |
| ------- | ---------------------- |
| **_子網域_** | 您用來透過[!DNL Marketo Optimizer]傳送電子郵件的傳送網域委派部分（例如，`mail.contoso.com`）。 子網域會將您的B2B行銷信譽與公司或交易郵件隔離。 |
| **_IP集區_** | 與一或多個子網域相關聯的一組IP位址。 [!DNL Marketo Optimizer]在此版本中支援Adobe管理的共用IP集區；專用IP集區位於GA藍圖上。 |
| **_頻道設定_** | 一組可重複使用的電子郵件傳送設定（寄件者身分、回覆位址、子網域、IP集區、電子郵件型別和追蹤），可附加至歷程中的電子郵件動作。 您可以對不同品牌、業務單位或傳送型別擁有多個已命名管道設定。 |

<!--

## Roles and permissions {#roles-permissions}

[!DNL Marketo Optimizer] uses role-based access control (RBAC) for email features. Permissions are managed in the Adobe Admin Console (IMS) and synced at login. Product administrators assign granular permissions to product profiles, and then attach those product profiles to users.

Access to email functionality in [!DNL Marketo Optimizer] is gated by two layers:

1. **Feature flag (LD).** A LaunchDarkly flag controls whether the entire feature is turned on for your organization. Email authoring and deliverability are gated by `dx_ajo_btob_channel_foundation`. Without this flag, the feature is hidden regardless of permissions.
2. **Functional permission.** A user-level permission that controls whether a specific user can read or write within a feature.

Most email features follow a `view-*` (read) and `manage-*` (write) pattern. A user needs the read permission to see a feature in the navigation, and the write permission to create, edit, or delete within it.

### Email authoring permissions {#email-authoring-permissions}

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View emails** | `view-b2b-emails` | View the email list, open emails, view content (read-only). |
| **Create / edit / delete emails** | `manage-b2b-emails` | All read access plus create, edit, duplicate, and delete emails. Required to author email content within a journey. |
| **View templates** | `view-b2b-templates` | Browse and preview templates in the Templates gallery (read-only). |
| **Create / edit / delete templates** | `manage-b2b-templates` | All read access plus create, edit, and delete saved templates. |
| **View fragments** | `view-b2b-fragments` | Browse and preview visual fragments (read-only). |
| **Create / edit fragments** | `manage-b2b-fragments` | All read access plus create and edit visual fragments. |
| **Publish fragments** | `publish-b2b-fragments` | Publish a fragment so it becomes available to email authors across the organization. |
| **Manage shared assets and library items** | `manage-b2b-library-items` | Manage the underlying shared library used by templates, fragments, and emails. Often granted alongside the template/fragment manage permissions. |
| **Manage usage labels** | `manage-b2b-delete-usage-labels` | Manage data usage labels (DULE) attached to library items for governance. |
| **Manage packages** | `manage-b2b-packages` | Bundle and move templates, fragments, and emails between sandboxes. |
| **View assets (Marketo Design Studio assets in [!DNL Marketo Optimizer])** | `view-b2b-assets` | Browse the asset picker and preview images. Read-only. |
| **Manage assets** | `manage-b2b-assets` | All read access plus future asset-management actions (Beta scope). |
| **Export message data** | `manage-b2b-message-export` | Export email-level message data and reports. |

Within a person journey, the **Send email** action requires `manage-b2b-person-journeys` (to add the action and activate the journey). A user with only email permissions can author content but cannot add an email to a journey.

### Email deliverability permissions {#email-deliverability-permissions}

Deliverability features (subdomains, DMARC, IP pools, suppression lists, allowed lists, IP warmup plans, and seed lists) are administrator-level configuration. They are governed by two permissions covering the entire **[!UICONTROL Channels]** > **[!UICONTROL Email settings]** area:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View email settings** | `view-b2b-email-settings` | View subdomains, PTR records, IP pools, suppression list, allowed list, IP warmup plans, and seed lists (read-only). |
| **Manage email settings** | `manage-b2b-email-settings` | All read access plus delegate subdomains, configure DMARC, manage suppression and allowed lists, manage IP warmup plans and seed lists. |

Some sub-features within Email settings are gated by additional LaunchDarkly flags — Suppression list (`enable-suppression`), Allowed list (`enable-allow-list`), Seed lists (`enable-seedlist-ui`). If a sub-feature is not visible in your organization, check with your Adobe representative on flag enablement.

### Channel configuration permissions {#channel-configuration-permissions}

Channel configurations sit under **[!UICONTROL Channels]** → **[!UICONTROL General settings]**. They tie deliverability primitives (subdomain, IP pool, sender identity) to a reusable object that journey authors reference. They are governed by a single permission:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **Manage channel configurations** | `manage-b2b-channels-configurations` | View, create, edit, and delete email channel configurations. |

-->

## 子網域委派 {#subdomain-delegation}

子網域委派會告訴網際網路，Adobe已獲得授權，可以代表您網域的特定子網域（例如，`mail.contoso.com`）傳送電子郵件。 委派專屬的子網域（而不是您的根網域）可保護您的公司郵件，並提供下列優點：

* **信譽隔離。** 行銷傳送與公司郵件會分開。 如果行銷信譽下降，您的交易和公司郵件不受影響。
* **更快速的IP熱身。** 專用子網域可協助透過ISP更快建立正面的傳送者信譽。
* **新式驗證。** SPF、DKIM和DMARC可針對每個子網域進行徹底的設定，而不會影響其他郵件流程。
* **法規遵循。** 協助滿足Gmail、Yahoo和其他主要ISP的大量寄件者需求。

>[!NOTE]
>
>[!DNL Marketo Optimizer]中的每個子網域只能由一個Adobe產品使用。 您無法在[!DNL Marketo Optimizer]和其他產品（例如Adobe Marketo Engage或Adobe Campaign）之間共用相同的傳送子網域，您必須使用不同的子網域。

### 支援的方法 {#supported-methods}

[!DNL Marketo Optimizer]支援此Beta發行版本中三種子網域委派方法中的兩種。 第三個方法（自訂委派）在藍圖上。

| 方法 | 使用時機 | 它包含的內容 |
| ------ | ----------- | ---------------- |
| **已完全委派** | 推薦 | 將子網域的完整DNS授權委派給Adobe。 Adobe會建立及維護MX、SPF、DKIM、DMARC、A和CNAME記錄。 最低的營運負荷。 Adobe會為您處理DNS變更。 |
| **CNAME** | 針對受限制的原則 | 將DNS授權保留在您的身邊，並建立指向Adobe管理記錄的CNAME記錄。 當貴組織的DNS原則不允許完全委派時，請使用此選項。 您有責任維護DNS記錄。 |
| **自訂委派** | 藍圖(GA) | 維護DNS和SSL憑證的完整所有權。 提供最大程度的控制，包括使用您自己的憑證的能力。 此目標為GA版本。 |

### 委派子網域（完全委派方法） {#delegate-fully-delegated}

>[!PREREQUISITES]
>
>* 決定子網域命名慣例（例如，`mail.contoso.com`代表行銷，`alerts.contoso.com`代表異動）。
>* 向您的IT/DNS團隊確認他們可以將子網域（NS記錄）委派給Adobe。
>* 在您的DNS提供者中建立新的子網域，然後等候24到48小時讓DNS傳播，再委派給Adobe。
>* 確認您擁有[!DNL Marketo Optimizer]中的管理員角色。

1. 在[!DNL Marketo Optimizer]左側導覽中，展開&#x200B;**[!UICONTROL 管理]**&#x200B;並選取&#x200B;**[!UICONTROL 管道]**。
1. 在面板中，展開&#x200B;**[!UICONTROL 電子郵件設定]**&#x200B;並選取&#x200B;**[!UICONTROL 子網域]**。
1. 按一下&#x200B;**[!UICONTROL 設定子網域]**。
1. 輸入完整子網域名稱（例如，`mail.contoso.com`）。
1. 選擇&#x200B;**[!UICONTROL 完全委派]**&#x200B;作為委派方法。
1. 設定子網域的DMARC （請參閱[DMARC、SPF和DKIM](#dmarc-spf-dkim)）。

   至少需使用開始原則`none`來設定DMARC記錄，以便監視報告而不影響傳遞。

1. 檢視Adobe要管理的DNS記錄清單。

   這些通常包括MX、SPF、DKIM、DMARC、A和CNAME記錄（用於追蹤和映象頁面URL）。

1. 使用&#x200B;**[!UICONTROL 下載記錄]**&#x200B;按鈕將DNS記錄下載為CSV檔案。 與您的DNS團隊共用此檔案。

1. 您的DNS團隊會在您的網域託管解決方案中新增NS記錄，該解決方案會將子網域委派給Adobe。

1. 在您的DNS團隊確認記錄已就緒後，請返回[!DNL Marketo Optimizer]並核取方塊，確認您已在代管網站上建立所需記錄。

1. 按一下「**[!UICONTROL 提交]**」以啟動一系列驗證檢查（預先驗證、MX、SPF、DKIM、DMARC、FBL註冊）。

1. 等候子網域狀態變更為&#x200B;**[!UICONTROL 成功]**。

   這通常需要DNS傳播完成後的幾分鐘時間。

>[!NOTE]
>
>如果驗證失敗，狀態會變更為&#x200B;**[!UICONTROL 失敗]**，[!DNL Marketo Optimizer]會顯示原因（例如，找不到NS記錄、遺失MX記錄或DMARC設定錯誤）。 請修正基礎DNS問題，然後重試提交。

### 委派子網域（CNAME方法） {#delegate-cname}

只有在貴組織的DNS原則禁止完全委派時，才使用此方法。 使用CNAME時，您可以自行維護DNS記錄。

1. 在[!DNL Marketo Optimizer]左側導覽中，展開&#x200B;**[!UICONTROL 管理]**&#x200B;並選取&#x200B;**[!UICONTROL 管道]**。
1. 在面板中，展開&#x200B;**[!UICONTROL 電子郵件設定]**&#x200B;並選取&#x200B;**[!UICONTROL 子網域]**。
1. 按一下&#x200B;**[!UICONTROL 設定子網域]**。
1. 輸入完整子網域名稱。
1. 選擇&#x200B;**[!UICONTROL CNAME]**&#x200B;做為委派方法。
1. 設定子網域的DMARC （[DMARC、SPF和DKIM](#dmarc-spf-dkim)）。
1. 檢閱要產生的CNAME記錄清單。 這些會將您子網域的元件指向Adobe管理的記錄。
1. 將記錄下載為CSV檔並與您的DNS團隊共用。
1. 您的DNS團隊會將每個CNAME記錄新增到您的DNS託管解決方案。
1. 當記錄已就緒並傳播時，請返回[!DNL Marketo Optimizer]並確認。
1. 按一下&#x200B;**[!UICONTROL 提交]**。
1. 等待狀態達到&#x200B;**[!UICONTROL 成功]**。

>[!IMPORTANT]
>
>使用CNAME時，Adobe無法協助您變更、維護子網域的DNS，或針對其進行疑難排解。 任何未來的變更（例如為功能更新新增新的CNAME）都必須由您的DNS團隊進行。

如需常見DNS提供者的逐步指示，請參閱下列章節：

### 依DNS提供者新增CNAME記錄 {#add-cname-records-dns-provider}

[!DNL Marketo Optimizer]會產生您子網域的確切CNAME和TXT記錄，並讓您將其下載為CSV檔案。 使用以下提供者專屬步驟，協助您的DNS團隊找到正確的設定畫面並新增每筆記錄。

>[!NOTE]
>
>下載的CSV中的主機、型別和目標值是您的子網域和組織專屬的值。 請完全複製，而非重複使用其他子網域中的值。

#### AWS路線53 {#aws-route-53}

1. 登入AWS管理主控台，並開啟&#x200B;**[!UICONTROL Route 53]**。
1. 選取&#x200B;**[!UICONTROL 託管區域]**，然後為您的網域選擇託管區域。
1. 按一下&#x200B;**[!UICONTROL 建立記錄]**，並將路由原則設定為&#x200B;**[!UICONTROL 簡單路由]**。
1. CSV中的每一列：

   * **記錄名稱** — 僅輸入區域名稱之前的部分。 例如，對於`contoso.com`區域中的`data.mail.contoso.com`，請輸入`data.mail`。
   * **記錄型別** — 選擇`CNAME`或`TXT`以符合CSV。
   * **值** — 從CSV貼上目標。 對於TXT記錄，請以雙引號括住值。
   * **TTL** — 300秒就足夠了。

1. 按一下&#x200B;**[!UICONTROL 新增其他記錄]**&#x200B;至批次專案，然後在輸入所有資料列後&#x200B;**[!UICONTROL 建立記錄]**。

>[!NOTE]
>
>TXT值必須加上雙引號，否則記錄無法驗證。 CNAME記錄不能位於區域頂端，但這不會影響委派的子網域。

#### Cloudflare {#cloudflare}

1. 登入Cloudflare儀表板並選取您的網域。
1. 移至&#x200B;**[!UICONTROL DNS記錄]**&#x200B;並按一下&#x200B;**[!UICONTROL 新增記錄]**。
1. CSV中的每一列：

   * **型別** — 選擇`CNAME`或`TXT`。
   * **名稱** — 輸入主機部分，例如`data.mail`。 Cloudflare會自動附加您的網域。
   * **目標** （適用於CNAME）或&#x200B;**內容** （適用於TXT） — 貼上CSV中的值。
   * **Proxy狀態** — 設定為僅&#x200B;**[!UICONTROL DNS]** （灰色雲端圖示）。
   * **TTL** — 保留為&#x200B;**[!UICONTROL 自動]**。

1. 按一下每一列的&#x200B;**[!UICONTROL 儲存]**。

>[!IMPORTANT]
>
>您為[!DNL Marketo Optimizer]新增的每個記錄都必須顯示灰色雲端（僅限DNS），而非橘色雲端（已代理）。 代理記錄會透過Cloudflare的伺服器而非Adobe路由流量，這會中斷DKIM簽署、點選追蹤和跳出處理。 如果記錄顯示橘色，請按一下雲端圖示將其切換為灰色。

#### AZURE DNS {#azure-dns}

1. 登入Azure入口網站並開啟&#x200B;**[!UICONTROL DNS區域]**。
1. 選取您網域的DNS區域。
1. 按一下&#x200B;**[!UICONTROL +記錄集]**。
1. CSV中的每一列：

   * **名稱** — 輸入主機部分，例如`data.mail`。 Azure會附加區域名稱。
   * **型別** — 選擇`CNAME`或`TXT`。
   * 對於CNAME記錄，請在&#x200B;**[!UICONTROL 別名]**&#x200B;欄位中輸入CSV中的目標。
   * 若為TXT記錄，請將值貼到&#x200B;**[!UICONTROL 值]**&#x200B;欄位中。 Azure會為您處理引號。
   * **TTL** — 輸入數字和單位，例如300秒。

1. 按一下&#x200B;**[!UICONTROL 確定]**&#x200B;儲存每一列的記錄集。

>[!NOTE]
>
>使用標準CNAME記錄集，而不是「別名記錄集」選項，此選項僅指向Azure資源，而不是外部主機名稱。 每個CNAME記錄集只保留一個目標，符合[!DNL Marketo Optimizer]發出記錄的方式 — 每個主機一個CNAME。

#### Google Cloud DNS {#google-cloud-dns}

1. 開啟Google雲端主控台，然後前往&#x200B;**[!UICONTROL 網路服務]** > **[!UICONTROL 雲端DNS]**。
1. 為您的網域選取區域。
1. 按一下&#x200B;**[!UICONTROL 新增標準]**&#x200B;以新增記錄集。
1. CSV中的每一列：

   * **DNS名稱** — 輸入主機部分，例如`data.mail`。 雲端DNS會顯示區域尾碼，而您會在主機前加上前置詞。
   * **資源記錄型別** — 選擇`CNAME`或`TXT`。
   * **TTL** — 300秒就足夠了。
   * 對於CNAME記錄，請在&#x200B;**[!UICONTROL 正式名稱]**&#x200B;中輸入目標，並以結尾句點結束。
   * 若為TXT記錄，則將值貼到資料欄位。

1. 按一下每一列的&#x200B;**[!UICONTROL 建立]**。

>[!NOTE]
>
>規範名稱必須是完整名稱，並以結尾句點結束，否則解析會失敗。 您的DNS團隊也可以使用`gcloud dns record-sets create`命令新增每個記錄。

### 子網域護欄 {#subdomain-guardrails}

* **預設限制：**&#x200B;每個組織10個子網域。 如果您需要更多（根據合約，最多100個），請聯絡您的Adobe代表。
* **DNS傳輸：**&#x200B;允許24到48小時讓變更在全域傳播。 驗證可能會失敗，因為DNS尚未傳播。
* **子網域重複使用：**&#x200B;其他Adobe產品(Marketo Engage、Adobe Campaign)已使用的子網域無法在[!DNL Marketo Optimizer]中重複使用。

## DMARC、SPF和DKIM {#dmarc-spf-dkim}

DMARC、SPF和DKIM是電子郵件驗證標準。 一起向接收郵件伺服器證明您的郵件確實是以您網域的名義傳送，而且未受到欺騙。 現代ISP — Gmail、Yahoo、Microsoft — 需要這些標準才能大量傳送郵件。

| 記錄 | 表示 | 用途 |
| ------ | ---------- | ------- |
| **SPF** | 寄件者原則架構 | 列出允許從您的網域傳送郵件的郵件伺服器IP。 接收伺服器會拒絕來自不在此清單上IP的郵件。 當您委派子網域（已完全委派）時，Adobe會自動建立及維護SPF記錄。 |
| **DKIM** | DomainKeys識別的郵件 | 每個傳出電子郵件都新增了密碼編譯簽章。 接收伺服器會根據DNS中發佈的公開金鑰來驗證簽章。 在子網域委派期間，Adobe會自動產生DKIM金鑰和DNS記錄。 |
| **DMARC** | 網域型訊息驗證、報告和符合性 | 告訴接收伺服器如果SPF或DKIM失敗該怎麼做 — 並提供有關驗證結果的報告。 DMARC有三種原則模式：無、隔離和拒絕。 |

### DMARC原則模式 {#dmarc-policy-modes}

| 原則 | 動作 | 使用時機 |
| ------ | ------ | ----------- |
| `none` | 監視 | 如果DMARC失敗，接收伺服器不會執行任何動作，但仍會傳送報表。 首次委派子網域以確認驗證運作正常，且不會出現訊息遺失風險時，請使用此選項。 |
| `quarantine` | 隔離 | 接收伺服器會將失敗的郵件放入垃圾郵件/垃圾郵件資料夾。 |
| `reject` | 拒絕 | 接收伺服器會拒絕（退回）驗證失敗的訊息。 最嚴格的模式。 當您對驗證設定有信心時，建議使用此選項。 |

### 設定DMARC {#configure-dmarc}

DMARC是在委派子網域時進行設定，但您也可以為已委派的子網域新增或更新DMARC 。

1. 在[!DNL Marketo Optimizer]左側導覽中，展開&#x200B;**[!UICONTROL 管理]**&#x200B;並選取&#x200B;**[!UICONTROL 管道]**。

1. 在面板中，展開&#x200B;**[!UICONTROL 電子郵件設定]**&#x200B;並選取&#x200B;**[!UICONTROL 子網域]**。

1. 在「子網域」清單中，找出您的子網域並勾選「DMARC記錄」欄。

   如果缺少記錄，則會顯示警報。

1. 開啟子網域並捲動至DMARC記錄區段。

   * 如果父網域上已存在DMARC記錄，[!DNL Marketo Optimizer]會自動擷取值。 您可以保留或覆寫。
   * 如果記錄不存在，請選擇&#x200B;**[!UICONTROL 使用Adobe管理]**，Adobe會建立並託管DMARC記錄。

1. 設定原則： `none`、`quarantine`或`reject`。 從`none`開始，除非您的上層網域已有成熟的DMARC狀態。

1. （選用）設定其他DMARC標籤（`sp`用於子網域原則，`pct`用於百分比，`rua`和`ruf`用於報表地址）。

1. 若使用已完全委派，請按一下&#x200B;**[!UICONTROL 儲存]**。

   Adobe會自動套用記錄。 如果使用CNAME，請複製DNS記錄並讓您的DNS團隊新增它，然後在[!DNL Marketo Optimizer]中確認。

1. 允許DNS傳播最多48小時，然後驗證子網域頁面上的DMARC狀態指標是綠色/狀況良好。

>[!TIP]
>
>從`policy=none`開始以監視驗證報告，然後進展到`quarantine`，最後在您的報告顯示健康的SPF和DKIM對齊後進展到`reject`。 直接移至`reject`而不進行監視，可能會導致合法郵件遭到拒絕。

## IP集區 {#ip-pools}

IP集區是用來傳送電子郵件的已命名IP位址群組。 IP集區對傳送者信譽至關重要：每個集區在ISP中都有自己的信譽，因此一個集區的問題（例如觸發垃圾郵件投訴的行銷突發事件）不會汙染另一個集區（例如交易確認）。

### 集區型別 {#pool-types}

| 集區型別 | 可用性 | 說明 |
| --------- | ------------ | ----------- |
| **共用IP集區** | 可於Beta取得 | 由Adobe管理並在許多客戶間共用的IP位址集區。 Adobe會在整個集區維護信譽。 最適合中低階電子郵件數量，以及不想管理IP熱身的客戶使用。 |
| **專用IP集區** | 藍圖(GA) | 一或多個IP位址僅分配給您的組織。 您擁有聲譽。 建議高容量寄件者使用。 包括IP熱身計畫和PTR記錄管理。 |

### 檢閱和指派IP集區 {#review-ip-pool}

在此版本中，會為您的組織預先布建IP集區。 您在建立電子郵件通道設定時指派IP集區。

1. 在[!DNL Marketo Optimizer]左側導覽中，展開&#x200B;**[!UICONTROL 管理]**&#x200B;並選取&#x200B;**[!UICONTROL 管道]**。
1. 在面板中，展開&#x200B;**[!UICONTROL 電子郵件設定]**&#x200B;並選取&#x200B;**[!UICONTROL IP集區]**。
1. 確認貴組織可以使用狀態為&#x200B;**[!UICONTROL 作用中]**&#x200B;的IP集區。
1. 將游標停留在集區上以檢視IP位址及其PTR記錄（反向DNS）。
1. 如果您的組織有多個業務單位或品牌，在建立管道設定之前，請先規劃如何使用IP集區（例如，行銷集區與網路研討會集區）。

>[!IMPORTANT]
>
>請勿在同一IP集區上混合行銷和異動流量，即使共用集區可供使用亦然。 管道設定上的電子郵件型別設定（行銷與交易）會控制隱藏行為，但您的管道設定仍應儘可能使用不同的集區。

<!--

### Frequently asked questions {#faq}

| Question | Answer |
| -------- | ------ |
| **Can I reuse the subdomain I already use in Marketo Engage?** | No. A subdomain can only be associated with one Adobe product at a time. Create a new subdomain (for example, mail2.contoso.com) for [!DNL Marketo Optimizer]. |
| **Why does my channel configuration show Failed?** | The most common reasons are: MX record validation failed (your subdomain DNS isn't fully configured); DMARC misalignment; or an IP pool that is in Processing and has never been associated with the selected subdomain. Open the configuration to see the specific reason. |
| **What happens if a personalization token has no value at send time?** | If you defined a fallback with the Handlebars `default` helper, the fallback is used. If not, the token resolves to an empty string. [!DNL Marketo Optimizer] warns you when a token has no fallback and the underlying attribute is not guaranteed by the audience definition. |
| **Can I personalize using account-level attributes?** | Not in this release. Personalization in [!DNL Marketo Optimizer] today supports profile attributes only. |
| **What's the maximum email size?** | 100 KB is the recommended best-practice cap for inbox rendering. [!DNL Marketo Optimizer] warns you in the editor if you exceed it. |
| **Can I migrate existing Marketo email templates into [!DNL Marketo Optimizer]?** | A guided self-serve migration tool — including Velocity-to-Handlebars conversion — is delivered at GA. In this release, you can manually rebuild templates or paste raw HTML. |
| **Will my updates to Marketo assets show up in [!DNL Marketo Optimizer]?** | No. Asset availability in [!DNL Marketo Optimizer] is based on a one-time copy from Marketo Design Studio. Re-uploaded or modified Marketo assets are not reflected in [!DNL Marketo Optimizer] today. Native asset upload and management within [!DNL Marketo Optimizer] is on the Beta roadmap. |

## Glossary {#glossary}

| Term | Definition |
| ---- | ---------- |
| **DKIM** | DomainKeys Identified Mail — cryptographic email signature. |
| **DMARC** | Domain-based Message Authentication, Reporting & Conformance. |
| **FBL** | Feedback Loop — a service ISPs offer to receive spam-complaint reports back to senders. |
| **Handlebars** | JavaScript templating language used in [!DNL Marketo Optimizer] for personalization expressions. |
| **IP pool** | Group of IP addresses used to send email. |
| **MX record** | Mail Exchange DNS record — directs incoming mail to the correct mail servers. |
| **NS record** | Name Server DNS record — used to delegate a subdomain. |
| **PTR record** | Pointer record — reverse DNS that maps an IP address back to a hostname. |
| **RBAC** | Role-Based Access Control. |
| **SPF** | Sender Policy Framework — DNS record listing authorized sending IPs. |
| **Subdomain delegation** | Granting Adobe authority over a portion of your domain (a subdomain) for sending email. |

-->


