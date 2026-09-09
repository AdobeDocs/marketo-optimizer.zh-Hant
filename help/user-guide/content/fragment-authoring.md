---
title: 片段製作
description: 使用視覺化設計工具製作可重複使用的內容片段 — 在Marketo Optimizer中新增結構、資產、個人化、條件式內容以及電子郵件和範本的連結URL追蹤。
TQID: 'https://experienceleague.adobe.com/KbnYkUMVfjBv5ST55WwAqYiMDkynwSw4BKIP0bsE-DI'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 203
ht-degree: 3%

---

# 片段編寫

在您[建立片段](./fragments.md#create-fragments)後，請使用視覺設計空間來編寫片段中的結構和內容元件。

## 新增結構和內容 {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## 新增資產 {#add-assets}

在視覺化設計空間中，選取左側導覽列中的&#x200B;_Assets_ （![Assets圖示](../assets/do-not-localize/icon-assets-me.svg) ）圖示，以瀏覽並選取[!DNL Marketo Optimizer]資產庫中的影像資產。

如需選取、取代或上傳影像資產的步驟，請參閱[使用資產進行內容製作](./digital-asset-management.md#assets-authoring)。

## 導覽圖層、設定和樣式 {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## 將內容個人化 {#personalize-content}

[!DNL Marketo Optimizer]使用Handlebars語法進行個人化。 Token在傳送時會取代為每個收件者設定檔資料的值。

新增個人化&#x200B;:_(_T)

1. 選取文字元件，然後按一下工具列中的&#x200B;_新增個人化_ （![個人化圖示](../assets/do-not-localize/icon-personalize.svg) ）圖示。
1. 在個人化對話方塊中，瀏覽左側的架構樹並選取設定檔屬性。 編輯器會插入對應的Handlebars運算式，例如`{{profile.firstName}}`。
1. 如有需要，新增遞補值以處理遺漏的資料，例如`{{profile.firstName | default: "there"}}`。
1. 按一下&#x200B;**[!UICONTROL 確認]**&#x200B;或&#x200B;**[!UICONTROL 插入]**。 運算式會內嵌顯示於欄位中。

如需運算式編輯器工具和語法的詳細資訊，請參閱[Personalization編輯器](./personalization-expressions.md)。

## 編輯連結的URL追蹤 {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
