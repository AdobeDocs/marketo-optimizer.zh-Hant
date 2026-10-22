---
title: 產品許可權
description: 控制對Experience Platform功能存取的Marketo Optimizer許可權參考清單，包含管理員、完全存取和唯讀使用者的說明和建議許可權。
TQID: https://experienceleague.adobe.com/Q4HnGxPkiE0dsZUjIgPvVJHgs0dPwLJiOKVSL1edS4Y
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
    internal-label: Setup
  - id: a659ad61-de21-559d-a901-02e2fb329ff5
    internal-label: Administration
subfeature_v2:
  - id: b6434e31-d7bb-5416-960c-1c77bb1a2e8d
    internal-label: User Access
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
autotag-review: '2026-10-20T17:03:48.312Z'
source-git-commit: a33f749c32631dcd77ecf2892bdc3b1a5e06cd66
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 3%
---
# 產品許可權

下列許可權控制[!DNL Adobe Marketo Optimizer]中功能的存取。 將它們新增至[!DNL Adobe Experience Platform]的&#x200B;_[!UICONTROL 許可權]_&#x200B;區域中的角色。 如需有關建立角色並將其指派給使用者的詳細資訊，請參閱&#x200B;[_使用者存取權和許可權_](./user-management.md)。

最後三欄顯示每個[建議的使用者型別](#suggested-user-types)所建議的許可權： Admin、All Access User和Read Only Access User。 核取記號(✔)表示建議該使用者型別使用許可權，虛線(-)表示不建議使用。 調整建議以適合您的組織。

>[!IMPORTANT]
>
>[!DNL Marketo Optimizer]存取權需要您啟用使用下列命名慣例布建的特定沙箱： `Mktoaep` + [!DNL Marketo Engage]訂閱前置詞。 例如，如果連結的[!DNL Marketo Engage]訂閱首碼是&#x200B;_AcmeAssoc_，則存取[!DNL Marketo Optimizer]所需的沙箱是&#x200B;_MktoaepAcmeAssoc_。 將此沙箱新增至每個角色。

>[!NOTE]
>
>您必須是系統管理員才能在Experience Platform中看到&#x200B;_[!UICONTROL 許可權]_&#x200B;圖磚。

部分許可權適用於產品尚未提供的功能。 管理員現在可以新增這些許可權，這樣使用者在功能可用時就可以擁有適當的存取權。

## 建議的使用者型別 {#suggested-user-types}

使用此頁面表格中的許可權建議作為您建立之角色的起點。 這些是每種使用者型別的建議。 調整這些欄位以符合您的組織。

| 屬性 | 管理員 | 所有存取使用者 | 唯讀存取許可權使用者 |
| --- | ----- | --------------- | --------------------- |
| **代表**&#x200B;的人員 | 為您的團隊設定及管理[!DNL Marketo Optimizer]的人員。 | 每日在[!DNL Marketo Optimizer]中工作的行銷人員和操作者。 | 需要檢視[!DNL Marketo Optimizer]但不變更任何專案的人員，例如主管、分析師和稽核師。 |
| **他們能做什麼** | 全部，包括設定和管理設定。 | 使用每個功能：歷程、程式、內容、清單、報告和助理。 | 檢視歷程、程式、內容、清單及報告，並詢問助理員問題。 |
| **要指派的許可權** | 此頁面上的每個許可權（在角色編輯器中選取&#x200B;**[!UICONTROL 全部新增]**）。 | 此頁面上資料表的&#x200B;_所有存取_&#x200B;資料行中具有✔的許可權。 | 此頁面上資料表的&#x200B;_唯讀_&#x200B;資料行中具有✔的許可權。 |
| **不包含** | – | <li>管理員設定<li>管道設定，包括電子郵件設定、表單預設集、登陸頁面設定，以及WhatsApp預設集和設定<li>計畫型別（檢視和管理） | <li>建立、編輯、刪除、發佈或匯出（所有&#x200B;_管理_&#x200B;和&#x200B;_發佈_&#x200B;許可權，聊天存取許可權除外）<li>將對象啟用至目的地<li>管理員設定和管道設定，包括檢視電子郵件設定和表單預設集<li>檢視方案型別 |
| **建議的使用者群組** | Marketo Optimizer管理員群組 | Marketo Optimizer使用者群組 | Marketo Optimizer唯讀使用者群組 |
| **建議的角色** | Marketo Optimizer管理員 | Marketo Optimizer完全存取使用者 | Marketo Optimizer唯讀存取使用者 |

如需建立這些群組和角色的程式，請參閱[為建議的使用者型別建立使用者群組和角色](./user-management.md#create-suggested-roles)。

## 內容和資產 {#content-assets}

| 類別 | 權限 | 說明 | 管理員 | 完全存取 | 唯讀 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B Assets | 管理B2B Assets | 建立、編輯和刪除資產檔案。 | ✔ | ✔ | – |
| | 管理B2B電子郵件 | 建立、編輯和刪除電子郵件訊息。 | ✔ | ✔ | – |
| | 管理B2B Forms | 建立、編輯和刪除表單。 | ✔ | ✔ | – |
| | 管理B2B片段 | 建立、編輯和刪除內容片段。 | ✔ | ✔ | – |
| | 管理B2B登陸頁面 | 建立、編輯和刪除登入頁面。 | ✔ | ✔ | – |
| | 管理B2B訊息匯出 | 匯出&#x200B;_電子郵件_&#x200B;區段下的郵件報表。 | ✔ | ✔ | – |
| | 管理B2B範本 | 建立、編輯和刪除內容範本。 | ✔ | ✔ | – |
| | 管理B2B網路研討會 | 建立、編輯和刪除互動式網路研討會。 | ✔ | ✔ | – |
| | 發佈B2B Forms | 發佈表單以用於登陸頁面。 | ✔ | ✔ | – |
| | 發佈B2B片段 | 發佈內容片段，以用於範本、電子郵件和登入頁面。 | ✔ | ✔ | – |
| | 發佈B2B登陸頁面 | 發佈登陸頁面。 | ✔ | ✔ | – |
| | 檢視B2B Assets | 檢視Assets程式庫和資產檔案的詳細資訊。 | ✔ | ✔ | ✔ |
| | 檢視B2B電子郵件 | 檢視電子郵件訊息。 | ✔ | ✔ | ✔ |
| | 檢視B2B Forms | 檢視表單。 | ✔ | ✔ | ✔ |
| | 檢視B2B片段 | 檢視內容片段清單和詳細資訊。 | ✔ | ✔ | ✔ |
| | 檢視B2B登陸頁面 | 檢視登陸頁面。 | ✔ | ✔ | ✔ |
| | 檢視B2B範本 | 檢視內容範本清單和詳細資訊。 | ✔ | ✔ | ✔ |
| | 檢視B2B網路研討會 | 檢視互動式網路研討會。 | ✔ | ✔ | ✔ |

## 頻道設定和管理 {#channels-admin}

| 類別 | 權限 | 說明 | 管理員 | 完全存取 | 唯讀 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B管理設定 | 管理B2B管理設定 | 設定管理設定，例如數位資產管理連線、資產存放庫和事件。 | ✔ | – | – |
| B2B通道設定 | 管理B2B管道設定 | 存取左側導覽中的&#x200B;_管道_&#x200B;功能表專案以及所有管道設定作業。 | ✔ | – | – |
| | 管理B2B電子郵件設定 | 設定電子郵件設定。 使用者傳送電子郵件前，必須先完成這些設定。 | ✔ | – | – |
| | 管理B2B Forms預設集 | 建立、編輯和刪除表單預設集。 | ✔ | – | – |
| | 管理B2B登陸頁面設定 | 設定登陸頁面設定，例如子網域。 | ✔ | – | – |
| | 管理B2B WhatsApp預設集 | 建立、檢視和刪除WhatsApp訊息預設集和相關的SMS設定。 | ✔ | – | – |
| | 管理B2B WhatsApp設定 | 設定WhatsApp頻道設定。 | ✔ | – | – |
| | 發佈B2B Forms預設集 | 發佈表單預設集。 | ✔ | – | – |
| | 檢視B2B電子郵件設定 | 檢視電子郵件設定（子網域、PTR記錄、IP集區、隱藏清單、種子清單、IP熱身計畫）。 | ✔ | – | – |
| | 檢視B2B Forms預設集 | 檢視表單預設集。 | ✔ | – | – |

## 歷程、程式和資料夾 {#journeys-programs}

| 類別 | 權限 | 說明 | 管理員 | 完全存取 | 唯讀 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B資料夾權杖 | 管理B2B資料夾權杖 | 建立、編輯和刪除資料夾上的權杖。 變更會套用至資料夾中的所有專案，因此請將此專案與&#x200B;_管理B2B資料夾_&#x200B;分開指派。 | ✔ | ✔ | – |
| | 檢視B2B資料夾權杖 | 檢視資料夾上定義的權杖。 | ✔ | ✔ | ✔ |
| B2B資料夾 | 管理B2B資料夾 | 建立、編輯和刪除資料夾。 | ✔ | ✔ | – |
| | 檢視B2B資料夾 | 檢視資料夾。 | ✔ | ✔ | ✔ |
| B2B歷程 | 管理B2B歷程流量控制 | 設定歷程流量控制，包括模擬其效果。 | ✔ | ✔ | – |
| | 管理B2B個人歷程 | 存取&#x200B;_個人歷程_&#x200B;清單和所有個人歷程作業。 | ✔ | ✔ | – |
| | 發佈B2B個人歷程 | 發佈個人歷程。 | ✔ | ✔ | – |
| | 檢視B2B歷程流量控制 | 檢視歷程流量控制設定。 | ✔ | ✔ | ✔ |
| | 檢視B2B個人歷程報告 | 檢視個人歷程報告，包括&#x200B;_個人歷程個人_&#x200B;報告。 | ✔ | ✔ | ✔ |
| | 檢視B2B個人歷程 | 以唯讀方式存取&#x200B;_個人歷程_&#x200B;清單和歷程詳細資料。 | ✔ | ✔ | ✔ |
| B2B計畫權杖 | 管理B2B方案Token | 在計畫和計畫型別上建立、編輯和刪除權杖。 | ✔ | ✔ | – |
| | 檢視B2B方案Token | 檢視在計畫和計畫型別上定義的權杖。 | ✔ | ✔ | ✔ |
| B2B程式型別 | 管理B2B程式型別 | 建立、編輯和刪除行銷方案型別。 | ✔ | – | – |
| | 檢視B2B程式型別 | 檢視行銷方案型別。 | ✔ | – | – |
| B2B計畫 | 管理B2B計畫 | 建立、編輯和刪除行銷方案。 | ✔ | ✔ | – |
| | 檢視B2B計畫 | 檢視行銷方案。 | ✔ | ✔ | ✔ |

## 對象、意圖和目的地 {#audiences-intent}

| 類別 | 權限 | 說明 | 管理員 | 完全存取 | 唯讀 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B目的地 | 啟用B2B目的地 | 將受眾啟用至B2B目的地。 | ✔ | ✔ | – |
| | 管理B2B目的地 | 建立、編輯和刪除B2B目的地。 | ✔ | ✔ | – |
| | 檢視B2B目的地 | 對B2B目的地的僅限檢視存取權。 | ✔ | ✔ | ✔ |
| B2B意圖設定 | 管理B2B意圖設定 | 建立、編輯和刪除意圖組態。 | ✔ | ✔ | – |
| | 檢視B2B意圖設定 | 檢視意圖設定（意圖加權模型）。 | ✔ | ✔ | ✔ |
| B2B組織規則 | 管理B2B組織規則 | 建立、編輯和刪除組織規則。 | ✔ | ✔ | – |
| | 檢視B2B組織規則 | 檢視組織規則。 | ✔ | ✔ | ✔ |
| B2B個人清單 | 管理B2B個人清單 | 建立、編輯和刪除人員清單，以及管理清單成員資格。 | ✔ | ✔ | – |
| | 檢視B2B人員清單 | 檢視靜態和動態人員清單。 | ✔ | ✔ | ✔ |

## 報表、Labs和聊天 {#reports-labs-chat}

| 類別 | 權限 | 說明 | 管理員 | 完全存取 | 唯讀 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| B2B對話體驗 | 管理B2B對話體驗 | 存取聊天面板和助理。 面板中的動作也需要相符功能的許可權。 例如，建立歷程需要&#x200B;_管理B2B個人歷程_。 檢視[聊天許可權](#chat-permissions)。 | ✔ | ✔ | ✔ |
| B2B Labs | 管理B2B Labs | 啟用和設定Labs功能。 | ✔ | ✔ | – |
| | 檢視B2B Labs | 檢視可用和啟用的Labs功能。 | ✔ | ✔ | ✔ |
| B2B報告 | 檢視B2B內嵌報表 | 檢視&#x200B;_報告_&#x200B;標籤中的報告。 | ✔ | ✔ | ✔ |
| | 檢視B2B意圖報告 | 檢視意圖報表。 | ✔ | ✔ | ✔ |

## 聊天許可權 {#chat-permissions}

聊天許可權遵循功能層級的許可權。 [!DNL Coworker for Marketo Optimizer]會根據功能在聊天以外所需的相同許可權檢查聊天中的每個技能或動作： _管理_&#x200B;建立、編輯或發佈的許可權，以及&#x200B;_檢視_&#x200B;唯讀技能的許可權。 如果使用者缺少功能許可權，[!DNL Coworker]無法為他們執行該動作。 例如，建立歷程需要&#x200B;_管理B2B個人歷程_，而列出表單需要&#x200B;_檢視B2B Forms_。

<!--
_Manage B2B Conversational Experience_ gives access to the [!DNL CX Coworker] chat panel, but it does not grant access to any feature functions.

Per wiki: 
Update 10/02: We are no longer mapping b2b-conversational-experience read or write to any tools. It was decided that chat will be available for all users without permissions, but what they can do within the chat (i.e. tools they can use) will be defined by other permissions.
-->

## 外部目的地許可權 {#external-destinations-permissions}

若要為[!DNL Marketo Optimizer]中的使用者提供外部目的地的存取權，需要下列許可權。 欄遵循[建議的使用者型別](#suggested-user-types)中說明的每個使用者型別的相同建議。

| 類別 | 權限 | 說明 | 管理員 | 完全存取 | 唯讀 |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| 儀表板 | 管理標準儀表板 | 新增尚未在Data Warehouse的自訂屬性。 | ✔ | ✔ | – |
| | 檢視標準儀表板 | 對&#x200B;_設定檔_、_目的地_&#x200B;和&#x200B;_區段_&#x200B;儀表板的僅限檢視存取權。 也可讓您存取左側導覽中的&#x200B;_儀表板_。 | ✔ | ✔ | ✔ |
| 目的地 | 啟用目的地 | 啟用作用中目的地的資料。 也需要&#x200B;_檢視目的地_&#x200B;或&#x200B;_管理目的地_。 | ✔ | ✔ | – |
| | 啟用區段而不進行對應 | 無需對應步驟即可將受眾啟動至現有目的地。 使用者可以在啟動工作流程中新增和移除對象，但無法新增或移除對應的屬性或身分。 也需要&#x200B;_檢視目的地_。 | ✔ | ✔ | – |
| | 目的地製作 | 使用Experience Platform Destination SDK製作目的地。 | ✔ | ✔ | – |
| | 管理和啟用資料集目的地 | 檢視、建立、編輯和停用資料集匯出流程，以及啟用資料集的資料。 也需要&#x200B;_檢視目的地_。 | ✔ | ✔ | – |
| | 管理目的地 | 檢視、建立及刪除目的地連線和目的地帳戶。 | ✔ | ✔ | – |
| | 檢視目的地 | 檢視&#x200B;_目錄_&#x200B;索引標籤中的可用目的地和&#x200B;_瀏覽_&#x200B;索引標籤中的已驗證目的地。 | ✔ | ✔ | ✔ |
| 資料治理 | 管理B2B刪除使用標籤 | 檢視、建立和刪除套用至資料集和結構描述的資料使用標籤(DULE)。 | ✔ | ✔ | – |
| | 管理資料使用原則 | 檢視、建立、編輯和刪除資料使用原則。 | ✔ | ✔ | – |
| | 檢視資料使用原則 | 屬於您組織的資料使用原則的僅限檢視存取權。 | ✔ | ✔ | ✔ |
| 資料擷取 | 管理來源 | 檢視、建立、編輯和停用來源。 | ✔ | ✔ | – |
| | 檢視來源 | 檢視&#x200B;_目錄_&#x200B;標籤中的可用來源，以及&#x200B;_瀏覽_&#x200B;標籤中的已驗證來源。 | ✔ | ✔ | ✔ |
| 輪廓管理 | 管理設定檔設定 | 檢視並編輯所有設定檔設定。 | ✔ | ✔ | – |
| | 檢視設定檔設定 | 僅供檢視即可存取所有設定檔設定。 | ✔ | ✔ | ✔ |

<!-- 

## Planned permissions {#planned-permissions}

The following permissions are for features that are not yet available in [!DNL Marketo Optimizer]. Adobe Marketo Qualifier permissions are not currently enforced. The estimated enforcement date is November 2026. Accounts and buying groups are targeted for delivery in Q1 2027.

| Category | Permission | Description | Admin | All Access | Read Only |
| -------- | ---------- | ----------- | :---: | :--------: | :-------: |
| Marketo Qualifier Configurations | Manage Marketo Qualifier Configurations | Create, edit, and delete Marketo Qualifier configurations. | ✔ | – | – |
| | View Marketo Qualifier Configurations | View Marketo Qualifier configurations. | ✔ | ✔ | ✔ |
| Marketo Qualifier Outbound | View Marketo Qualifier Outbound | View Marketo Qualifier outbound workflows and outbound reporting. | ✔ | ✔ | ✔ |
| Marketo Qualifier Research | Manage Marketo Qualifier Research | Use and manage research capabilities. | ✔ | ✔ | – |
| | View Marketo Qualifier Research | View research: conversational interface, prospect view, and account and lead research. | ✔ | ✔ | ✔ |
| B2B Account Lists | Manage B2B Account Lists | Create, edit, and delete account lists, including adding, removing, and importing accounts. | ✔ | ✔ | – |
| B2B Buying Groups | Manage B2B Buying Groups | Create, edit, and delete buying groups. | ✔ | ✔ | – |
| | Manage B2B Role Templates | Manage the role templates used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Solution Interests | Manage the solution interests used in buying groups. | ✔ | ✔ | – |
| | Manage B2B Stages | Manage buying group stages. | ✔ | ✔ | – |
| | View B2B Buying Groups | View buying groups. | ✔ | ✔ | ✔ |

-->
