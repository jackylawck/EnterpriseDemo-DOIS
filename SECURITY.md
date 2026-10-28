# Security Policy & Architecture (安全防護政策與架構)

## 🛡️ Enterprise Security Architecture (企業級資安架構聲明)

This repository serves as an Enterprise Demo designed with **Zero-Trust principles** and aligns with **ISO/IEC 27001 Information Security Management** standards. 

本示範專案遵循「零信任架構」設計，並對標 ISO/IEC 27001 資訊安全管理系統（ISMS）的核心精神（機密性、完整性、可用性）：

1. **Confidentiality (機密性) - Row-Level Security (RLS)**: 
   The Power Automate workflow utilizes SharePoint REST API (`breakroleinheritance`) to enforce Zero-Trust item-level security. Declarations are strictly accessible only to the declarant, line managers, and authorized HR personnel.
   *(系統透過 REST API 動態打斷 SharePoint 權限繼承，確保高度敏感的防貪申報單據僅限申報人、直屬主管及授權 HR 讀取。)*

2. **Integrity (完整性) - Digital Audit Trail**:
   All status changes and disposal directives are injected via system accounts with immutable digital timestamps (HKT/UTC+8), preventing unauthorized tampering and ensuring legal non-repudiation.
   *(所有狀態變更與管理層批示均由系統帳號寫入，並強制蓋印數位時間戳記，確保審計軌跡不可篡改及具備法律防禦力。)*

3. **Availability (可用性) - Zero-License Ecosystem**:
   Built entirely on Microsoft 365 Standard Connectors (Forms, SharePoint Online, Power Automate), ensuring high availability and seamless integration without dependency on premium licensing.
   *(全系統基於 M365 原生標準連接器構建，確保企業在無額外授權成本下享有高可用性的雲端服務。)*

---

## 🚨 Reporting a Vulnerability (漏洞回報機制)

**[English]**
As this is an academic and architectural demonstration repository (Demo), it is not connected to any live production data or active corporate tenant. However, if you discover any architectural security flaws, logic loopholes, or potential injection risks within the provided templates, please report them directly to the repository owner via GitHub Issues or email.

**[中文]**
由於本專案為架構示範用途（Demo），並未連接任何真實企業之正式環境或機敏資料。然若您在程式碼範本、流程邏輯或架構設計中發現任何潛在的資安漏洞（如權限繞過、注入風險等），歡迎透過 GitHub Issues 或直接 Email 聯繫專案擁有者進行技術交流與回報。

**Contact (聯絡方式):**
Please refer to the author's GitHub profile for contact information. / 請參閱作者之 GitHub 個人主頁取得聯絡資訊。
