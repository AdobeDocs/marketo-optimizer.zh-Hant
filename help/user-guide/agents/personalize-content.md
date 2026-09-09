---
title: 依角色個人化電子郵件內容
description: 使用Marketo Optimizer中的Content Personalization技能，將電子郵件轉換為以人物為基礎、以資料為基礎的變體。 個人化或分析電子郵件。
TQID: 'https://experienceleague.adobe.com/9fa1wfsHH6h46jJ-slLxMpB6fud1VHgmiWxbao-bWvo'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1236
ht-degree: 0%

---


# 依角色個人化電子郵件內容

_內容Personalization_&#x200B;技能可將一封電子郵件轉換為以人物為基礎、以資料為根據的變體，因此您不必為每個對象分別建立電子郵件。 此技能不是在活動後傳送訊息，而是將您的對象解析為[衍生角色](../audiences/personas.md)同類群組、顯示深入分析，並產生個人化變體。 每個變體都會儲存為單一電子郵件中的條件式內容，因此每個人在歷程傳送時都會自動收到符合其角色的版本。

* **技能** - `content-personalization`
* **引動** — 從[聊天介面](./chat-interface.md)，說明新電子郵件的目標對象，或選取&#x200B;**[!UICONTROL 個人化此電子郵件]**&#x200B;或&#x200B;**在[傳送電子郵件節點](../marketing/action-nodes.md)中的現有電子郵件上分析此電子郵件**
* **從**&#x200B;讀取/寫入 — [!DNL Marketo Optimizer]

## 重要概念 {#key-concepts}

| 術語 | 定義 |
|---|---|
| **角色同類群組** | 共用[衍生角色](../audiences/personas.md) （例如&#x200B;_CXO/EVP_&#x200B;或&#x200B;_個人貢獻者_）的一群人。 |
| **區段** | 由任何條件定義的一組人員，例如人員、產業或參與層級。 角色同類群組是由共用衍生角色所專屬定義的區段。 |
| **目標群組** | 您以自然語言描述的對象。 此技能會將其解析為相符的角色同類群組。 |
| **Insight** | 根據您自己的資料，尋找對同類角色表現最佳的訊息、定位或語調的相關資料提示發現。 |
| **變體** | 您選擇個人化的電子郵件區段個人化版本，針對一個角色同類群組產生。 |
| **AI個人化電子郵件** | 將每個變體捆綁為[條件式內容](../content/conditional-content.md)區塊的單一已儲存電子郵件。 |
| **電子郵件稽核** | 針對每個目標群組區段審查現有電子郵件，顯示哪些可引起共鳴，以及在您個人化之前需改善每個角色的內容。 |

## 先決條件 {#prerequisites}

* 在啟用同事的情況下存取[!DNL Marketo Optimizer]。
* 已在您的資料中解析[衍生角色](../audiences/personas.md)。 此技能需仰賴這些分類來建立角色同類群組。 已規劃在未來版本提供自訂角色支援。
* 足夠的歷史資料供深入分析使用。 如果無法使用角色同類群組的深入分析，技能會告訴您資料不足，並退回該角色的一般最佳實務。
* [電子郵件範本](../content/templates.md)或&#x200B;[_傳送電子郵件_&#x200B;動作節點](../marketing/action-nodes.md)參考的現有電子郵件。
* 包含用來傳遞個人化電子郵件的&#x200B;_傳送電子郵件_&#x200B;動作節點的[個人歷程](../marketing/person-journeys.md)。

## 從範本建立及個人化電子郵件 {#create-personalize-from-template}

此流量會作者新電子郵件，並在相同交談中將其個人化。

1. **提供內容。** 上傳內容簡介，或以自然語言描述您想要的內容。

1. 從範本資料庫中&#x200B;**選取[範本](../content/templates.md)**。

1. **檢閱草稿。**

   同事將您的內容對應至範本，並產生草稿電子郵件。 您可以內嵌編輯基本文字。

   >[!WARNING]
   >
   >在製作期間只能內嵌基本文字編輯。 若要進行進階編輯，請儲存電子郵件，並在[視覺設計空間](../content/email-authoring.md)中開啟。

1. **以自然語言描述目標群組**。

1. **檢閱已解析的角色同類群組**。

   同事會檢查您的資料，並傳回符合您說明的角色同類群組，以及每個角色同類群組的計數。 修訂目標群組說明，並視需要重試。

1. **確認目標群組**。

   然後同事會擷取每個已解析角色同類群組的深入分析。

1. **選取要個人化的區段**，例如主旨列或內文區段，並檢閱產生的變體。

   如果變體不適合，則重新產生變體。 角色同類群組數量未固定。 這取決於您的目標群組和資料。

1. **儲存電子郵件**。

   所有變體都會儲存在一個AI個人化電子郵件中，而不是作為單獨的電子郵件。

<!-- screenshot: Coworker chat panel showing the resolved persona cohorts with counts, and the "Personalized variants" review grid -->

## 分析現有電子郵件 {#analyze-existing-email}

在參考現有電子郵件的歷程&#x200B;[_傳送電子郵件_&#x200B;節點](../marketing/action-nodes.md)上，**[!UICONTROL 採取動作]**&#x200B;面板會顯示電子郵件名稱有兩個選項： **[!UICONTROL 個人化此電子郵件]**&#x200B;和&#x200B;**[!UICONTROL 分析此電子郵件]**。

<!-- screenshot: Send Email node "Take an action" panel showing the email name and the Personalize this email / Analyze this Email options -->

選取&#x200B;**[!UICONTROL 分析此電子郵件]**&#x200B;以執行電子郵件稽核：

1. **描述您想要個人化的目標群組**，以設定其角色。

   例如&#x200B;_行銷角色中的人員_&#x200B;或&#x200B;_領導職能中的人員_。

1. **檢閱電子郵件稽核。**

   同事將您的描述解析為角色區段，並顯示一張&#x200B;**電子郵件稽核**&#x200B;卡片，其中列出每個區段，然後針對每個區段檢閱電子郵件，以強調哪些區段能引起共鳴以及要改善什麼。

1. 同事詢問後續要做什麼，包括&#x200B;**[!UICONTROL 檢視逐節稽核]**&#x200B;和&#x200B;**[!UICONTROL 個人化此電子郵件]**。

1. 選取&#x200B;**[!UICONTROL 檢視逐節稽核]**&#x200B;以開啟&#x200B;**_電子郵件分析_**&#x200B;檢視，其中包含角色選擇器以及每個節的特定建議。

   每個區段顯示建議多少變更，而每個角色顯示建議計數，例如`4 recommendations for SVP/VP`。 您也可以在聊天中輸入&#x200B;_個人化_，直接套用建議。

1. 從稽核中選取&#x200B;**[!UICONTROL 個人化此電子郵件]**&#x200B;以套用見解並產生變體。

   請參閱下列章節，[_個人化現有的電子郵件_](#personalize-existing-email)。

<!-- screenshot: Email analysis view with persona selector, per-section "N changes" badges, and "what needs work" recommendations -->

## 個人化現有電子郵件 {#personalize-existing-email}

在&#x200B;_傳送電子郵件_&#x200B;動作節點上選取&#x200B;**[!UICONTROL 個人化此電子郵件]**，或繼續進行[電子郵件稽核](#analyze-existing-email)，以個人化您已建置的電子郵件。

1. **檢閱已解析的角色同類群組。**

   同事會檢查您的資料，並傳回符合您說明的角色同類群組，以及每個角色同類群組的計數。 修訂目標群組說明，並視需要重試。

   如果您是透過電子郵件稽核到達此步驟，Co-worker會直接從稽核深入分析繼續進行。

1. **選取要在電子郵件預覽中個人化的區段**，例如主旨列和特定內容區段，然後確認。

1. **檢閱產生的變體。**

   除了角色之外，變體也可能因行業而異，例如醫療保健領域的CXO與金融服務領域的CXO相比。 同事提供&#x200B;**[!UICONTROL 個人化變體]**&#x200B;格線，每個角色同類群組一張卡片，每張卡片都有主旨列、標題、內文和&#x200B;**[!UICONTROL 預覽]**&#x200B;選項。

   選取卡片上的&#x200B;_資訊_&#x200B;圖示，以檢視該變體背後的insight （其根據的角色和塑造該變體的參與insight），並視需要重新產生變體。

   您可以依角色篩選網格。

1. **儲存集。**

   按一下&#x200B;**[!UICONTROL 儲存]**&#x200B;並確認。 同事確認電子郵件現在可在AI資料庫中使用，然後詢問是否將變更同時套用至原始電子郵件，這會更新到適當位置。

<!-- screenshot: "Personalized variants" grid showing persona cards with subject, headline, body, Preview, and the info-icon insight tooltip -->

## 已儲存的輸出和在歷程中使用 {#saved-output}

無論您從哪個流程開始，個人化都會產生單一&#x200B;**AI個人化電子郵件**，並儲存在AI資料庫中。 電子郵件包含[由角色輸入的條件式內容](../content/conditional-content.md)區塊。 若要編輯區段，請在[視覺設計空間](../content/email-authoring.md)中開啟該區段，並預覽每個以人物為關鍵字的區塊解析方式，請使用&#x200B;**[!UICONTROL 模擬內容]**。

若要在歷程中使用電子郵件，請新增[傳送電子郵件節點](../marketing/action-nodes.md)，並選取&#x200B;**[!UICONTROL AI個人化電子郵件]**&#x200B;而非&#x200B;**[!UICONTROL 建立電子郵件]**，然後挑選儲存的電子郵件。 照常將您的設定和業務規則套用至節點。

<!-- screenshot: Send Email node configuration with "AI Personalized Emails" selected and the saved email applied -->

## 執行階段行為 {#run-time-behavior}

您在歷程中選取單一AI個人化電子郵件，而不是每個受眾選取一個變體。 當歷程執行時，電子郵件會自動解析為符合每個收件者角色的變體。 您不會為每個收件者選擇變體。

## 限制 {#limitations}

| 限制 | 詳細資料 |
|---|---|
| **自訂角色** | 尚未支援。 此技能僅會將來自現成[衍生角色](../audiences/personas.md)的角色同類群組分類。 |
| **資料不足，無法深入分析** | 如果您的資料不支援該角色同類群組的insight，則該技能會指出這點，並退回該角色的一般最佳實務。 |
| **在製作期間進行內嵌編輯** | 當您[從範本](#create-personalize-from-template)建立及個人化電子郵件時，只能內嵌編輯基本文字。 進階編輯需要[視覺化設計空間](../content/email-authoring.md)。 |
| **需要起點** | 個人化電子郵件需要範本或「傳送電子郵件」節點所參考的現有電子郵件。 |
