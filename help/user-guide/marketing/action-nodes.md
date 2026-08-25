---
title: 執行動作節點
description: 在Marketo Optimizer中設定「採取動作」節點，以便在人員、清單、程式和目的地到達人員歷程中的節點時新增、移除或更新人員、清單、程式和目的地，或傳送訊息。
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 0%

---

# 執行動作節點

在人員歷程中，當您想要將變更套用至節點路徑上的所有人員時，可對人員使用動作。

## 動作和限制 {#actions}

| 動作 | 限制 |
| ------ | ----------- |
| **[!UICONTROL 啟用到目的地]** | <li>選取或建立靜態清單 <li>如果清單沒有已啟用的目的地，請將清單啟用至一或多個目的地 |
| **[!UICONTROL 將人員新增至歷程]** | <li>選取已排程或即時歷程 <li>未套用目標歷程的對象條件 |
| **[!UICONTROL 新增至清單]** | <li>建立新的靜態清單或選取現有的清單 |
| **[!UICONTROL 新增至Marketo Engage清單]** | <li>在Marketo Engage中選取靜態清單 |
| **[!UICONTROL 變更資料值]** | <li>選取人員屬性 <li>設定新值 |
| **[!UICONTROL 變更方案]**&#x200B;中的狀態 | <li>選取計畫<li>選取新狀態 |
| **[!UICONTROL 變更網路研討會成員狀態]** | <li>選取計畫<li>選取新狀態 |
| **[!UICONTROL 從清單移除]** | <li>選取靜態清單 <li>若目前不是成員，則略過人員 |
| **[!UICONTROL 從Marketo Engage清單移除]** | <li>在Marketo Engage中選取靜態清單 <li>若目前不是成員，則略過人員 |
| **[!UICONTROL 從歷程中移除人員]** | <li>選取即時歷程 <li>如果目前不是目標歷程的成員，則略過人員 |
| **[!UICONTROL 請求Marketo Engage行銷活動]** | <li>選取Marketo Engage行銷活動 |
| **[!UICONTROL 傳送電子郵件]** | <li>建立、編輯或使用AI個人化電子郵件 <li>傳送時間最佳化（選擇性） |
| **[!UICONTROL 傳送WhatsApp]** | <li>選取WhatsApp訊息 |

<!-- 
removed? | **[!UICONTROL Change Program Data]** | <li>Select program attribute <li>Set new value | 
-->

## 新增動作節點 {#add-an-action-node}

1. 導覽至歷程畫布。

1. 按一下路徑上的加號( **+** )圖示，然後選擇&#x200B;**[!UICONTROL 執行動作]**。

   ![按一下歷程路徑上的新增圖示](./assets/person-journey-canvas-add-node.png){width="200"}

1. 在右側的節點屬性中，從清單中選取動作，並設定該動作的任何值。

+++針對目的地啟用

使用此動作將人員新增至靜態清單，並直接從您的歷程將該清單啟動至目的地。 您可以使用現有的靜態清單，或建立專為歷程使用的清單。

>[!PREREQUISITES]
>
>設定&#x200B;_啟用至目的地_&#x200B;歷程節點之前，您必須先為您的[!DNL Marketo Optimizer]沙箱設定一或多個[已設定的目的地](../audiences/destinations.md)。

![採取動作 — 啟用到目的地](./assets/person-action-node-activate-to-destination.png){width="450"}

在&#x200B;**[!UICONTROL 新增至清單]**&#x200B;下，選擇下列其中一個選項：

* **[!UICONTROL 建立]** — 建立新的靜態清單並新增人員。 此清單立即可在&#x200B;**[!UICONTROL 人員清單]**&#x200B;下取得。

  為清單選取父計畫，並輸入&#x200B;**[!UICONTROL 名稱]** （必要）和&#x200B;**[!UICONTROL 描述]** （選用）。 按一下&#x200B;**[!UICONTROL 建立]**&#x200B;以新增節點的清單。

  ![建立要用於歷程節點](./assets/person-action-node-destination-create-list.png){width="375"}的靜態清單

* **[!UICONTROL 選取]** — 選取您要新增到達節點之人員的現有靜態清單。

  選取現有靜態清單的核取方塊，然後按一下[儲存]。**&#x200B;**

  ![選取要用於歷程節點](./assets/person-action-node-destination-select-list.png){width="700" zoomable="yes"}的靜態清單

到達節點的任何人都會新增至所選的靜態清單，但動作要等到清單啟動至目的地之後才會完成：

* 如果選取的清單已經啟動，則其目的地會顯示在&#x200B;**[!UICONTROL 目的地]**&#x200B;下方，而且動作已就緒。
* 否則，會顯示&#x200B;_至少需要一個目的地_&#x200B;訊息。 按一下&#x200B;**[!UICONTROL 啟用清單至目的地]**，選取目的地，然後按一下&#x200B;**[!UICONTROL 儲存]**。 在確認對話方塊中按一下&#x200B;**[!UICONTROL 啟動]**。

![可供啟用的已設定目的地](../audiences/assets/static-list-activate-destination-select.png){width="600" zoomable="yes"}

啟用完成時，目的地會顯示在&#x200B;**[!UICONTROL 目的地]**&#x200B;下方，而且動作已就緒。 如有需要，您可以啟用其他目的地的清單。

到達節點的任何人都會新增至所選的靜態清單（這會在所選目的地啟動），因此他們都會新增至該目的地對象，進而新增至對象摘要的任何促銷活動。

+++

+++[!UICONTROL 將人員新增至歷程]

使用此動作將人員新增到其他排程或即時歷程。 透過此動作新增的人員會立即新增至目標歷程的對象中；目標歷程的對象條件不會套用。

![採取動作 — 將人員新增至歷程](./assets/person-action-node-add-to-journey.png){width="450"}

+++

+++[!UICONTROL 新增至清單]

使用此動作將人員新增至Marketo Optimizer中的靜態清單。

![採取動作 — 新增至清單](./assets/person-action-node-add-to-list.png){width="450"}

選擇下列其中一個選項：

* **[!UICONTROL 建立]** — 建立新的靜態清單資產並新增人員。 此清單可立即供Marketo Optimizer中的其他資產使用。
* **[!UICONTROL 選取]** — 選取您要新增到達節點之人員的現有靜態清單資產。

+++

+++[!UICONTROL 新增至Marketo Engage清單]

使用此動作將人員新增至Marketo Engage中的靜態清單。

![採取動作 — 新增至Marketo清單](./assets/person-action-node-add-to-marketo-list.png){width="450"}

+++

+++[!UICONTROL 變更資料值]

使用此動作來更新人員記錄的屬性值。 選取屬性並設定新值。

>[!TIP]
>
>若要清除屬性的值，請將值設定為`NULL`。

![採取動作 — 變更資料值](./assets/person-action-node-change-data-value.png){width="450"}

+++

+++[!UICONTROL 變更方案]中的狀態

使用此動作來變更Marketo Engage程式中人員的狀態。 選取方案，然後選取新狀態。

![採取動作 — 變更方案狀態](./assets/person-action-node-change-status-program.png){width="450"}

+++

+++[!UICONTROL 變更網路研討會成員狀態]

使用此動作來變更個人與互動式網路研討會相關的狀態。 選取網路研討會，然後選取新狀態。

![採取動作 — 變更方案狀態](./assets/person-action-node-change-webinar-status.png){width="450"}

+++

+++[!UICONTROL 從清單移除]

使用此動作從Marketo Optimizer的靜態清單中移除人員。 如果人員目前不是清單成員，則會略過該人員的動作。

![採取動作 — 從清單移除](./assets/person-action-node-remove-from-list.png){width="450"}

+++

+++[!UICONTROL 從Marketo Engage清單移除]

使用此動作從Marketo Engage的靜態清單中移除人員。 如果人員目前不是清單成員，則會略過該人員的動作。

![採取動作 — 從Marketo清單移除](./assets/person-action-node-remove-from-marketo-list.png){width="450"}

+++

+++[!UICONTROL 從歷程中移除人員]

使用此動作將人員從其他即時人員歷程中移除。 人員會立即從目標歷程中移除，且不會對其採取進一步的動作。 如果人員目前不是目標歷程的成員，則會略過該人員的動作。

![採取動作 — 將人員從歷程移除](./assets/person-action-node-remove-from-journey.png){width="450"}

+++

+++[!UICONTROL 請求Marketo Engage行銷活動]

使用此動作，在連線的Marketo Engage執行個體中將人員新增至請求行銷活動。 選取要請求的Marketo Engage行銷活動。

![採取動作 — 要求Marketo行銷活動](./assets/person-action-node-request-marketo-campaign.png){width="450"}

+++

+++[!UICONTROL 傳送電子郵件]

使用此動作傳送電子郵件給選擇加入的人員。 取消訂閱、封鎖列出、電子郵件已暫停或行銷已暫停的使用者會略過此動作。

![採取動作 — 傳送電子郵件](./assets/person-action-node-send-email.png){width="450"}

您可以建立電子郵件、編輯現有電子郵件，或使用AI個人化電子郵件。 如需有關建立和編輯電子郵件的資訊，請參閱[電子郵件頻道](./email-channel.md)。 若要產生現有電子郵件的人物化變體，請參閱[依人物化電子郵件內容](../agents/personalize-content.md)。

您可以使用[傳送時間最佳化](./email-send-time-optimization.md)，透過預測每個設定檔最有可能參與的時間來個人化電子郵件傳遞時間。

+++

+++[!UICONTROL 傳送WhatsApp]

使用此動作傳送WhatsApp訊息。 您可以在視覺化設計空間建立、個人化和預覽WhatsApp訊息（請參閱[WhatsApp製作](../content/whatsapp-authoring.md)）。

![採取動作 — 傳送WhatsApp](./assets/person-action-node-send-whatsapp.png){width="450"}

+++
