---
title: 登陸頁面設計
description: 使用視覺化工具設計登入頁面 — 為Marketo Optimizer中的個人歷程新增內容元件、表單、自訂CSS、個人化和裝置預覽。
feature: Landing Pages, Content Design Tools
role: User
TQID: 'https://experienceleague.adobe.com/zb7rXCj7iWnk8Src1sWLZaYgRa35GjqGxXXu0pTJ-ds'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 556
ht-degree: 2%

---

# 登陸頁面設計

在您[建立登入頁面](./landing-pages-create-publish.md#create-landing-page)之後，請使用視覺設計空間來編寫頁面中的結構和內容元件。

## 新增結構和內容 {#structure-content-landing-page}

{{$include /help/_includes/content-design-components-prime.md}}

### 新增自訂 CSS {#add-custom-css}

您可以直接在登入頁面設計空間內新增自己的自訂CSS。 使用自訂CSS套用進階和特定的樣式，以擁有更大的彈性並控制內容的外觀。 最佳實務是在加入影像、按鈕和文字等元件前，先新增此最高層級的樣式。

如果畫布中至少有一個內容元件，請在左側導覽樹狀結構中選取&#x200B;**[!UICONTROL Body]**&#x200B;元件，以存取自訂CSS編輯器。

![存取內文樣式](assets/landing-page-body-styles-css.png){width="800" zoomable="yes"}

如需步驟、語法規則和疑難排解，請參閱[為您的內容新增自訂CSS](./design-custom-css.md)。

### 新增資產 {#add-assets}

在視覺化設計空間中，選取左側導覽列中的&#x200B;_Assets_ （![Assets圖示](../assets/do-not-localize/icon-assets-me.svg) ）圖示，以瀏覽並選取[!DNL Marketo Optimizer]資產庫中的影像資產。

如需選取、取代或上傳影像資產的步驟，請參閱[使用資產進行內容製作](./digital-asset-management.md#assets-authoring)。

### 新增表單 {#add-forms}

{{$include /help/_includes/content-design-add-forms.md}}

### 導覽圖層、設定和樣式 {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

### 將內容個人化 {#personalize-content}

[!DNL Marketo Optimizer]使用Handlebars語法進行個人化。 檢視登入頁面時，Token會取代為每個訪客的個人資料值。

新增個人化&#x200B;:_(_T)

1. 選取文字元件，然後按一下工具列中的&#x200B;_新增個人化_ （![個人化圖示](../assets/do-not-localize/icon-personalize.svg) ）圖示。
1. 在個人化對話方塊中，瀏覽左側的架構樹並選取屬性。 編輯器會插入對應的Handlebars運算式。
1. 如有需要，可新增遞補值以處理遺失的資料。
1. 按一下&#x200B;**[!UICONTROL 確認]**&#x200B;或&#x200B;**[!UICONTROL 插入]**。 運算式會內嵌顯示於欄位中。

如需運算式編輯器工具和語法的詳細資訊，請參閱[Personalization編輯器](./personalization-expressions.md)。

### 編輯連結的URL追蹤 {#linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}

![按一下「編輯」圖示以存取連結追蹤](assets/landing-page-link-tracking.png){width="400"}

使用&#x200B;**[!UICONTROL 追蹤型別]**&#x200B;控制連結的追蹤：

* **[!UICONTROL 已追蹤]** — 啟用連結URL上的追蹤。
* **[!UICONTROL Never]** — 從未啟用連結URL的追蹤。

### 儲存您的工作 {#save-your-work}

隨時按一下「儲存」****&#x200B;以儲存草稿登陸頁面。

您可以繼續編輯草稿頁面。 當您準備好顯示頁面，並可在電子郵件或簡訊訊息中供連結使用時，即可發佈頁面。

### 檢視選項 {#view-options}

善用視覺化設計空間中可用的檢視和內容驗證選項。

* 透過預設縮放選項放大/縮小內容。

* 切換在案頭、行動裝置或純文字/純文字間檢視內容。
  * 按一下&#x200B;_檢視_&#x200B;圖示，即可跨裝置預覽內容。
  * 選取其中一個現成可用的裝置，或輸入自訂維度以預覽內容。

### 更多選項 {#more-options}

從視覺設計空間頂端的&#x200B;_[!UICONTROL 更多……]_&#x200B;功能表，您可以執行下列動作：

![按一下[更多]以存取登入頁面動作](assets/landing-page-designer-more-menu.png){width="500"}

* **[!UICONTROL 重設登陸頁面]** — 按一下此選項，將視覺化設計畫布清除為空白並重新啟動建立頁面內容。
* **[!UICONTROL 變更您的設計]** — 返回&#x200B;_[!UICONTROL 建立您的主要登陸頁面]_&#x200B;首頁。 從那裡，您可以選擇另一個範本以重新啟動設計程式，或選擇在空白畫布中從頭開始設計頁面。
* **[!UICONTROL 匯出HTML]** — 將視覺畫布中的內容以HTML格式下載到您的本機系統，並封裝成zip檔。
