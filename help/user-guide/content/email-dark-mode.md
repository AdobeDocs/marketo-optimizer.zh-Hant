---
title: 電子郵件內容的深色模式
description: 瞭解Marketo Optimizer中的深色模式電子郵件設計。 在電子郵件使用者端之間預覽呈現、自訂設定和測試。
TQID: 'https://experienceleague.adobe.com/IFAOy7HJQ93uT4Mz70dC-RPHPaWhUhE9T0d5dEgJYgk'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
topic_v2: id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1476
ht-degree: 7%

---

# 電子郵件內容的深色模式 {#dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode"
>title="切換至深色模式"
>abstract="切換至深色模式，以預覽轉譯結果並定義自訂設定。 <br>轉譯結果取決於收件者的電子郵件用戶端。 並非所有電子郵件用戶端都支援自訂深色模式。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_preview"
>title="切換至深色模式"
>abstract="切換至深色模式，以預覽支援的電子郵件用戶端上的轉譯結果。 <br>最終的轉譯結果取決於收件者的電子郵件用戶端。 請注意，並非所有電子郵件用戶端都支援深色模式。"

_深色模式_&#x200B;可讓支援的電子郵件使用者端或應用程式針對文字、按鈕和其他視覺元素，顯示背景較暗且顏色較淺的電子郵件。 這種顯示器可減輕眼睛疲勞、節省電池壽命，並改善低光環境的可讀性，提供更舒適的觀賞體驗。 隨著主要作業系統和應用程式呈上升趨勢，這是現代電子郵件設計的重要考量，能確保內容清晰易懂，而且視覺上吸引所有使用者。

當您在[!DNL Marketo Optimizer]視覺化設計空間中[建立您的電子郵件內容](./email-authoring.md)時，您可以切換至&#x200B;_**[!UICONTROL 深色模式]**_&#x200B;檢視。 在此檢視中，您也可以定義特定的自訂設定，以便在啟用電子郵件使用者端的深色模式時支援這些使用者端。

## 電子郵件使用者端注意事項 {#email-client-considerations}

不同的電子郵件使用者端和應用程式套用深色模式的方式存在重大差異。 因此，請謹慎考量深色模式演算的期望。 在電子郵件設計空間中使用深色模式之前，請考慮以下電子郵件使用者端使用案例：

+++不支援深色模式的使用者端

有些電子郵件使用者端完全不支援此功能，例如：

* [!DNL Yahoo! Mail]
* [!DNL AOL]

如果您在電子郵件設計中定義深色模式自訂設定，這些電子郵件使用者端無法顯示任何深色模式呈現。

+++

+++使用者端套用自己的深色模式

有些電子郵件使用者端會系統地將其本身的預設深色模式套用至所有收到的電子郵件。 它們會根據其深色模式設定，自動調整顏色、背景、影像和其他元素，而外部設定是不可能的。 這些使用者端包括：

* Gmail （案頭網頁郵件、iOS、Android™、行動網頁郵件）
* Outlook Windows
* Outlook Windows Mail

在此情況下，使用者端深色模式設定會覆寫您在[!DNL Marketo Optimizer]中定義的自訂深色模式設定。

+++

+++支援自訂深色模式的使用者端

許多最熱門的電子郵件使用者端都支援使用`@media (prefers-color-scheme: dark)`查詢自訂深色模式呈現，這是[!DNL Marketo Optimizer]電子郵件樣式所使用的方法。 此使用者端清單包括：

* Apple Mail macOS
* Apple Mail iOS
* Outlook macOS
* Outlook.com
* Outlook iOS
* Outlook ™

在此情況下，將會轉譯您在[!DNL Marketo Optimizer]中定義的特定設定。 不過，某些限制可能會根據每個電子郵件使用者端而適用。 例如，如果電子郵件內容中出現影像，部分使用者端(例如Apple Mail 16 (macOS 13))就不會產生深色模式。

為了獲得最佳結果，請使用您定位的電子郵件使用者端測試您的內容。

+++

## 深色模式設計

[!DNL Marketo Optimizer]視覺化設計空間提供兩種工具，可在深色模式下設定電子郵件內容的樣式：

* 使用[預覽函式](#preview-dark-mode)檢閱大部分支援電子郵件使用者端的預設深色模式轉譯。

* 如果您要覆寫支援電子郵件使用者端的預設設定，請定義並套用[自訂深色模式設定](#custom-dark-mode)至您的電子郵件內容。

### 預覽預設深色模式 {#preview-dark-mode}

1. 在電子郵件設計空間中開啟電子郵件內容。

   在畫布的右上方，有一個淺色與深色選取器，可切換淺色（預設）與深色模式之間的內容顯示。

   ![電子郵件設計畫布在右上角顯示燈光模式選擇器](assets/email-color-mode-light-selector.png){width="700" zoomable="yes"}

1. 將選取器變更為&#x200B;_深色模式_ （ ![深色模式圖示](../assets/do-not-localize/icon-content-dark-mode.svg) ）。

   畫布會使用預設深色模式預覽來顯示內容。

   根據預設，深色模式預覽會將`full color invert`色彩配置套用至影像和圖示以外的所有元素。 此色彩配置會偵測包含明暗元素的區域，並加以反轉。 淺色背景變成深色，深色文字變成淺色，或深色背景變成淺色，淺色文字變成深色。

   ![電子郵件設計畫布顯示深色模式選擇器，電子郵件內容以深色模式顯示](assets/email-color-mode-dark-selector.png){width="700" zoomable="yes"}

>[!CAUTION]
>
>最終轉譯可能會因收件者的電子郵件使用者端而異。 若要檢視儘可能接近每個電子郵件使用者端最終結果的模擬，請使用電子郵件設計空間中&#x200B;**[!UICONTROL Simulate Content]**&#x200B;提供的Litmus電子郵件呈現整合。

### 定義自訂深色模式設定 {#custom-dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_image"
>title="將特定影像用於深色模式"
>abstract="為深色模式選取其他影像。 <br>新增特定影像並不能保證會在所有電子郵件用戶端中正確轉譯。 並非所有電子郵件用戶端都支援自訂深色模式。"

切換至深色模式後，您可以編輯內容的特定樣式元素，這些樣式元素僅在收件者的電子郵件使用者端中啟用深色模式（假設該模式支援該功能）時才會顯示。

>[!NOTE]
>
>深色模式的最終呈現取決於每個電子郵件使用者端，因此結果可能因人而異。 如需詳細資訊，請參閱[電子郵件使用者端考量事項](#email-client-considerations)。

自訂深色模式樣式會使用`@media (prefers-color-scheme: dark)` CSS查詢來偵測電子郵件使用者端是否已設為深色模式，並套用您定義的深色主題設計。

若要定義自訂深色模式設定(_T):_

1. 如有需要，請將選取器移至設計畫布右上角的&#x200B;_深色模式_ （ ![深色模式圖示](../assets/do-not-localize/icon-content-dark-mode.svg) ）。

1. 編輯任何樣式色彩屬性，例如文字、背景或按鈕。

![顯示顏色和字型選項的深色模式文字樣式設定面板](assets/email-color-mode-dark-text-settings.png){width="700" zoomable="yes"}

1. 針對影像和圖示，僅針對深色模式定義特定資產。

   您無法變更影像和圖示的顏色，但可以定義用於深色模式的替代資產。 您可以嘗試圖示的不同顏色組合，或調整像片影像的顏色和飽和度。

   ![不同顏色組合的圖示](../assets/do-not-localize/color-contrast-images-diagram.svg){width="80%"}

   選取任何影像，並使用&#x200B;**[!UICONTROL 設定]**&#x200B;窗格中的專用切換切換功能切換至&#x200B;**[!UICONTROL 深色模式]**。 然後，從Marketo Design Studio資產選取器中選取其他影像資產。

   請參閱[從Marketo Design Studio插入影像](./email-authoring.md#insert-image)，以取得選取影像資產的詳細資訊。

1. 在您的設計變更期間，隨時選取&#x200B;**[!UICONTROL 切換到即時檢視]**，以檢查您的內容在各種裝置大小上的呈現方式。

   從這個檢視，將選擇器變更為&#x200B;_深色模式_ （ ![深色模式圖示](../assets/do-not-localize/icon-content-dark-mode.svg) ），以預覽不同裝置上的深色模式內容版本。

   ![即時檢視面板，以深色模式顯示不同裝置大小的電子郵件內容](assets/email-color-mode-dark-live-view.png){width="800" zoomable="yes"}

   >[!CAUTION]
   >
   >即時檢視是通用的預覽，用來比較各種裝置大小下的轉譯效果。 最終呈現內容可能會因收件者的電子郵件使用者端而異。

1. 當您的深色模式變更完成時，請按一下&#x200B;**[!UICONTROL 模擬內容]**&#x200B;以使用預覽和校訂工具來測試您的電子郵件設計。

1. 如果您有Litmus Enterprise帳戶，請選取&#x200B;**[!UICONTROL 轉譯電子郵件]**，以檢視Litmus整合中各種電子郵件使用者端的最終深色模式轉譯。

   >[!CAUTION]
   >
   >雖然模擬非常接近電子郵件在深色模式中的顯示方式，但由於電子郵件服務提供者或裝置層級設定的差異，實際呈現可能會有所不同。

## 最佳實務 {#best-practices}

隨著主要電子郵件使用者端採用深色模式的人數增加，您必須考量您的電子郵件在明暗環境中呈現的方式，無論您是否使用[自訂深色模式](#custom-dark-mode)。

深色模式可以改變顏色、背景和影像 — 有時會覆寫設計選擇。 為確保視覺一致性、協助工具及品牌完整性，請遵循下列最佳實務：

| 實務 |            |
| -------- | ---------- |
| 最佳化您的影像和標誌 | 檢查清單：<ul><li>將圖志和圖示儲存為具有透明背景的PNG檔案，以避免在深色模式中看到白色方塊。 <li>避免使用硬式編碼白色或淺色背景的影像。 <li>如果無法使用透明度，請在設計中將影像置於純色背景上，以防止發生尷尬的顏色倒轉。 |
| 觀看您的背景 | 檢查清單：<ul><li>確保文字和背景顏色之間有足夠的對比，以便在淺色和深色模式中都能閱讀。 <li>避免僅依賴背景顏色處理重要內容。 有些使用者端會以深色模式覆寫背景顏色，因此請確定關鍵資訊仍然可見。 |
| 在深色模式中設計可存取的內容 | 檢查清單：<ul><li>使用顏色組合，可輕鬆區別色盲人士。 <li>使用中間調調色盤，確保與淺色和深色背景的對比。 <li>使用具有高對比度的無障礙色彩組合，以改善可讀性並符合[!DNL Web Content Accessibility Guidelines (WCAG)]標準。 使用[!DNL WebAIM Contrast Checker]之類的工具來驗證色彩對比。 <li>避免使用精簡字型，因為精簡字型會影響可讀性。 如果您的品牌需要細字型，請在深色模式中將其粗體。 <li>略過純黑色的純白色，這可能會導致眼睛疲勞，而且在某些電子郵件使用者端中可能會自動反轉。 <li>如果深色模式不受支援，請提供可存取的遞補樣式。 |
| 在深色模式環境中測試您的電子郵件 | 檢查清單：<ul><li>使用電子郵件設計空間中的[深色模式預覽](#preview-dark-mode)，它會使用反轉的色彩配置來提早發現問題。 <li>如果您有Litmus Enterprise帳戶，請使用&#x200B;**[!UICONTROL 轉譯電子郵件]**&#x200B;選項，在主要電子郵件使用者端（例如Apple Mail、Gmail和Outlook）上模擬您的設計，並檢視色彩和影像在深色模式下的行為。 |

