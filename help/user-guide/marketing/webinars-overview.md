---
title: 互動式網路研討會
description: 瞭解Marketo Optimizer互動式網路研討會背後的概念，包括網路研討會資產模型、成員國、Token和活動。
keywords: 
role: User
feature: Channels
TQID: 'https://experienceleague.adobe.com/rcaoljHUnCghXxc-W0LY5DYM-46-9jc5mz39208eMxE'
product_v2: id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2: id: 3c1de303-7a7c-59a6-abca-8c534730e19cid: 3cf5f37e-e87e-5179-812b-53ce05d7eebbid: 46e599c6-e20f-5f67-9824-93415016f66bid: 64b90904-e4f0-5c1b-a871-8c6a40b204a1id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4id: d4203578-d294-5145-b397-f26f4488a904
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 1085
ht-degree: 2%

---


# 互動式網路研討會

互動式網路研討會可讓您在不離開[!DNL Adobe Marketo Optimizer]的情況下規劃、提升、提供即時或模擬即時網路研討會，以及進行後續追蹤。 傳遞會在[!DNL Adobe Connect]自動執行，因此您永遠不需要將產品切換為設計註冊頁面、主持即時工作階段或提取出席資料。

>[!NOTE]
>
>此功能需要授權，且受其他條款與條件的約束。 若要查詢其他條款與條件，請檢閱您的合約或聯絡Adobe。

您可以透過兩種方式建立網路研討會：

* **交談體驗** — 要求同事以自然語言排程、推廣並報告網路研討會。 請參閱[與同事建立網路研討會](../agents/webinar-creation.md)。

* **點選並按一下** — 使用&#x200B;_[!UICONTROL 程式]_&#x200B;工作區來新增網路研討會資產、設計資產、新增共同主持人和主持人、建立促銷活動和後續歷程，以及檢閱報告。 請參閱[建立及設計網路研討會](create-webinar.md)和[網路研討會推廣與後續歷程](webinar-journeys.md)。

## 將網路研討會作為資產

網路研討會是[程式](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/marketing-management/programs/programs)所擁有的資產，其方式與電子郵件或登入頁面相同。 新增網路研討會至計畫可在其中註冊，並讓其代號、屬性和活動可用於該計畫中的每個歷程和資產。

>[!IMPORTANT]
>
>計畫目前可以擁有一項網路研討會資產。 計畫在未來的版本中，支援每個計畫的多次網路研討會。

## 會員國

任何人只要是包含網路研討會之計畫的成員，可同時套用三個獨立狀態。 每個變數可在受眾和歷程條件中個別參考。

| 狀態 | 所有者 | 值 |
|---|---|---|
| 方案成員狀態 | 方案 | 可根據[程式型別](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/prime/admin/program-types)設定 |
| 網路研討會狀態 | 網路研討會資產 | 已邀請、已註冊、已出席、不顯示、已隨選 |
| 歷程狀態 | 歷程 | 目前節點、已暫停、已完成和其他歷程執行階段狀態 |

### 網路研討會狀態

網路研討會狀態有五個值。 [!DNL Adobe Connect]通常會自動設定值，但如果您需要覆寫該值，也可以透過歷程動作設定狀態。 例如，若要反映在另一個系統中記錄的出勤率，您可以在歷程中設定狀態。

| 狀態 | 設定方式 | 來源 |
|---|---|---|
| 已邀請 | _採取動作_&#x200B;歷程節點，通常是在傳送邀請電子郵件時 | 作者控制 |
| 已註冊 | 人員註冊時&#x200B;_採取動作_&#x200B;歷程節點。 這也會觸發[!DNL Adobe Connect]產生人員的加入URL | 作者控制 |
| 已出席 | 在即時網路研討會執行後，來自[!DNL Adobe Connect]的活動 | 系統控制，可透過歷程提供作者覆寫 |
| 不顯示 | 在即時網路研討會執行後，來自[!DNL Adobe Connect]的活動 | 系統控制，可透過歷程提供作者覆寫 |
| 隨選出席 | 來自[!DNL Adobe Connect]的事件，未出席的人員稍後會現場觀看錄製 | 系統控制，可透過歷程提供作者覆寫 |

>[!IMPORTANT]
>
>無論是自動設定還是從歷程設定，網路研討會狀態都只會朝一個方向移動，就像[程式狀態](./programs.md#statuses)一樣。 人員可以移至較晚的狀態（例如，_已註冊_&#x200B;到&#x200B;_已參加_），但不能回到較早的狀態。 規劃任何作者覆寫，並注意這種線性遞進。

若要將人員從歷程中移動到不同狀態，請使用&#x200B;**[!UICONTROL 變更網路研討會成員狀態]**&#x200B;動作。 請參閱[網路研討會促銷活動和後續歷程](webinar-journeys.md)。

## 網路研討會Token

網路研討會Token可供您個人化電子郵件內容的任意位置使用（主旨、內文、預覽文字和寄件者）。 在&#x200B;**_內容>網路研討會_**&#x200B;底下的個人化編輯器中尋找它們。

資產層級Token直接位於網路研討會資料夾中：

- 標題
- 說明
- 開始日期時間、結束日期時間
- 持續時間
- 時區
- 主持人
- 錄製URL

>[!NOTE]
>
>共同主機會顯示在網路研討會頁面的「網路研討會團隊」區段中，但無法當作個人化Token使用。

每個收件者的Token位於&#x200B;**Member**&#x200B;子資料夾中：

- **狀態** — 收件者目前的網路研討會狀態（已邀請、已註冊、已出席、不顯示或隨選出席）。 檢視[網路研討會狀態](#webinar-status)。
- **加入URL** — 收件者的個人[!DNL Adobe Connect]連結。 這只有在收件者的網路研討會狀態為已註冊或稍後才解析。 對於先前階段的任何人，它都會解析為空白。
- **錄製URL** — 在即時工作階段發佈錄製作業之後解析，在此之前保持空白。 有條件地在後網路研討會電子郵件中使用連結，以免在要顯示錄製內容之前顯示連結。

>[!NOTE]
>
>網路研討會Token目前僅呈現於電子郵件內容（主旨、內文、預覽文字和寄件者）。 登入頁面和表單中的網路研討會權杖支援已規劃於未來版本中。
>
>由於這些權杖解析為空白而非擲回錯誤，因此參照它們的電子郵件或頁面會在網路研討會生命週期的任何時間點安全地轉譯。 在值可用之前和之後預覽內容，以確認版面朝任一方向看起來都正確。

## 網路研討會活動

每個網路研討會都會自動報告您可用作&#x200B;_接聽事件_&#x200B;觸發器、_分割路徑_&#x200B;條件、對象篩選器和報告量度的活動：

* 提出問題
* 回應輪詢
* 按一下連結
* 下載資產
* 舉手

>[!NOTE]
>
>網路研討會狀態變更（已邀請、已註冊、已出席、不顯示、已出席隨選）目前無法作為自己的&#x200B;_接聽事件_&#x200B;觸發器或活動篩選器。 若要在網路研討會狀態上分支歷程，請直接在網路研討會狀態上使用&#x200B;_分割路徑_&#x200B;條件（在&#x200B;[_建置後續網路研討會歷程_](webinar-journeys.md#build-post-webinar-journey)&#x200B;中說明），而不是接聽狀態變更活動。

在即時活動擷取為相同活動（以隨選模式標籤）後，觀看錄影的人員的參與。 與活動不同，隨選參與確實會建立單獨的網路研討會狀態：未參加即時且後來觀看錄影的人，會從&#x200B;**不播放**&#x200B;移至&#x200B;**隨選參與**。

## 先決條件

開始建立網路研討會之前，請確定已具備下列條件。

| 先決條件 | 詳細資料 |
|---|---|
| 計畫 | 此網路研討會會新增至現有計畫中。 行銷作業分析人員通常先建立方案。 |
| 網路研討會授權（容量） | 網路研討會授權（也稱為容量權利）必須在您排程網路研討會之前可用。 您可在設定時選擇容量，而且可能提供更高容量的附加元件。 若要增加可用容量，請聯絡您的Adobe客戶團隊。 |
| [!DNL Adobe Connect] | 在[!DNL Adobe Connect]內執行傳遞。 布建會在背景自動進行。 您不需要離開[!DNL Marketo Optimizer]來編寫或主持網路研討會。 |

### 權限

網路研討會功能的存取權取決於您指派的網路研討會許可權。

| 角色 | 授予內容 |
|---|---|
| 檢視B2B網路研討會 | 檢視網路研討會清單，以及網路研討會組態、詳細資訊和報告。 建立、設計、編輯和輸入控制項無法透過此許可權使用，而且您也無法被指派為網路研討會的主持人或主持人。 |

<!-- 
| Manage B2B webinars | Full lifecycle access: create, design, configure, schedule, edit, deliver, host, and delete a webinar. The Create, Design, Edit, and Manage controls are available only for users with this role. |
| Webinar co-host | After you are added as a co-host, this permission enables you to design and enter that webinar with co-host controls. |
| Webinar presenter | After you are added as a presenter, this permission enables you to view and enter that webinar with presenter capabilities. It grants no authoring or design access on its own. |

>[!NOTE]
>
>Co-hosts and presenters are currently defined by entering a name and email rather than selected from a picker of role-eligible users — see [Add co-hosts and presenters](create-webinar.md#add-co-hosts-and-presenters). The _Webinar co-host_ and _Webinar presenter_**_ roles still govern what that person can do when they are added as a co-host or presenter.

-->
