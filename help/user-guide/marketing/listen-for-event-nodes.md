---
title: 接聽事件節點
description: 設定在Marketo Optimizer中接聽事件節點 — 設定事件觸發器、套用選用篩選器，並在活動或資料變更發生時提升人員。
TQID: 'https://experienceleague.adobe.com/6v3i6M-Hhr2RAWrS68WaEVb8VJEzJZbD7vXOJOsjgc8'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
source-git-commit: bc370a501d3f8ff80ad846576b62504aca77f530
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 2%
---
# 接聽事件節點

若要在事件發生時將您的對象推進到歷程的下一個步驟，請新增&#x200B;_接聽事件_&#x200B;節點。

## 事件觸發程式 {#event-triggers}

定義會引發歷程節點並往前移動對象成員的事件條件。

| 觸發程序 | 說明 |
| -------- | ----------- |
| Brand Concierge | 與[!DNL Brand Concierge]互動的潛在客戶活動。 |
| 電子郵件 | 潛在客戶的電子郵件活動，包括傳送、傳送和參與。 |
| 事件 | 潛在客戶的互動式網路研討會活動，包括註冊、出席和互動。 |
| 機會 | 與潛在客戶或帳戶相關聯之商機記錄相關的活動。 |
| 銷售應用程式 | 與[!DNL Sales Qualifier]或[!DNL Marketo Sales Insights]相關的潛在客戶活動。 |
| 其他 | 不屬於預先定義類別的活動，可提供自訂或雜項事件觸發器的彈性。 |

>[!BEGINSHADEBOX]

**支援的觸發程式Marketo Engage活動**

在事件上觸發時，[!DNL Marketo Optimizer]支援來自已連線為資料來源之[!DNL Marketo Engage]執行個體的活動。

>[!NOTE]
>
>只能有一個[!DNL Marketo Engage]執行個體作為資料來源，而且是在布建[!DNL Marketo Optimizer]執行個體時預先設定的。

您可以針對下列[!DNL Marketo Engage]個活動建立事件觸發程式：

* **[!UICONTROL 填寫Marketo Engage表單]** — 當潛在客戶提交指定的[!DNL Marketo Engage]表單時引發。
* **[!UICONTROL 瀏覽Marketo Engage網頁]** — 具有Munchkin追蹤Cookie的潛在客戶瀏覽指定網頁時引發。
* **[!UICONTROL 點按Marketo Engage網頁上的連結]** — 當潛在客戶點按已安裝[!DNL Marketo Engage] Munchkin追蹤程式碼的網頁上的追蹤超連結時，就會引發。
* **[!UICONTROL Marketo Engage電子郵件已傳遞]** — 當潛在客戶的郵件伺服器(MX)傳回成功回應（250 OK訊息）至[!DNL Marketo Engage]傳送伺服器時會引發。
* **[!UICONTROL Marketo Engage電子郵件退信]** — 目標郵件伺服器拒絕已傳送的[!DNL Marketo Engage]電子郵件訊息為永久錯誤（例如無效的使用者或未知網域）時，就會引發。
* **[!UICONTROL Marketo Engage電子郵件軟退信]** — 目標郵件伺服器拒絕已傳送的[!DNL Marketo Engage]電子郵件為暫時性問題（例如伺服器忙碌或信箱已滿）時，就會引發。 在標示問題之前，[!DNL Marketo Engage]會透過MX伺服器自動重試多次軟退信。
* **[!UICONTROL 取消訂閱Marketo Engage電子郵件]** — 潛在客戶選擇退出非營運行銷電子郵件時引發。 觸發時，[!DNL Marketo Engage]會自動將潛在客戶的`Unsubscribed`欄位值更新為`true`，從未來的標準電子郵件傳送中隱藏這些值。
* **[!UICONTROL 開啟Marketo Engage電子郵件]** — 當潛在客戶開啟追蹤的[!DNL Marketo Engage]電子郵件時引發。
* **[!UICONTROL 點按Marketo Engage電子郵件中的連結]** — 當潛在客戶點按[!DNL Marketo Engage]電子郵件中的任何連結（或特定的限制連結）時引發。

>[!ENDSHADEBOX]

## 事件篩選器 {#event-filters}

您可以包含篩選，以根據各種條件限制相符的事件觸發器：

| 篩選器 | 說明 |
| ------- | ----------- |
| 活動歷史記錄 | 根據使用一或多個選取專案評估之條件的活動 |
| Brand Concierge | 與[!DNL Brand Concierge]互動的潛在客戶活動。 |
| 公司屬性 | 公司/帳戶個人資料中的屬性，包括： <li>[!UICONTROL 年收入] <li>[!UICONTROL 公司名稱] <li>[!UICONTROL 帳單國家/地區] <li>[!UICONTROL 產業] <li>[!UICONTROL 員工數目] <li>[!UICONTROL SIC碼] <li>[!UICONTROL 狀態] |
| 意圖資料 | 根據與個人設定檔相關聯的意圖資料的屬性。 |
| 機會 | 根據與個人設定檔相關聯之商機的狀態與屬性，包括： <li>[!UICONTROL 有商機] <li>[!UICONTROL 機會數] <li>[!UICONTROL 總機會金額] <li>[!UICONTROL 已新增至商機] <li>[!UICONTROL 已從商機移除] |
| 人員屬性 | B2B個人設定檔中的屬性，包括： <li>[!UICONTROL 城市] <li>[!UICONTROL 國家/地區] <li>[!UICONTROL 出生日期] <li>[!UICONTROL 電子郵件地址] <li>[!UICONTROL 電子郵件無效] <li>[!UICONTROL 電子郵件已暫停] <li>[!UICONTROL 名字] <li>[!UICONTROL 推斷的狀態區域] <li>[!UICONTROL 職稱] <li>[!UICONTROL 姓氏] <li>[!UICONTROL 行動電話號碼] <li>[!UICONTROL 人員參與度分數] <li>[!UICONTROL 電話號碼] <li>[!UICONTROL 郵遞區號] <li>[!UICONTROL 狀態] <li>[!UICONTROL 已取消訂閱] <li>[!UICONTROL 取消訂閱原因] |
| 銷售應用程式 | 與[!DNL Sales Qualifier]或[!DNL Marketo Sales Insights]相關的潛在客戶活動。 |
| 特殊篩選條件 | 篩選不屬於預先定義類別的屬性，為自訂或其他篩選條件提供彈性。 |

>[!BEGINSHADEBOX]

**篩選器支援的Marketo Engage活動**

篩選觸發的事件時，[!DNL Marketo Optimizer]支援來自連線為資料來源之[!DNL Marketo Engage]執行個體的活動。

>[!NOTE]
>
>只能有一個[!DNL Marketo Engage]執行個體作為資料來源，而且是在布建[!DNL Marketo Optimizer]執行個體時預先設定的。

您可以針對下列[!DNL Marketo Engage]個活動建立事件篩選器：

* **[!UICONTROL 已填寫Marketo Engage表單]** — 符合在其非過時活動記錄中任何時候已完成特定[!DNL Marketo Engage]表單的潛在客戶。
* **[!UICONTROL 造訪的Marketo Engage網頁]** — 比對已在您的網站或[!DNL Marketo Engage]登陸頁面上檢視特定URL的潛在客戶。 直接仰賴您網站上安裝的Munchkin追蹤程式碼。
* **[!UICONTROL 已點按Marketo Engage網頁上的連結]** — 符合已點按追蹤頁面上特定連結或資產的潛在客戶。
* **[!UICONTROL 已傳送Marketo Engage電子郵件]** — 比對[!DNL Marketo Engage]嘗試傳送特定電子郵件的潛在客戶，說明硬退信或伺服器接受之前的部署動作。
* **[!UICONTROL 已傳遞Marketo Engage電子郵件]** — 符合其郵件伺服器(MX)向[!DNL Marketo Engage]傳送伺服器傳回成功回應（250 OK訊息）的潛在客戶。
* **[!UICONTROL Marketo Engage電子郵件已退回]** — 符合在特定電子郵件傳送或時間範圍內遇到硬退回（永久傳遞失敗）的潛在客戶。
* **[!UICONTROL Marketo Engage電子郵件已退信]** — 符合電子郵件發生暫時傳遞失敗（例如完整收件匣或離線伺服器）而非永久硬退信的潛在客戶。
* **[!UICONTROL 已取消訂閱Marketo Engage電子郵件]** — 符合選擇退出非營運行銷電子郵件的潛在客戶。 發生此情況時，[!DNL Marketo Engage]會自動將潛在客戶的`Unsubscribed`欄位值更新為`true`，從未來的標準電子郵件傳送中隱藏這些值。
* **[!UICONTROL 已開啟Marketo Engage電子郵件]** — 比對已開啟追蹤的[!DNL Marketo Engage]電子郵件的潛在客戶。
* **[!UICONTROL 在Marketo Engage電子郵件中點選的連結]** — 符合在[!DNL Marketo Engage]電子郵件中點選任何連結（或特定連結）的潛在客戶。

>[!ENDSHADEBOX]

## 新增事件節點 {#add-event-node}

1. 導覽至歷程畫布。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 接聽事件]**。

   ![按一下歷程路徑上的新增圖示](./assets/person-journey-canvas-add-node.png){width="200"}

1. 在右側的節點屬性中，按一下&#x200B;**[!UICONTROL 新增事件條件]**。

1. 在&#x200B;_[!UICONTROL 編輯事件]_&#x200B;對話方塊中，新增事件並設定您要與觸發條件相符的條件約束。

   將事件觸發器拖放到產生器空間中，並設定定義。 按一下&#x200B;**[!UICONTROL 新增限制]**，以針對您想要用來調整事件比對的每個限制。

   ![編輯事件 — 事件觸發程式](./assets/edit-event-triggers.png){width="700" zoomable="yes"}

   您可以新增多個相符的事件。 第一個符合資格事件會前進歷程中的個人設定檔。

1. （選擇性）選取&#x200B;**[!UICONTROL 篩選器]**&#x200B;索引標籤，並為觸發器新增篩選准則。

   將篩選器拖放到產生器空間中，並設定定義。 按一下&#x200B;**[!UICONTROL 新增限制]**，以針對您想要用來調整篩選比對的每個限制。

   ![編輯事件 — 事件篩選](./assets/edit-event-filters.png){width="700" zoomable="yes"}

1. 按一下&#x200B;**[!UICONTROL 儲存]**。

   您可以隨時按一下&#x200B;**[!UICONTROL 編輯事件]**&#x200B;來變更節點的事件條件。

1. 如有需要，請設定&#x200B;**[!UICONTROL 逾時]**&#x200B;選項，以限制接聽事件的時段。

   >[!NOTE]
   >
   >歷程會在逾時後結束，除非您定義逾時路徑，在其中新增其他節點。

   啟用&#x200B;**[!UICONTROL 逾時]**&#x200B;選項，並選取歷程在逾時前等待事件發生的持續時間。

   為接聽事件歷程節點![&#128279;](./assets/person-journey-event-node-timeout.png){width="550" zoomable="yes"}啟用逾時選項

   您可以選擇在此結束路徑，或透過設定其他路徑採取不同的動作。 若要在歷程中建立新路徑，以便在不發生事件時新增適用於設定檔的動作和事件，請選取&#x200B;**[!UICONTROL 設定逾時路徑]**&#x200B;核取方塊。
