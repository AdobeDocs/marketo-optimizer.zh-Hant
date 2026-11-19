---
title: 內容模組
description: 瞭解如何新增及自訂電子郵件、登入頁面、視覺化片段和電子郵件範本的模組。 使用準備好的版面來建置一致的內容設計。
feature: Content Design Tools
role: User
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
source-git-commit: 73e54767086a103c11dce78a0295ad435c07f2c0
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 0%
---
# 內容模組

使用[!DNL Adobe Marketo Optimizer]中的模組，從準備好的版面組合內容。 每個模組都結合了[結構](./structure-components.md)和[內容元件](./content-components.md)以及您用自己的文字、影像和連結取代的預設內容。

不同於個別內容元件，模組會提供完整的區段，例如標題、橫幅、卡片和頁尾。 將模組新增到畫布，然後自訂其元件，而不是從空白空間建立每個區段。

模組與[視覺化片段](./fragments.md)不同。 模組會成為您設計內容的一部分。 視覺片段是已儲存的內容資產，您可以在電子郵件和電子郵件範本中重複使用。

## 「模組」標籤

針對下列任何內容型別，使用視覺化設計空間中的&#x200B;**[!UICONTROL 模組]**&#x200B;標籤：

* 電子郵件 — 請參閱&#x200B;[_電子郵件內容製作_](./email-authoring.md)。
* 登陸頁面 — 請參閱&#x200B;[_登陸頁面設計_](./landing-page-design.md)。
* 視覺片段 — 請參閱&#x200B;[_片段製作_](./fragment-authoring.md)。
* 電子郵件範本 — 請參閱&#x200B;[_建立電子郵件範本_](./templates-create.md#build-new)。

在視覺化設計畫布旁邊顯示的![模組類別](../../assets/modules-left-panel.png){width="600" zoomable="yes"}

## 模組類別

展開類別以選擇版面。 這些版面配置提供區段內容的不同排列，例如一、二或三欄。

| 類別 | 使用 |
| --- | --- |
| [!UICONTROL 標頭] | 使用標誌、導覽連結和介紹文字來介紹您的內容。 |
| [!UICONTROL 英雄] | 以橫幅區段反白標示公告或促銷活動。 |
| [!UICONTROL 表揚] | 在樣式的區段中呈現客戶報價。 |
| [!UICONTROL 卡片] | 在格線中排列產品、文章或其他內容專案。 |
| [!UICONTROL 團隊] | 向團隊成員、作者或演講者介紹像片、姓名和角色。 |
| [!UICONTROL 頁尾] | 使用導覽連結、社交連結和法律文字完成您的內容。 |

## 新增和自訂模組

從符合您要建立之區段的模組開始，然後調整其內容和樣式。 將預設連結和文字取代為您的頻道適用的內容。

>[!NOTE]
>
>對於行銷電子郵件，請在發佈電子郵件之前加入選擇退出連結並[檢查電子郵件警示](../marketing/email-channel.md#alerts)。

1. 在視覺化設計空間開啟您的電子郵件、登入頁面、視覺化片段或電子郵件範本。

   在畫布的左側，預設會顯示&#x200B;**[!UICONTROL 模組]**&#x200B;標籤。

1. 若要檢閱可用的版面，請展開類別。

   您也可以使用搜尋欄位，依名稱尋找模組。

1. 將模組拖曳至畫布上。

   ![模組清單會依搜尋篩選，並將模組拖曳到畫布上。](../../assets/modules-search-drag.png){width="600" zoomable="yes"}

1. 檢閱模組內的元素。

   每個模組都包含您可編輯的預設內容。 按一下畫布左側的&#x200B;_導覽樹狀結構_&#x200B;圖示（![導覽樹狀結構圖示](../assets/do-not-localize/icon-navigation-tree.svg)）以顯示模組中的結構和元素。

   ![導覽樹狀結構會顯示所選模組的結構和元素。](./assets/modules-navigation-tree.png){width="600" zoomable="yes"}

1. Select是模組中的一個元素，用於自訂。

   您可以取代預設文字、從資產選擇影像，以及更新內容的連結。

   使用&#x200B;**[!UICONTROL 設定]**&#x200B;和&#x200B;**[!UICONTROL 樣式]**&#x200B;索引標籤來調整選取的元件。

   ![模組中所選的文字元件，已顯示[樣式]選項](../../assets/modules-select-element-styles.png){width="600" zoomable="yes"}

1. 若要新增其他元素，請選取&#x200B;**[!UICONTROL 元件]**&#x200B;索引標籤，並將[內容元件](./content-components.md)拖曳到模組中。

   如果您將元件新增至模組結構，依預設會繼承模組樣式。 視需要調整其樣式。

   ![拖曳至模組結構的文字元件，顯示格式化的預留位置文字](./assets/modules-select-element-add-component.png){width="800" zoomable="yes"}

1. 選取&#x200B;**[!UICONTROL 儲存]**&#x200B;以儲存您的變更。

>[!NOTE]
>
>將品牌主題套用至電子郵件內容時，模組會繼承其樣式。 當您[從草稿開始設計電子郵件](./email-authoring.md#design-from-scratch)時，請選擇樣式模式。

## 重複使用自訂模組內容

若要建置可重複使用的模組內容，請[建立視覺化片段](./fragments.md#create-fragments)，並在片段設計空間中新增和自訂模組。 儲存並發佈片段，以便用於電子郵件和電子郵件範本。

然後[將片段](./fragments.md#add-to-content)插入其他電子郵件或電子郵件範本。
