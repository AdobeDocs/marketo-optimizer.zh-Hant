---
title: 分割和合併路徑節點
description: 瞭解如何在個人歷程中使用分割和合併路徑節點，以根據定義的條件將人們分割為不同的路徑，然後在下游的共同點將其重新統一。
TQID: 'https://experienceleague.adobe.com/XMN7lgb77bFlJkNXrmPf9ZSCV-GgIuybtr-O3AsqT2U'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
    internal-label: Journeys
source-git-commit: 9d9f2ae1aafc5ffdc2bcc6546c7eb2ddcbaa4ab2
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 6%
---
# 分割和合併路徑節點

在個人歷程中使用分割和合併路徑節點，根據您定義的條件將人們分割為不同的路徑，然後合併這些路徑，以便歷程可以繼續。 分割路徑可讓您將動作和事件量身打造為適合特定對象區段，而合併路徑可在共同點組合這些區段。

## 分割路徑節點

使用分割節點，根據您定義的條件來劃分人員。 根據條件建立對象清單的路徑，使用區段的動作和事件節點定義每個路徑，然後組合路徑並繼續歷程。

「分割路徑」節點會根據人員篩選器定義一或多個分段路徑。

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->

_&#x200B;**分割路徑節點如何運作**&#x200B;_

* 每個路徑的評估方式都是從上到下。 如果人員符合第一個和第二個路徑，則他們只會沿著第一個路徑前進。
* 此節點支援&#x200B;_其他人_&#x200B;路徑的定義，您可以在此為不符合其中一個已定義區段/路徑的人員新增動作或事件。

### 相符的人員篩選器

對於您為節點定義的每個路徑，請使用下列篩選器型別，根據一或多個條件來比對人員。

| 篩選器 | 說明 |
| ------- | ----------- |
| 活動歷史記錄 | 根據使用一或多個選取專案評估之條件的活動 |
| Brand Concierge | 與[!DNL Brand Concierge]互動的潛在客戶活動。 |
| 公司屬性 | 公司/帳戶個人資料中的屬性，包括： <li>年收入 <li>公司名稱 <li>帳單國家/地區 <li>行業 <li>員工人數 <li>SIC 代碼 <li>狀態 |
| 意圖資料 | 根據與個人設定檔相關聯的意圖資料的屬性。 |
| 機會 | 以與個人設定檔相關聯之商機為基礎的屬性。 |
| 人員屬性 | B2B個人設定檔中的屬性，包括： <li>城市 <li>國家 <li>出生日期 <li>電子郵件地址 <li>電子郵件無效 <li>電子郵件中止 <li>名字 <li>推斷的州別區域<li>職稱 <li>姓氏 <li>手機號碼 <li>人員參與度分數 <li>電話號碼 <li>郵遞區號 <li>狀態 <li>已取消訂閱 <li>取消訂閱的原因 |
| 銷售應用程式 | 與[!DNL Sales Qualifier]或[!DNL Marketo Sales Insights]相關的潛在客戶活動。 |
| 特殊篩選條件 | 篩選不屬於預先定義類別的屬性，為自訂或其他篩選條件提供彈性。 |

>[!BEGINSHADEBOX]

條件篩選器&#x200B;**的**&#x200B;支援[!DNL Marketo Optimizer]活動

對於路徑條件，[!DNL Marketo Optimizer]支援來自作為資料來源連線的[!DNL Marketo Engage]執行個體的活動。

>[!NOTE]
>
>只能有一個[!DNL Marketo Engage]執行個體作為資料來源，而且是在布建[!DNL Marketo Optimizer]執行個體時預先設定的。

您可以建置有關下列[!DNL Marketo Engage]個活動的條件：

* [!UICONTROL 已填寫Marketo Engage表單] — 符合在其非過時活動記錄中任何時候已完成特定[!DNL Marketo Engage]表單的潛在客戶。
* [!UICONTROL 造訪的Marketo Engage網頁] — 比對已在您的網站或[!DNL Marketo Engage]登陸頁面上檢視特定URL的潛在客戶。 其運作方式直接透過安裝在網站上的Munchkin追蹤程式碼執行。
* [!UICONTROL 已點按Marketo Engage網頁上的連結] — 符合已點按追蹤頁面上特定連結或資產的潛在客戶。
* [!UICONTROL 已傳送Marketo Engage電子郵件] — 比對[!DNL Marketo Engage]嘗試傳送特定電子郵件的潛在客戶，說明硬退信或伺服器接受之前的部署動作。
* [!UICONTROL 已傳遞Marketo Engage電子郵件] — 符合其郵件伺服器(MX)向[!DNL Marketo Engage]傳送伺服器傳回成功回應（250 OK訊息）的潛在客戶。
* [!UICONTROL Marketo Engage電子郵件已跳出] — 符合在特定電子郵件傳送或時間範圍內遇到硬跳出（永久傳遞失敗）的潛在客戶。
* [!UICONTROL Marketo Engage電子郵件已退信] — 符合電子郵件發生暫時傳遞失敗（例如完整收件匣或離線伺服器）而非永久硬退信的潛在客戶。
* [!UICONTROL 已取消訂閱Marketo Engage電子郵件] — 符合選擇退出非營運行銷電子郵件的潛在客戶。 發生此情況時，[!DNL Marketo Engage]會自動將潛在客戶的`Unsubscribed`欄位值更新為`true`，從未來的標準電子郵件傳送中隱藏這些值。
* [!UICONTROL 已開啟Marketo Engage電子郵件] — 比對已開啟追蹤的[!DNL Marketo Engage]電子郵件的潛在客戶。
* [!UICONTROL 在Marketo Engage電子郵件中點選的連結] — 符合在[!DNL Marketo Engage]電子郵件中點選任何連結（或特定連結）的潛在客戶。

>[!ENDSHADEBOX]

### 新增分割路徑節點

1. 導覽至歷程畫布。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 分割路徑]**。

   ![按一下歷程路徑上的新增圖示](./assets/person-journey-canvas-add-node.png){width="200"}

1. 若要定義適用於&#x200B;_[!UICONTROL 路徑1]_&#x200B;的條件，請按一下&#x200B;**[!UICONTROL 套用條件]**。

1. 若要定義分割路徑，請在條件編輯器中新增一或多個篩選器。

   * 從左側導覽拖放任何人員篩選器，並完成相符定義。

   * 按一下&#x200B;**[!UICONTROL 新增限制]**，以針對您想要用來調整篩選比對的每個限制。

     ![分割路徑節點 — 路徑條件的相符人員篩選器](./assets/journey-node-split-conditions-people.png){width="700" zoomable="yes"}

   * 在上方套用&#x200B;**[!UICONTROL 篩選邏輯]**，以精簡條件。 您可以選擇符合所有條件或任一條件。

   * 按一下「**[!UICONTROL 完成]**」。

1. 若要新增更多路徑，請按一下[新增路徑] **&#x200B;**，並重複上述步驟以新增適用於路徑的條件。

   您也可以根據這些條件來標示每個路徑，或使用預設標籤。

1. 如有需要，請根據您想要分割的優先順序來重新排序路徑。

   路徑篩選是以由上到下的順序評估。 每個人都會沿著第一個符合的路徑前進。

   按一下每個路徑卡片右上角的向上和向下箭頭，將其在路徑清單中向上或向下移動。

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. 啟用&#x200B;**[!UICONTROL 其他人]**&#x200B;選項，為不符合所定義路徑的人新增預設路徑。

   未啟用此選項時，不符合已定義區段/路徑的訪客會經過分割，繼續歷程的下一個步驟。

為每個路徑定義條件後，您可以新增要套用至路徑上人員的動作或事件節點。

## 合併路徑節點

1. 導覽至歷程畫布，並找出具有兩個或多個路徑的分割路徑節點。

   每個路徑都應該有動作和事件節點的組合。

1. 按一下任一路徑結尾的加號( **+** )圖示，然後從顯示的選項中選擇&#x200B;**[!UICONTROL 合併路徑]**。

1. 在右側的節點屬性中，選取您要合併的路徑。

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   此時，路徑會合併，以便來自所選路徑的人合併成單一路徑，繼續完成歷程。

1. 如有需要，您可以導覽回合併路徑節點屬性，並清除您要移除之任何路徑的核取方塊，以取消合併路徑。