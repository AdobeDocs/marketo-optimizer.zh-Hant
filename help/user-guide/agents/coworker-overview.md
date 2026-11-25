---
title: Adobe Marketo Optimizer中的CX Enterprise Coworker概觀
description: 瞭解CX Enterprise Coworker如何使用Marketo Optimizer技能來建立和調整計畫、檢查AI決策整備情況，以及呼叫MCP工具。
autotag-review: '2026-11-24T22:43:00.917Z'
TQID: https://experienceleague.adobe.com/V4Kww-NcdfbFxXqWrs7mPq7UYu8AREqDgyfvlMnlURM
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
    internal-label: Marketo Optimizer
feature_v2:
  - id: 1650dadf-b034-5ac9-a309-77ad1e2f5035
    internal-label: Chat Interface
  - id: 5229c72e-d79b-574f-a03e-5c4bf48172c3
    internal-label: AI Decisioning
  - id: a29661b8-f7a4-53d1-a9ac-fdec08c092e4
    internal-label: Programs
subfeature_v2:
  - id: b9e5c7f3-be30-563c-9e41-cc8ea76e2fee
    internal-label: Skills
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
source-git-commit: 418b81a0a39eca0ca7b537c76da972df7eefd09f
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 2%
---

# [!DNL Adobe Marketo Optimizer]中的[!DNL CX Enterprise Coworker] {#coworker-overview}

[!DNL CX Enterprise Coworker]聊天是對話式介面，可在[!DNL Adobe Marketo Optimizer]中完成工作。 以純文字描述目標，[!DNL Coworker]會規劃工作、在[!DNL Marketo Optimizer]中執行、驗證結果，並提供完成的工作以供您核准。

[!DNL Coworker]使用專為[!DNL Marketo Optimizer]建立的技能引導您完成常見行銷操作任務：建立新方案、調整現有[!DNL Marketo Engage]方案，以及檢查您的資料是否已準備好進行AI決策。

[!DNL Coworker]尊重您組織的現有[[!DNL Marketo Optimizer] 許可權](../start/permissions-reference.md)。 您只能執行您已經獲准執行的動作，而管理員可以控制您何時擁有寫入存取權。 [!DNL Coworker]是Adobe生態系統的一部分，不限於[!DNL Marketo Optimizer]。

如需詳細資訊，請參閱：

* [[!DNL Adobe CX Enterprise Coworker]聊天總覽](https://experienceleague.adobe.com/zh-hant/docs/coworker/content/chat/overview)
* [在 [!DNL Marketo Optimizer]的聊天介面](./chat-interface.md)
* [&#x200B; [!DNL Marketo Optimizer]中的[!DNL Coworker]技能](./skills.md)

## 在[!DNL CX Enterprise Coworker]中有[!DNL Marketo Optimizer]個技能 {#skills}

使用下列產品特定技能來建立和調整方案，或評估資料準備程度。

| 技能 | 協助您完成的工作 | 範例請求 |
| --- | --- | --- |
| `program-creation-marketo-optimizer` | 建立端對端的[!DNL Marketo Optimizer]行銷方案。 [!DNL Coworker]會引導您從目標完成並建置計畫。 | 上傳行銷活動簡報，然後詢問： _使用附加的簡訊建立方案。_ |
| `adapt-program-marketo-optimizer` | 調整、移轉或轉換現有的[!DNL Marketo Engage]程式為[!DNL Marketo Optimizer]程式。 | _將我們的第3季企業網路研討會Nurture方案從[!DNL Marketo Engage]調整為[!DNL Marketo Optimizer]。_ |
| `ai-decisioning-health-marketo-optimizer` | 報告您的租使用者的資料是否已準備好進行AI決策，涵蓋故事涵蓋範圍、特徵豐富度和角色涵蓋範圍。 | _哪些資料用於AI決策？_ |

### 程式建立提示範例 {#program-creation-prompt}

上傳簡報或直接說明程式。 包含您希望[!DNL Coworker]使用的對象、歷程、內容和設定。

此圖表總結了以下範例中的提示區段。 它會顯示如何組織請求，而非人員移動歷程的順序。

![八個方案建立提示區段：方案目標、對象、具有意圖型邀請的歷程、電子郵件內容、LinkedIn啟用、註冊處理、事件後跟進以及設定。](./assets/coworker-program-creation-prompts.svg){width="800" zoomable="yes"}

展開每個區段以檢視範例提示。

+++方案目標

_使用電子郵件和LinkedIn，建立名為Experience Cloud Leadership Forum - AI支援的Experience Summit的B2B行銷計畫，於8月3日至12月3日舉行。 此活動於上午9:00在灣區創新中心舉行。 立即開始歷程。_

+++

+++客群

_鎖定具有Experience Cloud任何產品意向且參與分數大於1的人員。 排除已取消訂閱和行銷暫停的設定檔。_

+++

+++歷程

_使用下一個最佳路徑，依高、Medium和低Experience Cloud意圖來分割對象。 傳送根據每個意圖層級量身打造的個人化電子郵件邀請。 合併路徑並等待兩天。 檢查電子郵件開啟、點按、內容參與和註冊。 傳送議程預覽給參與的成員；在LinkedIn上啟用未參與的成員，並等待兩天。 合併參與路徑，並在事件發生10天前傳送最終註冊提醒。 啟用所有電子郵件的傳送時間最佳化。_

+++

+++電子郵件內容

_建立三封電子郵件：主管邀請（活動前6週）、議程預覽（活動前6週）和最終註冊提醒（活動前10天）。 包含相關主旨列、標題、行動要求（預留我的名額、檢視議程、完整註冊）和使用個人故事、角色分類、產業、解決方案興趣、最近參與和Experience Cloud意圖的AI個人化內容。 邀請中包含場地影像，但議程預覽中沒有橫幅。_

+++

+++LinkedIn

_將目標鎖定為未參與的成員，這些成員具有促進客戶體驗轉換和AI個人化的贊助內容。_

+++

+++註冊

_立即結束邀請歷程的註冊會員，並傳送一封主管準備電子郵件，內含AI產生的討論主題、個人化議程、地點詳細資料、建議的工作階段以及行事曆連結。_

+++

+++貼文事件

_透過回顧、錄製、資源和銷售資格審查，將與會者導向Experience Cloud領導力後續計畫。 傳送不顯示的峰會亮點、隨選內容以及未來的活動邀請。_

+++

+++設定

_將my.replyToEmail設定為`events@example.com`，並將my.senderName設定為Experience Cloud事件。 使用僅變更城市、地點、主題和產業焦點的可重複使用範本。_

+++

如需有關準備簡報的詳細資訊，請參閱[從簡報建立程式](./program-from-brief.md)。

## 使用案例範例 {#use-cases}

### 在檢查資料整備情況後建立方案 {#check-readiness-create-program}

在建置新的帳戶型方案之前，行銷作業負責人想知道租使用者已準備好進行AI決策。

1. 若要檢閱本文涵蓋範圍、特徵豐富度和角色涵蓋範圍，請執行[AI決策健康狀態檢查](./ai-decisioning-health.md)。 例如，詢問：_向我顯示用於AI決策的Marketo資料。_
1. 解決報表所指出的任何差距。
1. 上傳行銷活動簡報，並詢問： _使用附加的簡訊建立方案。_
1. 當[!DNL Coworker]顯示結果時，請檢閱並核准方案。

結果會是整備程度報告，找出不足之處，然後是建立在可支援AI決策的資料上的計畫。

### 將現有[!DNL Marketo Engage]方案移至[!DNL Marketo Optimizer] {#adapt-program}

需求產生團隊想要在[!DNL Marketo Optimizer]中執行經過驗證的程式，而不需要手動重建。

1. 命名要改寫的[!DNL Marketo Engage]程式。 例如： _將Q3 Enterprise網路研討會Nurture方案從[!DNL Marketo Engage]調整為[!DNL Marketo Optimizer]。_
1. [!DNL Coworker]將程式對應到[!DNL Marketo Optimizer]建構，並標示未轉換的任何專案。
1. 檢閱結果並核准。

結果是一個轉換的程式供您審閱，另外還有需要手動決定的專案清單。

## [!DNL Marketo Optimizer] MCP工具 {#mcp-tools}

[!DNL Coworker]技能在[!DNL Marketo Optimizer]模型內容通訊協定(MCP)伺服器上呼叫下列37個工具。 每個工具名稱都帶有前置詞`marketo-optimizer__`。

此參考資料涵蓋註冊技能所記錄的工具，包括工作流程期間使用的支援技能。 它不會指示部署狀態或使用頻率。 此表格中的技能名稱會依循工具參照，且可能與上方列出的產品特定技能名稱不同。

| 工具 | 技能 | 用途 |
| --- | --- | --- |
| `marketo-optimizer__get_workspace_root_tree` | `program-creation-marketo-optimizer` | 尋找新程式的工作區區域或已命名的子資料夾。 |
| `marketo-optimizer__create_program` | `program-creation-marketo-optimizer` | 在已確認的區域或資料夾中建立方案。 |
| `marketo-optimizer__list_programs` | `program-creation-marketo-optimizer`, `landing-page-authoring` | 瀏覽程式或尋找登入頁面的檔案位置。 |
| `marketo-optimizer__get_program` | `program-creation-marketo-optimizer` | 依ID讀取計畫。 |
| `marketo-optimizer__update_program` | `program-creation-marketo-optimizer` | 更新程式中繼資料，例如其名稱。 |
| `marketo-optimizer__create_program_token` | `program-creation-marketo-optimizer` | 建立或修正已核准的計畫權杖。 |
| `marketo-optimizer__list_program_tokens` | `program-creation-marketo-optimizer` | 讀取方案的已解析Token。 |
| `marketo-optimizer__create_dynamic_people_list_with_rules` | `program-creation-marketo-optimizer` | 建立方案連結的人員清單，並從說明產生對象規則。 |
| `marketo-optimizer__list_people_journeys` | `adapt-program`；頻道外掛程式共用參考 | 檢查目的地歷程名稱衝突、在不明確結果後尋找現有歷程，或瀏覽歷程以進行頻道工作。 |
| `marketo-optimizer__create_person_journey` | `program-creation-marketo-optimizer`, `adapt-program`, `channel-content-authoring` | 建立程式連結歷程、開始改編歷程，或為電子郵件頻道建立缺失歷程。 |
| `marketo-optimizer__get_person_journey` | `program-creation-marketo-optimizer`， `adapt-program`；頻道外掛程式共用參考 | 閱讀歷程或其畫布、驗證分階段編輯，或查詢歷程以瞭解頻道工作。 |
| `marketo-optimizer__update_person_journey` | `adapt-program` | 一次將一個已核准的建置步驟附加至目的地歷程。 |
| `marketo-optimizer__run_person_journey_simulation` | `program-creation-marketo-optimizer` | 驗證歷程流程而不發佈。 |
| `marketo-optimizer__run_program_qa` | `program-creation-marketo-optimizer` | 對計畫及其歷程執行唯讀整備程度檢查。 |
| `marketo-optimizer__create_channel` | `channel-content-authoring`；`program-creation-marketo-optimizer`和`image-to-html`透過移交 | 建立並連結頻道。 對於電子郵件，第一個呼叫會列出範本；第二個呼叫會使用選取的範本建立和連結電子郵件。 |
| `marketo-optimizer__get_channel` | `channel-content-authoring` | 讀取管道，可選擇包括其電子郵件主題和HTML。 |
| `marketo-optimizer__list_channels` | `channel-content-authoring` | 依型別瀏覽管道，並可選擇依名稱篩選。 |
| `marketo-optimizer__update_channel_content` | `channel-content-authoring`； `image-to-html`已移交 | 更新電子郵件的主旨或HTML，包括套用轉換的HTML。 |
| `marketo-optimizer__image_to_html` | `image-to-html` | 開始非同步電子郵件設計轉換，並擷取可編輯的HTML。 |
| `marketo-optimizer__list_asset_library_images` | `landing-page-authoring` | 搜尋登陸頁面位置的替代影像。 |
| `marketo-optimizer__add_asset_to_program_or_folder` | `landing-page-authoring` | 在選取的最佳化處理程式或資料夾中註冊新的登入頁面。 |
| `marketo-optimizer__get_person_story` | `personalization-engine-health` | 依數值ID閱讀某人的個人化故事。 |
| `marketo-optimizer__get_persona_story` | `personalization-engine-health` | 請閱讀故事以取得確切的角色名稱。 |
| `marketo-optimizer__run_arbitration` | `personalization-engine-health` | 在明確確認後，重新評分並重新選取符合資格的歷程。 |
| `marketo-optimizer__get_arbitration_summary` | `personalization-engine-health` | 讀取最新仲裁回合的摘要統計資料。 |
| `marketo-optimizer__get_arbitration_decisions` | `personalization-engine-health` | 閱讀最新仲裁執行中的個人決定。 |
| `marketo-optimizer__get_ai_decisioning_health_summary` | `ai-decisioning-health` | 擷取整體的租使用者整備程度報表。 |
| `marketo-optimizer__get_persona_distribution` | `ai-decisioning-health` | 報表角色計數和百分比。 |
| `marketo-optimizer__get_people_without_personas` | `ai-decisioning-health` | 報告無角色的人數與分享率。 |
| `marketo-optimizer__get_person_story_attribute_coverage` | `ai-decisioning-health` | 測量特徵類別涵蓋範圍並識別填入的欄位。 |
| `marketo-optimizer__get_person_story_data_completeness` | `ai-decisioning-health` | 依角色報告故事的豐富度、完整度和變數。 |
| `marketo-optimizer__get_person_story_coverage` | `ai-decisioning-health` | 報告劇本涵蓋範圍、趨勢和待處理的產生。 |
| `marketo-optimizer__get_personalization_story_pipeline_status` | `ai-decisioning-health` | 讀取管道狀態、執行歷史記錄和報告的持續時間。 |
| `marketo-optimizer__get_person_story_refresh_backlog` | `ai-decisioning-health` | 計算因來源資料變更而等待重新整理的劇本。 |
| `marketo-optimizer__get_person_intent_signal_coverage` | `ai-decisioning-health` | 測量產品意圖、關鍵字意圖和活動涵蓋範圍。 |
| `marketo-optimizer__get_person_story_activity_coverage` | `ai-decisioning-health` | 報告擷取的參與欄位和彙總活動趨勢。 |
| `marketo-optimizer__get_person_audience_membership_distribution` | `ai-decisioning-health` | 報告每個人的受眾會籍的平均值和分佈。 |
