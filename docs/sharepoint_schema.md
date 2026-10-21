# Demo_Gift_Declarations 清單規格書 / SharePoint List Schema

* **清單名稱 (List Name)**：`Demo_Gift_Declarations`
* **網站 URL (Site URL)**：`[https://demo-tenant.sharepoint.com/sites/hr](https://demo-tenant.sharepoint.com/sites/hr)` *(Demo Placeholder)*

| 欄位顯示名稱<br>

<br>*(Display Name)* | 內部名稱 / 類型<br>

<br>*(Internal Name / Type)* | 必填<br>

<br>*(Required)* | 選項值 / 格式 / 預設值<br>

<br>*(Options / Format / Default)* | 業務說明<br>

<br>*(Business Description)* |
| --- | --- | --- | --- | --- |
| **標題**<br>

<br>*(Title)* | `Title`<br>

<br>(單行文字 / Single line of text) | 是<br>

<br>*(Yes)* | 自動生成公式 (Auto-generated formula)：<br>

<br>`DEC-YYYYMMDD-ID` | 系統案件唯一流水號<br>

<br>*(System unique serial number)* |
| **申報同事**<br>

<br>*(Declarant Name)* | `DeclarantName`<br>

<br>(單行文字 / Single line of text) | 是<br>

<br>*(Yes)* | 文字 (Text) | 申報人姓名<br>

<br>*(Name of the declarant)* |
| **申報人電郵**<br>

<br>*(Declarant Email)* | `DeclarantEmail`<br>

<br>(單行文字 / Single line of text) | 是<br>

<br>*(Yes)* | 文字 / 電子郵件 (Text / Email) | 提交者企業郵箱<br>

<br>*(Submitter's corporate email)* |
| **所屬組別**<br>

<br>*(Department/Team)* | `Department`<br>

<br>(單行文字或選擇 / Text or Choice) | 是<br>

<br>*(Yes)* | 文字 (Text) | 所屬部門或組別<br>

<br>*(Department or team of the declarant)* |
| **提供者姓名及職銜**<br>

<br>*(Provider Name & Title)* | `ProviderNameTitle`<br>

<br>(單行文字 / Single line of text) | 是<br>

<br>*(Yes)* | 文字 (Text) | 餽贈人身份<br>

<br>*(Identity of the offeror)* |
| **提供者公司**<br>

<br>*(Provider Company)* | `ProviderCompany`<br>

<br>(單行文字 / Single line of text) | 是<br>

<br>*(Yes)* | 文字 (Text) | 餽贈人所屬機構<br>

<br>*(Organization of the offeror)* |
| **業務關係**<br>

<br>*(Business Relationship)* | `BusinessRelationship`<br>

<br>(單行文字 / Single line of text) | 是<br>

<br>*(Yes)* | 文字 (Text) | 雙方業務往來性質<br>

<br>*(Nature of the business relationship)* |
| **獲贈場合**<br>

<br>*(Occasion)* | `Occasion`<br>

<br>(單行文字 / Single line of text) | 是<br>

<br>*(Yes)* | 文字 (Text) | 接受餽贈場合/時節<br>

<br>*(Occasion or timing of receiving the gift)* |
| **饋贈利益詳情**<br>

<br>*(Gift/Advantage Details)* | `GiftDetails`<br>

<br>(多行文字 / Multiple lines of text) | 是<br>

<br>*(Yes)* | 文字 (Text) | 物品名稱、品牌、數量等<br>

<br>*(Item name, brand, quantity, etc.)* |
| **估值**<br>

<br>*(Estimated Value)* | `EstimatedValue`<br>

<br>(數字 / Number) | 是<br>

<br>*(Yes)* | 數字 (小數點位數: 0 或 2)<br>

<br>*(Number - Decimal places: 0 or 2)* | 物品估算市場價值<br>

<br>*(Estimated market value)* |
| **流程狀態**<br>

<br>*(Workflow Status)* | `Status`<br>

<br>(選擇 / Choice) | 是<br>

<br>*(Yes)* | **選項 (Options):**<br>

<br>`待HR初審` *(Pending HR Review)*<br>

<br>`待管理層批核` *(Pending Mgt Approval)*<br>

<br>`待HR執行處置` *(Pending HR Execution)*<br>

<br>`已完成歸檔` *(Archived)*<br>

<br>`HR退回申報` *(Rejected by HR)*<br>

<br>

<br>**預設值 (Default):**<br>

<br>`待HR初審` | 流程生命週期狀態<br>

<br>*(Workflow lifecycle status)* |
| **HR初審結果**<br>

<br>*(HR Review Result)* | `HRReviewResult`<br>

<br>(單行文字 / Single line of text) | 否<br>

<br>*(No)* | `Approve` / `Reject` | 乙部審查結論<br>

<br>*(Part B review conclusion)* |
| **HR初審備註**<br>

<br>*(HR Review Comments)* | `HRReviewComments`<br>

<br>(多行文字 / Multiple lines of text) | 否<br>

<br>*(No)* | 文字 (Text) | HR 審核意見<br>

<br>*(HR review comments)* |
| **管理層批示**<br>

<br>*(Management Directive)* | `MDDecision`<br>

<br>(單行文字或選擇 / Text or Choice) | 否<br>

<br>*(No)* | 7 個法定處置選項之一<br>

<br>*(One of the 7 statutory disposal options)* | 丙部決策結論<br>

<br>*(Part C decision conclusion)* |
| **管理層備註**<br>

<br>*(Management Comments)* | `MDComments`<br>

<br>(多行文字 / Multiple lines of text) | 否<br>

<br>*(No)* | 文字 (Text) | 管理層附加指示<br>

<br>*(Additional instructions from management)* |
| **丁部處置落實記錄**<br>

<br>*(Part D Disposal Log)* | `DisposalActionLog`<br>

<br>(多行文字 / Multiple lines of text) | 否<br>

<br>*(No)* | 文字 (Text) | 實體處置詳情（拍賣/分享/退回等）<br>

<br>*(Details of physical disposal e.g., auction, share, return)* |
| **申報人確認狀態**<br>

<br>*(Declarant Ack Status)* | `DeclarantAckStatus`<br>

<br>(選擇 / Choice) | 否<br>

<br>*(No)* | **選項 (Options):**<br>

<br>`待申報人確認` *(Pending Declarant Ack)*<br>

<br>`申報人已確認` *(Declarant Acknowledged)*<br>

<br>

<br>**預設值 (Default):**<br>

<br>`待申報人確認` | 丁部閉環簽署狀態<br>

<br>*(Part D closed-loop sign-off status)* |
| **申報人確認日期**<br>

<br>*(Declarant Ack Date)* | `DeclarantAckDate`<br>

<br>(日期和時間 / Date and Time) | 否<br>

<br>*(No)* | 包含時間：是<br>

<br>*(Include Time: Yes)* | 員工數位按掣簽核之時間戳記<br>

<br>*(Timestamp of employee's digital sign-off)* |
