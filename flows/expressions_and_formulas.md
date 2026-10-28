# EnterpriseDemo-DOIS 核心公式與運算式清單 
# Core Formulas & Expressions Cheat Sheet

### 1. 主流程：自動生成案卷流水號 / Main Flow: Auto-generate Case Serial Number (Title)
**[ZH]** 在「建立項目」的「標題 (Title)」欄位中使用。
**[EN]** Used in the "Title" field of the "Create_item" action.
```text
concat('DEC-', utcNow('yyyyMMdd'), '-', triggerOutputs()?['body/resourceData/responseId'])

```

---

### 2. 主流程：文字估值轉數字 / Main Flow: Convert Text Value to Float (EstimatedValue)

**[ZH]** 在「建立項目」的「估值」欄位中使用。
**[EN]** Used in the "EstimatedValue" field of the "Create_item" action.

```text
float(outputs('Get_response_details')?['body/r8xxxx...'])

```

> **Note:**
> * **[ZH]** 可直接在 Power Automate 運算式中輸入 `float()`，並在括號內點選動態內容「估值/價值」。
> * **[EN]** You can directly type `float()` in the expression builder and select the dynamic content for "Estimated Value" inside the parentheses.
> 
> 

---

### 3. 主流程：OneDrive 附件取得完整路徑 / Main Flow: Get Full Path for OneDrive Attachments

**[ZH]** 在「使用路徑取得檔案內容」的「檔案路徑 (File Path)」中使用。
**[EN]** Used in the "File Path" field of the "Get_file_content_by_path" action.

```text
/Apps/Microsoft Forms/Demo_Gift_Declaration_Form/Question/@{items('Apply_to_each_attachment')?['name']}

```

> **Note:**
> * **[ZH]** 請確保路徑中的表單名稱 (`Demo_Gift_Declaration_Form`) 與資料夾語言 (`Question` 或 `問題`) 與您實際生成的 Forms 暫存路徑一致。
> * **[EN]** Ensure the form name (`Demo_Gift_Declaration_Form`) and folder language (`Question` or `問題`) match your actual Forms staging path in OneDrive.
> 
> 

---

### 4. 主流程：零信任權限隔離 REST API / Main Flow: Zero-Trust RLS REST API (Break Role Inheritance)

**[ZH]** 在「呼叫 SharePoint HTTP 要求」的「URI」欄位中使用，動態打斷該單據的預設權限繼承。
**[EN]** Used in the "URI" field of the "Send an HTTP request to SharePoint" action to dynamically break role inheritance for the specific item.

```text
_api/lists/getByTitle('Demo_Gift_Declarations')/items(@{outputs('Create_item')?['body/ID']})/breakroleinheritance(copyRoleAssignments=false, clearSubscopes=true)

```

---

### 5. 子流程：觸發條件防禦公式 / Sub-Flow: Trigger Condition Defense Formula

**[ZH]** 在子流程「建立或修改項目時」的「設定 ➔ 觸發程序條件」中使用，徹底杜絕無窮迴圈。
**[EN]** Used in the "Settings ➔ Trigger Conditions" of the sub-flow's trigger to completely prevent infinite loops.

```text
@and(equals(triggerOutputs()?['body/Status/Value'], '已完成歸檔'), not(equals(triggerOutputs()?['body/DeclarantAckStatus/Value'], '申報人已確認')))

```

---

### 6. 子流程：標準時間戳記轉換 / Sub-Flow: Standard Time Timestamp (e.g., HKT)

**[ZH]** 在子流程「更新項目」的「申報人確認日期」中使用，將 UTC 轉換為香港法定標準時間。
**[EN]** Used in the "DeclarantAckDate" field of the sub-flow's "Update_item" action to convert UTC to Hong Kong Standard Time.

```text
convertTimeZone(utcNow(), 'UTC', 'China Standard Time')

```


