# 企業防貪合規與內部審計對照規範
### Corporate Anti-Corruption Compliance & Internal Audit Mapping

## 一、 法律合規基準 / Legal & Compliance Basis (Reference: HK POBO Cap. 201)

**[中文]**
參照香港法例第 201 章《防止賄賂條例》（POBO）第 9 條（代理人的貪污交易）：
* 僱員在未經主事者（僱主／董事會）許可下，因其職務關係索取或接受利益，即屬違法。
* 利益包括金錢、禮物、貸款、佣金、職位、合約、服務或優待等。

**EnterpriseDemo-DOIS 系統的合規防禦核心：**
將原本「被動接受後口頭通報」轉換為「事前／即時之法定數位揭露」，並取得主事者（管理層）的明確數位處置批示，使利益處置具備不可撤銷的合規抗辯依據。

---

**[English]**
With reference to Section 9 (Corrupt transactions with agents) of the Prevention of Bribery Ordinance (Cap. 201, Hong Kong):
* It is an offense for an employee to solicit or accept an advantage in relation to their employer's affairs or business without the permission of the principal (employer/board).
* Advantages include money, gifts, loans, commissions, offices, contracts, services, or favors.

**Core Legal Defense of the EnterpriseDemo-DOIS System:**
Transforms the traditional "passive acceptance followed by verbal notification" into a "proactive and real-time statutory digital disclosure." It secures explicit digital disposal directives from the principal (management), providing an irrevocable compliance defense for advantage disposal.

---

## 二、 最佳實踐與系統功能對照表 / Best Practice & System Mapping (Reference: ICAC Guidelines)

| 企業誠信治理建議 / Integrity Governance Recommendations | 傳統紙本痛點 / Paper-based Flaws | EnterpriseDemo-DOIS 數位化控制機制 / Digital Controls |
| :--- | :--- | :--- |
| **及時申報原則**<br>*(Prompt Reporting)* | 表單層層傳遞耗時數週，物品常已被使用或消耗。<br>*Lengthy paper routing often results in items being consumed before approval.* | Forms 即時提交，Power Automate 秒級派發 HR 初審與管理層批示。<br>*Real-time Forms submission; Power Automate dispatches approvals to HR & Management in seconds.* |
| **客觀透明估值**<br>*(Objective Valuation)* | 員工隨意手寫金額，無物證比對。<br>*Arbitrary manual estimations without physical proof.* | 強制上傳實物相片及單據，由 HR 查驗公允市價後呈交。<br>*Mandatory upload of photos/receipts; HR verifies fair market value before escalation.* |
| **多級權限分離**<br>*(Segregation of Duties)* | 部門主管私下核可，缺乏人事與最高層複審。<br>*Private approvals by line managers lacking HR and top executive oversight.* | 嚴格執行「HR 合規審查 ➔ 管理層法定批示 ➔ HR 執行」之三權分立。<br>*Strict enforcement of separation of powers: HR Compliance Review ➔ Management Statutory Directive ➔ HR Execution.* |
| **處置結果閉環**<br>*(Disposal Verification)* | 管理層批示退回或義贈，但無物理落實追蹤。<br>*Management orders return or donation, but physical execution lacks tracking.* | HR 必須在 SharePoint 登錄處置流水帳，並變更狀態觸發閉環。<br>*HR must log the disposal record in SharePoint and update the status to trigger the closure loop.* |
| **雙向確認存證**<br>*(Mutual Sign-off)* | 員工聲稱不知情處置要求，引發勞資與法規爭議。<br>*Employees claim ignorance of disposal decisions, causing disputes.* | 系統自動派發確認卡片，強制員工按掣確認並蓋印數位時間戳記。<br>*Automated cards force employee sign-off, stamping a digital timestamp.* |

---

## 三、 審計追蹤軌跡規格 / Audit Trail Specifications

**1. 不可篡改性 / Tamper-evident Design**
* **[ZH]** 申報原始資料儲存於 SharePoint Online，一般員工無編輯清單權限。每次狀態變更與簽批意見均由 Power Automate 系統帳號寫入，保留修改歷史。
* **[EN]** Original declarations are stored in SharePoint Online; general employees lack edit permissions for the list. Every status change and approval comment is written by the Power Automate system account, preserving version history.

**2. 完整法律時間戳記 / Legally Binding Timestamps**
* **提交時間 (Submission Time):** 由 Microsoft Forms 記錄 / *Logged by Microsoft Forms*.
* **HR 初審時間 (HR Initial Review Time):** 記錄於 Approvals 系統日誌 / *Logged in Approvals system history*.
* **管理層批示時間 (Management Directive Time):** 記錄於 Approvals 系統日誌 / *Logged in Approvals system history*.
* **申報人閉環時間 (Declarant Closure Time):** 以標準時區（如 HKT, UTC+8）寫入 `DeclarantAckDate` 欄位 / *Written to the `DeclarantAckDate` field in standard timezone (e.g., HKT / UTC+8)*.
