---
title: 條件式內容
description: 在Marketo Optimizer中，根據個人化電子郵件和片段的設定檔屬性和事件，使用條件規則來建立動態內容變體。
TQID: 'https://experienceleague.adobe.com/-zyX02yagsaPV4Oc-1JQWUzSUZWDLiyIiQCyyy0EDiE'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 46e599c6-e20f-5f67-9824-93415016f66b
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1081
ht-degree: 7%

---


# 條件式內容

條件內容可讓您根據條件規則調整電子郵件和片段內容。 這些規則是使用設定檔屬性或內容事件定義的。 您可以在規則產生器中建立條件式規則，並儲存這些規則以便在您的人員歷程中重複使用。

若要新增條件式內容至您的片段與電子郵件訊息，[!DNL Marketo Optimizer]可讓您套用儲存在&#x200B;_條件_&#x200B;資料庫中的條件式規則。 當您創作[電子郵件內容](./email-authoring.md)或[片段](./fragment-authoring.md)時，在視覺設計空間內套用條件規則。

## 新增條件式內容 {#add-conditional-content}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_conditional_content"
>title="條件式內容"
>abstract="使用條件式規則建立內容元件的多個變體。 如果傳送訊息時未符合任何條件，會顯示預設變體的內容。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_conditional_rule_select"
>title="條件式內容"
>abstract="使用儲存在資料庫中的條件式規則或建立新規則。"

當您在視覺化設計空間中撰寫[片段](./fragment-authoring.md)或[電子郵件](./email-authoring.md)時，請使用條件式規則來定義內容元件的多個變體。

1. 選取內容元件，然後按一下元件工具列中的&#x200B;**[!UICONTROL 啟用條件式內容]**&#x200B;圖示。

   請參閱[內容元件工具列](./content-components.md#content-component-toolbars)。

   元件外框顯示為橙色，表示元件已啟用為條件元件。 **[!UICONTROL 條件式內容]**&#x200B;窗格會以&#x200B;_預設變體_&#x200B;和&#x200B;_變體 — 1_&#x200B;顯示在左側。

   ![啟用文字元件的條件式內容](assets/conditions-enable.png){width="700" zoomable="yes"}

   您選取並啟動的原始內容為預設內容，且會在您定義的任何變體都不符合任何條件規則時套用。

   在此窗格中，您可以使用條件規則為所選內容元件定義多個變體。

1. 將游標停留在第一個變體（_變體 — 1_）上，然後按一下&#x200B;_選取條件_&#x200B;圖示（![條件圖示](../assets/do-not-localize/icon-select-condition.svg)）。

   ![選取變體](assets/conditions-variant-select.png){width="700" zoomable="yes"}的條件

   _[!UICONTROL 選取條件]_&#x200B;對話方塊會開啟並顯示條件程式庫。

   如果您想要檢視條件的詳細資訊，以確保它是您想要的，請按一下&#x200B;_更多功能表_&#x200B;圖示(**...**) 並選擇&#x200B;**[!UICONTROL 檢視資訊]**。

   ![條件資料庫存取條件詳細資料](assets/conditions-select-dialog.png){width="600" zoomable="yes"}

   若您需要的條件不存在，請按一下&#x200B;**[!UICONTROL 新建]**&#x200B;以建立條件規則[&#128279;](#create-conditional-rule)。

1. 選取條件式規則，然後按一下&#x200B;**[!UICONTROL 選取]**&#x200B;以將其與變體關聯。

<!-- 

   You can review the associated condition by clicking the _More menu_ icon (**...**) for the variant and choosing **[!UICONTROL View condition]**.

   ![View the condition associated with the variant](assets/conditions-variant-view-condition.png){width="600" zoomable="yes"}

   Click X at the top right to close the popup.

   ![View details for the associated condition](assets/conditions-info-popup.png){width="500"}

   -->

1. 若要提高可讀性，請按一下&#x200B;_更多功能表_&#x200B;圖示(**...**)來重新命名變體 ，並選擇&#x200B;**[!UICONTROL 重新命名]**。

   為變體輸入有意義的名稱，以協助您識別變體及其意圖。

   ![重新命名變體](assets/conditions-variant-rename.png){width="600" zoomable="yes"}

1. 在左側窗格中選取變體後，變更元件，以在條件為true時變更其在訊息中的顯示方式。

   在此範例中，文字元件的變體會根據收件者的地區使用不同的說明。

   ![變更變體的元件](assets/conditions-variant-component-edit.png){width="600" zoomable="yes"}

1. 如有需要，請按一下&#x200B;**[!UICONTROL 新增變體]**&#x200B;以定義另一個變體。

   重複步驟2至5以選取條件、重新命名變體並變更變體的元件。

   您可以視需要為內容元件新增任意數量的變體。 隨時變更左窗格中選取的變體，以檢查內容元件在條件中的顯示方式。

   >[!IMPORTANT]
   >
   >條件式內容會依照變體列出的順序，根據相關規則進行評估。 元件會使用第一個具有評估為true之條件的變體。
   >
   >如果在傳送訊息時，沒有已定義的變體條件評估為true，則內容元件會根據&#x200B;**[!UICONTROL 預設變體]**&#x200B;顯示。

1. 若要刪除變體，請按一下&#x200B;_更多功能表_&#x200B;圖示(**...**) 為變體選擇&#x200B;**[!UICONTROL 刪除]**。

   在確認對話方塊中按一下&#x200B;**[!UICONTROL 刪除]**。

## 條件式規則 {#conditional-rules}

條件規則是一組條件運算式，可評估為true或false。 使用這些規則來根據各種篩選器決定要在訊息中顯示的內容變體，例如設定檔屬性或內容相關事件。

規則儲存在條件資料庫中，可在電子郵件和組織的片段內容中重複使用。

<!--
M1.5 info -- out of date?

### Condition filters {#condition-filters}

| Condition type | Filters | Description |
| -------------- | ------- | ----------- |
| **Account** | Account Attributes | Attributes from the account profile, including: <li>Annual revenue</li><li>City</li><li>Country</li><li>Employee size</li><li>Industry</li><li>Name</li><li>SIC code</li><li>State</li> |
| | [!UICONTROL Special filters] > [!UICONTROL Has Buying Group] | The account does or does not have members of buying groups. The filter can also be evaluated against one or more of the following criteria: <li>Solution Interest</li><li>Buying Group status</li><li>Completeness Score</li><li>Engagement Score</li> |
| **Person** | [!UICONTROL Activity history] > [!UICONTROL Email] | Email activities associated with the journey: <li>[!UICONTROL Clicked link in email]</li><li>Opened Email</li><li>Was delivered email</li><li>Was sent email</li> These conditions are evaluated using a selected email message from earlier in the journey. |
| | [!UICONTROL Person Attributes] | Attributes from the person profile, including: <li>City</li><li>Country</li><li>Date of birth</li><li>Email address</li><li>Email invalid</li><li>Email suspended</li><li>First name</li><li>Inferred state region</li><li>Job title</li><li>Last name</li><li>Mobile phone number</li><li>Phone number</li><li>Postal code</li><li>State</li><li>Unsubscribed</li><li>Unsubscribed reason</li> |
| | [!UICONTROL Special filters] > [!UICONTROL Member of Buying Group] | The person is or is not a buying group member evaluated against one or more of the following criteria: <li>Solution Interest</li><li>Buying Group status</li><li>Completeness Score</li><li>Engagement Score</li><li>Is Removed</li><li>Role</li> |
-->

### 建立條件式規則 {#create-conditional-rule}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_conditions_rule_editor"
>title="建立條件"
>abstract="結合屬性和內容事件來建置規則，決定在電子郵件訊息中顯示哪些內容變體。"

當您選取元件變體的條件時，可從設計空間存取條件規則產生器。

1. 在&#x200B;_[!UICONTROL 選取條件]_&#x200B;對話方塊中，按一下&#x200B;**[!UICONTROL 新建]**。

   ![選擇要建立的條件型別](./assets/conditions-select-create-new.png){width="700" zoomable="yes"}

   此動作會開啟&#x200B;_[!UICONTROL 建立條件]_&#x200B;對話方塊。 使用對話方塊工具將屬性結合到畫布中（類似於Experience Platform中的區段建置體驗）。 篩選器屬性會組織為三個標籤：

   * **[!UICONTROL 設定檔]** - B2B設定檔XDM結構描述會列出與Adobe Experience Platform中定義的Experience Data Model (XDM)結構描述相關的所有設定檔屬性。

   * **[!UICONTROL 內容]** — 當您的訊息用於歷程時，內容歷程欄位可透過此索引標籤使用。

   * **[!UICONTROL 對象]** — 列出從Adobe Experience Platform Segmentation服務中建立的區段定義產生的所有對象。

   ![建立條件對話方塊](./assets/conditions-rule-create.png){width="700" zoomable="yes"}

1. 根據您的需求建置條件式規則。

   針對您要納入規則中的每個篩選器，將專案拖放至規則畫布上。 展開篩選器並完成運算式。

   ![完成運算式以評估](./assets/conditions-rule-add-attribute.png){width="700" zoomable="yes"}

   視需要拖放其他篩選器。

   如果包含多個篩選器，您可以根據套用篩選器的方式切換篩選器邏輯設定：

   * **[!UICONTROL And]** — 如果&#x200B;**所有**&#x200B;篩選器為true，則規則會評估為true。
   * **[!UICONTROL 或]** — 如果&#x200B;**任何**&#x200B;個篩選器為true，則規則會評估為true。

   ![在And和Or](./assets/conditions-rule-filter-logic.png){width="700" zoomable="yes"}之間切換邏輯設定

1. 按一下&#x200B;**[!UICONTROL 選取]**&#x200B;以使用條件的自訂規則。

   如果要讓規則可供重複使用，可將其新增至程式庫。

### 將條件新增至程式庫 {#add-to-library}

1. 在[建立條件]對話方塊中，按一下底部的[儲存條件] **&#x200B;**。

1. 在右側，輸入規則的&#x200B;**[!UICONTROL Name]** （必要）和&#x200B;**[!UICONTROL Description]** （選用）。

   使用有意義的名稱和有用的說明來協助組織中的其他人重複使用它，而非建立重複的條件。

   ![新增條件規則的名稱和描述](./assets/conditions-rule-name-description.png){width="700" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 新增]**。

   條件規則會儲存至程式庫，您可以為目前變體選取它。 它也包含在程式庫中，以便供跨人員歷程的任何其他動態內容變體使用。

>[!NOTE]
>
>您無法修改儲存至程式庫的條件式規則。 不過，您可以使用已儲存的規則來建立新規則。 若要這麼做，請開啟條件式規則，進行所需的變更，然後以新名稱將其儲存至程式庫。

<!--

### Duplicate a rule {#duplicate-rule}

Conditional rules saved to the library cannot be modified. However, you can duplicate an existing rule and change it to create a new rule.

1. Click the _More menu_ icon (**...**) for the variant and choose **[!UICONTROL Duplicate]**.

   A duplicate of the rule opens in the rule builder. Use the duplicate as a starting point for the rule that you want to build.

   ![Use a duplicate rule to create the one that you need](assets/conditions-rule-duplicate.png){width="600" zoomable="yes"}

1. In the rule builder, change, add, or delete conditions according to what you need.

1. Change the name and description to match the purpose or items in the rule.

1. When your conditional rule is complete, click **[!UICONTROL Save]**.
-->
