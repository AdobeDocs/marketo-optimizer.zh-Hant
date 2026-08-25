---
title: 電子郵件通道設定
description: 建立並管理電子郵件通道設定，繫結Marketo Optimizer的寄件者身分識別、子網域、IP集區、電子郵件型別和URL追蹤。
feature: Administration
role: Admin
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 0%

---

# 電子郵件通道設定

管道設定是將您的傳送者身分識別、子網域、IP集區和追蹤設定繫結在一起的中央物件。 歷程中的電子郵件動作會參考頻道設定，以瞭解如何傳送訊息。 建立設定之前，請先完成[子網域委派和IP集區設定](../start/email-deliverability.md)。

* **頻道：**&#x200B;電子郵件。
* **電子郵件型別：**&#x200B;行銷或異動。 此設定會決定是否套用隱藏規則（行銷會套用這些規則；交易會略過合法交易訊息的預設垃圾郵件投訴隱藏）。
* **標頭引數：**&#x200B;來自名稱、來自電子郵件、回覆名稱、回覆電子郵件、錯誤電子郵件。
* **子網域：**&#x200B;用於傳送的委派子網域。 寄件者電子郵件必須使用此子網域。
* **IP集區：**&#x200B;用來傳遞訊息的IP集區。
* **URL追蹤：**&#x200B;啟用或停用點選並開啟追蹤；設定追蹤網域。
* **標籤：**&#x200B;組織和搜尋的標籤。

## 建立電子郵件通道設定 {#create-email-channel-configuration}

>[!PREREQUISITES]
>
>* 至少必須委派一個[子網域](../start/email-deliverability.md#subdomain-delegation)且處於作用中。
>* 至少必須指派一個[IP集區](../start/email-deliverability.md#ip-pools)給您的組織。
>* 您需要管理員角色。
>* 檢閱[目前限制](../start/email-deliverability.md#limitations) — 專用的IP集區在Beta中無法使用。

1. 在[!DNL Adobe Marketo Optimizer]左側導覽中，展開&#x200B;**[!UICONTROL 管理]**&#x200B;並選取&#x200B;**[!UICONTROL 管道]**。
1. 在面板中，展開&#x200B;**[!UICONTROL 電子郵件設定]**&#x200B;並選取&#x200B;**[!UICONTROL 頻道設定]**。
1. 按一下&#x200B;**[!UICONTROL 建立通道組態]**。
1. 輸入名稱（例如&#x200B;_Contoso B2B行銷 — 北美_）和選用的說明。
1. 選取&#x200B;**[!UICONTROL 電子郵件]**&#x200B;頻道。
1. （選用）選取標籤以將設定分類。
1. 在&#x200B;**[!UICONTROL 電子郵件型別]**&#x200B;區段中，選擇「行銷」或「異動」。
1. 在&#x200B;**[!UICONTROL 子網域]**&#x200B;區段中，選取先前委派的子網域。
1. 在&#x200B;**[!UICONTROL IP集區]**&#x200B;區段中，選取作用中IP集區。

   在Beta，只有共用IP集區可用。 您可以將游標停留在IP上以檢視PTR記錄。

1. 設定&#x200B;**[!UICONTROL 標頭引數]**：
   * 來源名稱（例如「Contoso行銷」）。
   * 來自電子郵件 — 必須使用選取的子網域（例如，`marketing@mail.contoso.com`）。
   * 回覆名稱與回覆電子郵件 — 如果空白，預設值為&#x200B;_From_。
   * 錯誤電子郵件 — 接收未傳遞通知的地址。
1. 啟用&#x200B;**[!UICONTROL URL追蹤]**&#x200B;並選取追蹤網域。
1. 按一下&#x200B;**[!UICONTROL 提交]**。

>[!NOTE]
>
>提交後，系統會執行驗證：子網域狀態、MX記錄、SPF/DKIM/DMARC校準、IP集區整備、FBL註冊。 組態會透過「草稿→處理」→「作用中」移動。

>[!NOTE]
>
>如果驗證失敗，組態會移至&#x200B;**[!UICONTROL 失敗]**&#x200B;狀態。 開啟設定以檢視失敗原因 — 常見的原因是MX記錄驗證失敗、集區中的IP不符合設定，或DMARC未對齊。 解決並重新提交。

## 編輯或刪除頻道設定 {#edit-channel-configuration}

您可以在建立之後編輯頻道設定，但有一個重要限制： **無法變更頻道。** 設定已繫結至其通道。

編輯使用中的設定時：

* **對於已發佈的歷程：**&#x200B;此變更會在下次週期或下次執行時套用。 在執行中執行會繼續沿用先前的設定。
* **對於異動或即時訊息：**&#x200B;變更會在約五分鐘內傳播。

>[!WARNING]
>
>刪除管道設定是永久性的。 您無法刪除使用中歷程參考的設定。 請先移除或重新指派所有電子郵件動作。

若要刪除設定，請先移除或更新在[新增電子郵件至歷程](../marketing/email-channel.md#define-email-properties)中參照它的每個電子郵件動作。 [!DNL Marketo Optimizer]不會刪除使用中歷程目前使用的設定。

## 多頻道設定 {#multiple-channel-configurations}

大部分的B2B組織會使用多個管道設定來分隔品牌、區域或傳送型別。 常見模式：

* 每個業務單位的個別行銷組態（例如，*BU-A行銷*、*BU-B行銷*）。
* 產品或合約通知的專用交易式設定，其電子郵件型別=交易式。
* 使用區域特定子網域的區域特定設定（例如，`mail.eu.contoso.com`、`mail.us.contoso.com`）以符合區域ISP和法規遵循。

>[!TIP]
>
>以清楚、結構化的慣例命名您的組態 — 例如： *[品牌] - [地區] - [型別]*。 一旦您擁有十數個或更多組態，這一點就變得至關重要。
