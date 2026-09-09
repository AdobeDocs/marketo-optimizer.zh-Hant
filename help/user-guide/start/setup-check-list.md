---
title: 設定檢查清單
description: 完成您的Marketo Optimizer執行個體的初始設定工作，包括使用者存取設定和電子郵件傳遞基礎結構。
TQID: 'https://experienceleague.adobe.com/XEPKIa88-L7mdPz1opKegY1pdEF4Qyls0nLVJBQSaJk'
product_v2:
  - id: a8deb403-4b0c-4f5a-95c6-5e5bedc292ed
feature_v2:
  - id: 3cf5f37e-e87e-5179-812b-53ce05d7eebb
  - id: 64b90904-e4f0-5c1b-a871-8c6a40b204a1
source-git-commit: 43b1b5ba8415d7a7f3291c12c3db4cc333b673c4
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 10%

---

# 設定檢查清單

完成這些工作以啟用您布建的[!DNL Marketo Optimizer]執行個體中的功能。

## 啟用使用者存取 {#enable-user-access}

布建完成且沙箱已繫結時，請為您的團隊和使用者設定[!DNL Journey Optimizer B2B Edition]存取權。

<table>
<thead>
<tr>
<th colspan="2">任務</th>
<th>詳細資訊和指示</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>為使用者提供產品存取和許可權</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>在Admin Console中建立Journey Optimizer B2B edition產品設定檔（僅限一次性/初始設定）</td>
<td><a href="./user-management.md#create-profile">建立設定檔</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>在Admin Console中新增使用者群組</td>
<td><a href="./user-management.md#add-user-group">新增使用者群組</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>將產品設定檔指派給Admin Console中的使用者群組</td>
<td><a href="./user-management.md#assign-profile">指派產品設定檔</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>在Admin Console中將使用者新增至使用者群組</td>
<td><a href="./user-management.md#add-users">新增使用者</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>編輯內建角色，或建立具有產品許可權的自訂角色</td>
<td><a href="./user-management.md#edit-role-permissions">編輯角色</a> <br/> <a href="./user-management.md#create-a-custom-role">建立自訂角色</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>在Adobe Experience Platform中新增使用者或群組至角色</td>
<td><a href="./user-management.md#add-users-to-a-role">新增使用者</a> <br/><a href="./user-management.md#add-user-groups-to-a-role">新增群組</a></td>
</tr>
</tbody>
</table>

## 電子郵件傳遞能力 {#email-deliverability}

行銷人員從歷程傳送電子郵件之前，請先設定組織的傳送基礎架構，包括子網域委派、電子郵件驗證和頻道設定。

<table>
<thead>
<tr>
<th colspan="2">任務</th>
<th>詳細資訊和指示</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>設定電子郵件傳遞能力與通道設定</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>將子網域委派給Adobe （完全委派或CNAME）</td>
<td><a href="./email-deliverability.md#delegate-fully-delegated">已完全委派</a> <br/> <a href="./email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>為子網域設定DMARC</td>
<td><a href="./email-deliverability.md#configure-dmarc">設定DMARC</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>檢閱和指派IP集區</td>
<td><a href="./email-deliverability.md#review-ip-pool">檢閱IP集區</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="任務的核取方塊"/></td>
<td>建立電子郵件通道設定</td>
<td><a href="../admin/email-channel-configuration.md#create-email-channel-configuration">設定電子郵件管道</a></td>
</tr>
</tbody>
