---
title: C2PA中繼資料
description: 瞭解Adobe Marketo Optimizer如何將C2PA中繼資料自動套用至使用創作AI產生的影像，以及這對於您的內容有何意義。
feature: Assets, Content
role: User
source-git-commit: c7d3546d075f5a58923134231217b2fd10fe4aca
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---

# C2PA中繼資料

行銷組織更關注內容透明度、AI揭露和防止資產竄改。 Adobe的Content Authenticity Initiative (CAI)建立符合[內容來源與真偽聯盟](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) (C2PA)技術標準的工具。 _C2PA中繼資料_&#x200B;已加密、顯示篡改的資訊，可協助檢視者瞭解內容歷程，並確保品牌資產的完整性。 此資訊包括：

* 發行者或簽署者 — 發行數位簽名以認證或簽署資產的實體或公司的相關資訊。
* 問題日期 — 將C2PA中繼資料套用至資產的日期。
* [Credit and Usage] — 有關資產製作者的資訊，包括名稱、社群媒體控制代碼或其他與身分相關的資訊。
* 程式 — 對資產所做的任何編輯或修改的記錄。
* 裝置詳細資訊 — 關於用來建立或編輯資產的應用程式或裝置的資訊。
* 使用的AI工具 — 如果使用產生AI來建立資產，則可能會包含使用的模型名稱。
* 其他相關資訊 — 也會包含其他資料，以協助提供有關資產歷史記錄的更多內容。

如需資產記錄的完整資訊，您可以使用Adobe Content Authenticity [檢查工具](https://contentauthenticity.adobe.com/inspect)。

C2PA中繼資料會隨著影像檔案持續存在。 使用產生AI產生或編輯的影像上傳至[!DNL Adobe Marketo Optimizer]或從匯出時，會保留其C2PA中繼資料。

>[!NOTE]
>
>有些將影像匯入內容的方法(例如從PDF或內嵌(base64)來源擷取影像)可能不會保留原始C2PA中繼資料。 在這些情況下，無法從來源讀取C2PA中繼資料，並且不會為結果建立任何資料。

>[!BEGINSHADEBOX]

## C2PA中繼資料透過管道持續存在 {#channels}

當您將影像納入電子郵件或WhatsApp訊息中時，也會持續儲存已傳送影像的C2PA中繼資料：

* **電子郵件** — 當您使用&#x200B;_傳送電子郵件_&#x200B;歷程動作時，請將影像從&#x200B;_Assets_&#x200B;資料庫新增至您的電子郵件內容。 在傳遞電子郵件時，收件者可以從訊息下載影像，且C2PA中繼資料保持不變。
* **WhatsApp** — 將影像新增至Meta商業帳戶中的WhatsApp訊息範本。 您可以直接從您的系統新增，或從&#x200B;_Assets_&#x200B;資料庫下載影像檔案。 使用範本進行&#x200B;_傳送WhatsApp_&#x200B;歷程動作。 傳遞WhatsApp訊息時，收件者可以從訊息下載影像，且C2PA中繼資料保持不變。

>[!ENDSHADEBOX]

## 影像產生 {#generate}

>[!INFO]
>
>圍繞創作AI透明度的新法律不斷湧現，Adobe正在努力滿足各個司法轄區的適用要求。 C2PA中繼資料是Adobe用來符合這些法律要求的來源工具。

當您使用generative AI為[!DNL Marketo Optimizer]中的電子郵件內容建立影像時，C2PA中繼資料會自動附加至產生的影像，而您不需要採取任何動作。 創作AI工具會為具有現有中繼資料（包括原始來源）的影像變體產生合併的C2PA中繼資料元素。

>[!NOTE]
>
>[!DNL Marketo Optimizer]目前不支援手動影像編輯動作。 這些動作的C2PA中繼資料工作流程目前不適用。
