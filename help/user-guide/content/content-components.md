---
title: 內容元件
description: 在Marketo Optimizer中設計包含內容元件的電子郵件、登入頁面和片段 — 新增按鈕、文字、影像、表單和容器。
feature: Content Design Tools
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '2828'
ht-degree: 7%

---

# 內容元件 {#content-components}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_content_components_email"
>title="關於內容元件"
>abstract="內容元件是指設計電子郵件時可以使用的空白內容預留位置。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_content_components_landing_page"
>title="關於內容元件"
>abstract="內容元件是指設計登陸頁面時可以使用的空白內容預留位置。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_content_components_fragment"
>title="關於內容元件"
>abstract="內容元件是指設計片段時可以使用的空白內容預留位置。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_content_components_template"
>title="關於內容元件"
>abstract="內容元件是指設計範本時可以使用的空白內容預留位置。"

當您設計電子郵件、登入頁面、範本及視覺化片段的內容時，請使用[!UICONTROL 內容元件]來新增視覺化設計元素。

您可以視需要在定義配置的一或多個[結構元件](./structure-components.md)內新增任意數目的內容元件。

## 內容庫

元件庫的&#x200B;**[!UICONTROL 內容]**&#x200B;區段會顯示可用的內容元件：

| 圖示 | 元件 | 說明 |
| --------- | ---- | ----------- |
| ![容器圖示](../assets/do-not-localize/icon-content-component-container.svg) | [容器](#container) | 將此元件新增到您的設計，以包含可用來將元件分組或將背景或邊框樣式套用至區域的矩形容器。 |
| ![按鈕圖示](../assets/do-not-localize/icon-content-component-button.svg) | [按鈕](#button) | 將此元件新增至您的設計，以包含可點按的按鈕元素。 |
| ![文字圖示](../assets/do-not-localize/icon-content-component-text.svg) | [文字](#text) | 將此元件新增至您的設計，以包含文字內文。 |
| ![分隔線圖示](../assets/do-not-localize/icon-content-component-divider.svg) | [分隔線](#divider) | 將此元件新增到您的設計，加入水平線以分隔內容的區域。 |
| ![HTML圖示](../assets/do-not-localize/icon-content-component-html.svg) | [HTML](#html) | 將此元件新增至您的設計，以複製並貼上現有HTML的不同部分。 使用此元件來建立免費的模組化HTML區塊，以重複使用某些外部內容。 |
| ![影像圖示](../assets/do-not-localize/icon-content-component-image.svg) | [影像](#image) | 將此元件新增到您的設計以插入影像檔案。 |
| ![社交圖示](../assets/do-not-localize/icon-content-component-social.svg) | [社交](#social) | 將此元件新增到您的設計，以插入指向社群媒體頁面的連結。 |
| ![表單圖示](../assets/do-not-localize/icon-content-component-form.svg) | [表單](#form) | **_僅供登陸頁面使用。_** 將此元件新增到您的設計以插入建立的表單。 |

## 內容元件工具列

當您在畫布中選取工具列時，每個內容元件型別都會顯示工具列。 可用的工具會因元件型別而異，提供直接在演算內容中處理元件的簡單方法。 工具列包含適用於元件型別的格式化和功能功能。

![內容元件工具列](../assets/do-not-localize/toolbar-content.png){width="450"}

### 格式化工具

+++變更文字樣式

<table>
    <tr>
        <th style="width: 30%;">工具</th>
        <th style="width: 50%;">使用情況</th>
        <th style="width: 20%;">元件</th>
    </tr>
    <tr>
        <td><img width="120px" src="../assets/do-not-localize/toolbar-button-text-styles.png" alt="變更文字樣式工具"></td>
        <td>將粗體、斜體、底線或刪除線、上標或下標套用至選取的文字字串。</td>
        <td><li>按鈕 <li>文字</td>
    </tr>
</table>

+++

+++水準對齊方式

<table>
    <tr>
        <th style="width: 30%;">工具</th>
        <th style="width: 50%;">使用情況</th>
        <th style="width: 20%;">元件</th>
    </tr>
    <tr>
        <td><img width="120px" src="../assets/do-not-localize/toolbar-button-horizontal-alignment.png" alt="水準對齊工具"></td>
        <td>將水準對齊方式型別套用至元件內容。 選擇左、中、右或左右對齊。 </td>
        <td><li>按鈕 <li>文字</td>
    </tr>
</table>

+++

+++建立清單

<table>
    <tr>
        <th style="width: 30%;">工具</th>
        <th style="width: 50%;">使用情況</th>
        <th style="width: 20%;">元件</th>
    </tr>
    <tr>
        <td><img width="120px" src="../assets/do-not-localize/toolbar-button-create-list.png" alt="建立清單工具"></td>
        <td>將排序或無排序的清單格式套用至元件文字。</td>
        <td><li>文字</td>
    </tr>
</table>

+++

+++設定標題

<table>
    <tr>
        <th style="width: 20%;">工具</th>
        <th style="width: 60%;">使用情況</th>
        <th style="width: 20%;">元件</th>
    </tr>
    <tr>
        <td><img width="60px" src="../assets/do-not-localize/toolbar-button-set-heading.png" alt="設定標題工具"></td>
        <td>在游標位置的段落套用標題層級格式。</td>
        <td><li>按鈕 <li>文字</td>
    </tr>
</table>

+++

+++字型大小

<table>
    <tr>
        <th style="width: 20%;">工具</th>
        <th style="width: 60%;">使用情況</th>
        <th style="width: 20%;">元件</th>
    </tr>
    <tr>
        <td><img width="60px" src="../assets/do-not-localize/toolbar-button-font-size.png" alt="字型大小工具"></td>
        <td>將字型大小套用至選取的文字。 按一下工具並選擇大小或輸入畫素值。</td>
        <td><li>按鈕 <li>文字</td>
    </tr>
</table>

+++

+++字型顏色

<table>
    <tr>
        <th style="width: 40%;">工具</th>
        <th style="width: 40%;">使用情況</th>
        <th style="width: 20%;">元件</th>
    </tr>
    <tr>
        <td><img width="200px" src="../assets/do-not-localize/toolbar-button-font-color.png" alt="字型顏色工具"></td>
        <td>將字型顏色套用至選取的文字。 從選擇器中選擇顏色，並使用顏色滑桿和顏色欄位來選取顏色。 或者，您可以輸入已知的RGB、HSL、HSB或十六進位值。 </td>
        <td><li>按鈕 <li>文字</td>
    </tr>
</table>

+++

+++插入連結

<table>
    <tr>
        <th style="width: 40%;">工具</th>
        <th style="width: 40%;">使用情況</th>
        <th style="width: 20%;">元件</th>
    </tr>
    <tr>
        <td><img width="200px" src="../assets/do-not-localize/toolbar-button-insert-link.png" alt="插入連結工具"></td>
        <td>為選取的文字或元素建立可點按的連結。 <li>電子郵件內容 — 指定外部URL或登陸頁面。<li>登陸頁面內容 — 指定外部連結。</td>
        <td><li>按鈕 <li>文字 <li>影像 </td>
    </tr>
</table>

+++

+++移除連結

<table>
    <tr>
        <th style="width: 15%;">工具</th>
        <th style="width: 60%;">使用情況</th>
        <th style="width: 25%;">元件</th>
    </tr>
    <tr>
        <td><img width="80px" src="../assets/do-not-localize/toolbar-button-remove-link.png" alt="移除連結工具"></td>
        <td> 移除所選文字或元素的可點按連結。</td>
        <td><li>按鈕 <li>文字 <li>影像 </td>
    </tr>
</table>

+++

### 功能工具

| 工具 | 名稱 | 使用情況 |
| ---- | ---- | ----- |
| ![新增個人化](../assets/do-not-localize/toolbar-button-add-personalization.png){width="40"} | 新增個人化 | 使用個人化編輯器在元件內容中插入個人化代號。 [了解更多](./email-authoring.md#personalize-content) |
| ![顯示原始程式碼](../assets/do-not-localize/toolbar-button-show-source-code.png){width="40"} | 顯示原始程式碼 | 以唯讀快顯視窗顯示元件的HTML原始碼。 <br/>![顯示HTML程式碼](assets/content-components-show-source-code.png){width="200"} |
| ![啟用條件式內容](../assets/do-not-localize/toolbar-button-enable-conditional-content.png){width="40"} | 啟用條件式內容 | （電子郵件和片段）啟用元件的條件變體。 |
| ![複製](../assets/do-not-localize/toolbar-button-duplicate.png){width="40"} | 重複 | 建立元件的復本，並直接將其新增到下方。 |
| ![刪除](../assets/do-not-localize/toolbar-button-delete.png){width="40"} | 刪除 | 移除元件。 |

## 將內容元件新增至您的設計

1. 在視覺設計空間中，使用現有範本或將所需的結構元件新增至空白畫布以定義版面。

1. 在&#x200B;**[!UICONTROL 元件]**&#x200B;資料庫中，抓取您所選內容元件的&#x200B;_拖曳控點_ ![拖曳控點](../assets/do-not-localize/icon-drag-handle.svg)，然後將其拖放到結構元件上。

   您可以將多個元件新增到單一結構元件和結構元件的每個欄中。

   ![將內容元件拖曳至結構元件](assets/content-components-drag.png){width="600" zoomable="yes"}

1. 使用右側的&#x200B;**[!UICONTROL 設定]**&#x200B;和&#x200B;**[!UICONTROL 樣式]**&#x200B;標籤，或畫布中顯示的內容工具列，調整元件顯示。

   例如，您可以變更元件的文字樣式、邊框間距或邊界。

   ![定義內容元件的設定和樣式](assets/content-components-settings-styles.png){width="600" zoomable="yes"}

使用設計時，您也可以使用[功能工具](#functional-tools)區段中的&#x200B;**刪除**&#x200B;和&#x200B;**複製**&#x200B;工具，移除或複製元件。

## 內容元件設定和樣式

新增元件後，會在視覺設計空間選取元件，其屬性會顯示在右側面板中。 您也可以隨時選取元件以變更設定和樣式。 許多設定和樣式都是元件專屬的，但有一些標準設定和樣式可套用至任何選取的內容元件。

### 顯示選項

若要從案頭或行動裝置顯示中排除元件，請變更&#x200B;**[!UICONTROL 顯示選項]**&#x200B;設定。 預設值&#x200B;_[!UICONTROL 在所有裝置上顯示]_，可跨所有裝置顯示。 選擇其他設定以依裝置型別排除元件：

* _[!UICONTROL 僅在桌上型裝置上顯示]_ — 當您想要在桌上型裝置上顯示元件，並將它排除在行動裝置上時，請選擇此設定。
* _[!UICONTROL 僅在行動裝置上顯示]_ — 當您想要在行動裝置（例如手機和平板電腦）上顯示元件時，請選擇此設定，並將它排除在桌上型裝置之外。

![內容元件的顯示選項](assets/content-components-display-options.png){width="400" zoomable="yes"}

### 容器 {#container}

使用容器將特定樣式套用至一組內容元件。 新增[!UICONTROL Container]元件，然後在其中新增其他內容元件。 此元件類似於您在HTML中使用`div`元素的方式。 您可以將不同的樣式套用至容器，使其與套用至其所包含內容元件的樣式不同。

例如，新增&#x200B;_[!UICONTROL 容器]_&#x200B;元件，然後在該容器內部新增&#x200B;_[!UICONTROL 按鈕]_&#x200B;元件。 您可以使用容器的特定區域樣式，並視需要設定按鈕及其背景的樣式。

![容器內容元件樣式](assets/content-components-container.png){width="600" zoomable="yes"}

+++背景

{{styles-background}}

+++

+++邊框

{{styles-border}}

+++

+++大小

{{styles-size}}

+++

+++邊距

{{styles-margin}}

+++

+++內距

{{styles-padding}}

+++

### 按鈕 {#button}

使用[!UICONTROL Button]元件將一或多個可點按的按鈕插入您的內容。 使用按鈕將頁面檢視器或電子郵件收件者重新導向至支援內容（已發佈的登陸頁面或外部連結）。

#### 新增按鈕文字

當畫布中顯示按鈕元件時，工具列會包含文字格式設定選項，以及個人化和條件變體。 如需有關編輯器工具列選項的詳細資訊，請參閱[內容元件工具列](#content-component-toolbars)。

當您輸入按鈕標籤文字並設定格式時，按鈕會調整大小以符合內容。

與工具列](assets/content-components-button.png){width="500" zoomable="yes"}一起顯示的![按鈕元件

#### 設定連結選項 {#button-set-link-options}

在&#x200B;_[!UICONTROL 設定]_&#x200B;索引標籤上，使用&#x200B;**[!UICONTROL 連結]**&#x200B;選項來定義按鈕文字、連結目的地，以及載入目標頁面的瀏覽器行為。

1. 設定連結的&#x200B;**[!UICONTROL 型別]**：

   * **[!UICONTROL 外部連結]** — 選擇此型別以使用標準URL作為連結目的地。

     在&#x200B;**[!UICONTROL Url]**&#x200B;中，輸入連結目的地的URL。 按一下「_個人化_」（「![個人化圖示](../assets/do-not-localize/icon-personalize.svg)」）圖示，使用個人化權杖作為URL中的引數。

     ![定義按鈕元件的外部連結](assets/component-button-link-options-external.png){width="200"}

   * **登陸頁面** — 選擇此型別，在<!-- Journey Optimizer B2B Edition (_Beta_) or -->連線的Marketo Engage執行個體中選取已發佈的登陸頁面。

     針對&#x200B;**[!UICONTROL 登陸頁面]**&#x200B;選項，請選取已發佈的登陸頁面。 按一下&#x200B;_選取頁面_&#x200B;圖示（![顯示連結圖示](../assets/do-not-localize/icon-landing-page-select.svg)）和[選取已發佈的登陸頁面](./landing-pages.md#link-to-landing-page)。

     ![定義按鈕元件登入頁面的連結](assets/component-button-link-options-landing-page.png){width="200"}

1. 針對&#x200B;**[!UICONTROL 標籤]**，請輸入您要在按鈕內顯示的文字。

   按鈕大小會根據您設定的文字和樣式進行調整。

1. 針對&#x200B;**[!UICONTROL Target]**，請選擇如何從電子郵件或頁面重新導向連結的目的地：

   * _[!UICONTROL 無]_ — 使用預設瀏覽器或使用者端行為（預設）開啟連結。
   * _[!UICONTROL 空白]_ — 在新視窗或索引標籤中開啟連結。
   * _[!UICONTROL Self]_ — 在相同框架中開啟連結。
   * _[!UICONTROL 父系]_ — 在父框架中開啟連結。
   * _[!UICONTROL Top]_ — 在視窗的整個內文中開啟連結。

#### 設定樣式

在&#x200B;**[!UICONTROL 樣式]**&#x200B;索引標籤中自訂按鈕樣式。

+++背景

{{styles-background}}

+++

+++文字

{{styles-text}}

+++

+++邊框

{{styles-border}}

+++

+++大小

{{styles-size}}

+++

+++對齊方式

{{styles-alignment-h-v}}

+++

+++按鈕邊界

{{styles-margin}}

+++

+++容器邊界

{{styles-margin}}

+++

+++內距

{{styles-padding}}

+++

+++進階

{{styles-advanced}}

+++

### 文字 {#text}

使用文字元件，將文字區塊插入內容中。 在畫布中選取文字元件時，輸入文字並使用工具列選項來新增內嵌格式和選項，包括個人化代號和條件變體。

在&#x200B;**[!UICONTROL 樣式]**&#x200B;索引標籤中自訂文字元件樣式。

+++背景

{{styles-background}}

+++

+++文字

這些樣式會套用至整個文字區塊。 您可以將內嵌樣式套用至選取的文字字串。

{{styles-text}}

+++

+++邊框

{{styles-border}}

+++

+++大小

{{styles-size}}

+++

+++邊距

{{styles-margin}}

+++

+++內距

{{styles-padding}}

+++

+++進階

{{styles-advanced}}

+++

### 分隔線 {#divider}

新增&#x200B;_分隔線_&#x200B;元件，在內容區段之間納入線性分隔。

+++背景

{{styles-background}}

+++

+++折線圖

在已選取&#x200B;_[!UICONTROL 樣式]_&#x200B;標籤的右側面板上，展開&#x200B;**[!UICONTROL 行]**&#x200B;區段並設定元件高度和寬度的選項：

* **[!UICONTROL 色彩]** — 按一下色彩方塊，從選擇器中選擇色彩。 您可以輸入已知的RGB、HSL、HSB或十六進位值來選擇顏色。 或者，您可以使用顏色滑桿和顏色欄位來選取顏色。

* **[!UICONTROL 高度]** — 按一下向上和向下箭頭圖示，以增加或減少畫素數量。 空白值(Auto)是預設值，會根據元素的內容調整元素的高度。

* **[!UICONTROL 寬度]** — 使用切換功能以畫素或百分比設定寬度。

  * 若為百分比寬度，請使用滑桿來設定百分比值。 百分比會根據包含區塊的內容方塊來決定元素大小，其中不包含邊框間距和邊框。 例如，值50會將元素寬度設定為其所包含區塊內容寬度的50%。

  ![定義分隔線元件](assets/component-divider-line-options.png){width="250"}的線條樣式

  * 針對以畫素為基礎的寬度，按一下向上和向下箭頭圖示，以增加或減少畫素數量。 空白值(Auto)是預設值，會根據元素內容調整元素寬度。

* **[!UICONTROL 樣式]** — 從標準CSS `line-style`值清單中選擇一個值，例如&#x200B;_實線_、_點線_&#x200B;和&#x200B;_虛線_。

+++

+++大小

{{styles-size}}

+++

+++對齊方式

{{styles-alignment-h}}

+++

+++邊距

{{styles-margin}}

+++

+++內距

{{styles-padding}}

+++

+++進階

{{styles-advanced}}

+++

### HTML {#html}

使用HTML元件來新增部分現有HTML。 此元件可讓您輕鬆建立重複使用外部內容的模組化HTML元素。

1. 在畫布上選取元件，然後按一下工具列中的「_顯示原始程式碼_」圖示。

   ![開啟程式碼編輯器以新增HTML](assets/content-components-html-show-code.png){width="450"}

1. 在文字方塊中貼上HTML，然後按一下[儲存]。****

   ![編輯HTML對話方塊](assets/content-components-html-edit-dialog.png){width="600" zoomable="yes"}

   如果HTML有效，它會在畫布上呈現元素。 如果是對映至其他內容元件的元素，您可以根據元件型別變更右側面板中的設定和樣式。 如果不適用，則會保留為HTML元件。

對於HTML元件，您可以在右側面板中為整個HTML元件設定下列樣式：

+++背景

{{styles-background}}

+++

+++邊框

{{styles-border}}

+++

+++大小

{{styles-size}}

+++

+++對齊方式

{{styles-alignment-h-v}}

+++

+++邊距

{{styles-margin}}

+++

+++內距

{{styles-padding}}

+++

+++進階

{{styles-advanced}}

+++

### 影像 {#image}

使用[!UICONTROL 影像]元件將影像資產插入您的內容。 在畫布中選取&#x200B;_影像_&#x200B;元件時，您可以新增或變更顯示的影像資產檔案。

![與工具列一起顯示的影像元件](assets/content-components-image.png){width="400" zoomable="yes"}

#### 新增影像資產 {#add-image-asset}

選擇要新增影像資產的方法：

* **[!UICONTROL 選取資產]** — 選擇此型別以瀏覽並從[!DNL Marketo Optimizer] Assets資料庫中選取影像資產。

  ![瀏覽可用的影像資產](./assets/dam-assets-internal-image-selected.png){width="700" zoomable="yes"}

  從對話方塊中，您可以從選取的存放庫中選擇影像。 按一下&#x200B;**[!UICONTROL 選取]**&#x200B;以新增資產。

  有多種工具可協助您找到所需的資產：

  * 按一下左上方的&#x200B;_篩選器_&#x200B;圖示，以根據您的條件篩選顯示的專案。

  * 在&#x200B;_搜尋_&#x200B;欄位中輸入文字，以篩選顯示的專案以符合資產名稱。

* **[!UICONTROL 匯入媒體]** — 選擇此型別以從您的系統選取檔案，並將其匯入[!DNL Marketo Optimizer]資產庫。

  在&#x200B;_[!UICONTROL 上傳影像]_&#x200B;對話方塊中，將檔案從您的系統拖放至檔案方塊。 檔案大小上限為100 MB。

  ![將影像檔案匯入資產庫](assets/email-designer-image-upload.png){width="450"}

  所選影像的檔案名稱會顯示在對話方塊中。 資產檔案名稱必須是唯一的（跨資料夾），如果已存在同名的檔案，則會顯示訊息。 名稱最多可包含100個字元，且不能包含特殊字元（例如`;`、`:`、`\`和`|`）。

  按一下&#x200B;**[!UICONTROL 匯入]**。

您可以在右側面板中為影像新增影像標題和替代文字。

![影像設定](./assets/dam-assets-image-settings.png){width="250"}

#### 設定連結選項 {#image-set-link-options}

在&#x200B;_[!UICONTROL 設定]_&#x200B;索引標籤上，使用&#x200B;**[!UICONTROL 連結]**&#x200B;選項將影像與載入目標頁面的目的地和瀏覽器行為連結。

1. 設定連結的&#x200B;**[!UICONTROL 型別]**：

   * **[!UICONTROL 外部連結]** — 選擇此型別以使用標準URL作為連結目的地。

     在&#x200B;**[!UICONTROL Url]**&#x200B;中，輸入連結目的地的URL。 按一下「_個人化_」（「![個人化圖示](../assets/do-not-localize/icon-personalize.svg)」）圖示，使用個人化權杖作為URL中的引數。

     ![定義影像元件的外部連結](assets/component-button-link-options-external.png){width="250"}

   * **登陸頁面** — 選擇此型別，在<!-- Journey Optimizer B2B Edition (_Beta_) or -->連線的Marketo Engage執行個體中選取已發佈的登陸頁面。

     針對&#x200B;**[!UICONTROL 登陸頁面]**&#x200B;選項，請選取已發佈的登陸頁面。 按一下&#x200B;_選取頁面_&#x200B;圖示（![顯示連結圖示](../assets/do-not-localize/icon-landing-page-select.svg)）和[選取已發佈的登陸頁面](./landing-pages.md#link-to-landing-page)。

     ![定義影像元件登入頁面的連結](assets/component-button-link-options-landing-page.png){width="250"}

1. 針對&#x200B;**[!UICONTROL 標籤]**，選擇性地為影像連結輸入描述文字。

1. 針對&#x200B;**[!UICONTROL Target]**，請選擇如何從電子郵件或頁面重新導向連結的目的地：

   * _[!UICONTROL 無]_ — 使用預設瀏覽器或使用者端行為（預設）開啟連結。
   * _[!UICONTROL 空白]_ — 在新視窗或索引標籤中開啟連結。
   * _[!UICONTROL Self]_ — 在相同框架中開啟連結。
   * _[!UICONTROL 父系]_ — 在父框架中開啟連結。
   * _[!UICONTROL Top]_ — 在視窗的整個內文中開啟連結。

#### 設定樣式

在右側面板中設定影像元件的樣式。

+++背景

{{styles-background}}

+++

+++邊框

{{styles-border}}

+++

+++大小

{{styles-size}}

+++

+++對齊方式

{{styles-alignment-h}}

+++

+++邊距

{{styles-margin}}

+++

+++內距

{{styles-padding}}

+++

+++進階

{{styles-advanced}}

+++

### 社交 {#social}

使用&#x200B;_社交_&#x200B;元件，將社群媒體頁面的連結插入您的內容中。 其中包含三種預設的社群媒體型別，但您可以視需求新增或移除這些型別。

![具有預設型別的新社交元件](./assets/content-components-social-settings.png){width="600" zoomable="yes"}

* 若要新增社群媒體型別，請按一下&#x200B;_新增_ ( **+** )圖示，然後選擇要新增的社群媒體型別。

  ![按一下+以新增社群媒體型別](./assets/content-components-social-settings-add-type.png){width="250"}

* 若要移除社群媒體型別，請按一下社群媒體圖示旁的&#x200B;**X**。

展開每個社群媒體型別的卡片以設定選項：

* **[!UICONTROL URL]** — 輸入您要連結至社群媒體圖形或圖示的社群媒體URL。
* **[!UICONTROL Source]** — 如果您想使用自己的影像，而不是預設影像，請選擇影像資產。 您可以從Assets資料庫中選取影像，或從系統匯入影像檔案。 如需選取和匯入影像資產的詳細資訊，請參閱[影像元件資訊](#add-the-image-asset)。
* **[!UICONTROL 替代文字]** — 為顯示的影像輸入替代文字。

![擴充的社群媒體型別設定](./assets/content-components-social-settings-for-type.png){width="250"}

若要定義所有社群媒體圖形的一致顯示大小，請設定&#x200B;**[!UICONTROL 影像大小]**。

您可以為&#x200B;_Social_&#x200B;元件設定下列樣式選項：

+++背景

{{styles-background}}

+++

+++邊框

{{styles-border}}

+++

+++大小

{{styles-size}}

+++

+++對齊方式

{{styles-alignment-h}}

+++

+++邊距

{{styles-margin}}

+++

+++內距

{{styles-padding}}

+++

+++進階

{{styles-advanced}}

+++

### 表單（僅限登陸頁面） {#form}

使用&#x200B;_表單_&#x200B;元件，將已發佈的表單新增至登入頁面或登入頁面範本。 如需建立和發佈表單的詳細資訊，請參閱[Forms](./forms.md)。

1. 按一下元件工具列中的&#x200B;_表單_&#x200B;工具，或使用右側的&#x200B;**[!UICONTROL 內嵌表單]**&#x200B;屬性來選取已發佈的表單。

   ![選取已發佈的表單](assets/content-design-add-form-properties.png){width="600"}

1. 如果您要覆寫表單的預設&#x200B;**[!UICONTROL 後續追蹤型別]**，請根據您的頁面或範本需求變更設定。

   此頁面也稱為表單的&#x200B;_感謝頁面_，此設定會決定訪客提交表單時會發生什麼情況：

   * **[!UICONTROL 停留在頁面]** — 選擇此選項可在提交表單時讓訪客停留在相同頁面。

   * **[!UICONTROL 登陸頁面]** — 選擇此選項可選取任何[!DNL Marketo Optimizer]或Marketo Engage登陸頁面作為後續追蹤。

   * **[!UICONTROL 外部URL]** — 選擇此選項可指定任何URL作為後續頁面。 訪客提交表單後，瀏覽器會載入指定的URL。

     >[!TIP]
     >
     >如果您想要使用表單下載檔案，您可以指定託管檔案的URL。 透過此設定，提交按鈕可作為下載按鈕運作。

     ![變更後續追蹤設定](assets/content-design-add-form-follow-up.png){width="280"}

如有需要，請選取右側面板中的&#x200B;**[!UICONTROL 樣式]**&#x200B;索引標籤，以設定結構元件內的表單邊界。

{{styles-margin}}
