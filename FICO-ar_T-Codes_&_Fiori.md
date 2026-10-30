## 💻 Comprehensive SAP S/4HANA FICO T-Codes & Fiori Apps Directory

SAP FICO consultants and end-users must master both classic SAP GUI Transaction Codes and their modern SAP S/4HANA Fiori App equivalents. Below is the complete operational and reporting reference across the 5 core sub-modules:

---

### 📘 1. General Ledger Accounting (`FI-GL`)

| Category | SAP GUI T-Code | Description (الوظيفة) | Equivalent S/4HANA Fiori App (Name & ID) |
| :--- | :--- | :--- | :--- |
| **Master Data** | **`FS00`** | Manage G/L Account Centrally (إنشاء/تعديل/عرض حساب أستاذ عام) | *Manage G/L Account Master Data (`F0731A`)* |
| **Master Data** | **`FSP0`** | Maintain G/L Account in Chart of Accounts (بيانات الحساب على مستوى الدليل) | *Manage Chart of Accounts (`F0763A`)* |
| **Master Data** | **`FSS0`** | Maintain G/L Account in Company Code (بيانات الحساب على مستوى الشركة) | *Manage G/L Account Master Data (`F0731A`)* |
| **Master Data** | **`OB58`** / **`FSE2`** | Maintain Financial Statement Versions (هيكل القوائم المالية) | *Manage Financial Statement Versions (`F2958`)* |
| **Master Data** | **`OB08`** | Maintain Currency Exchange Rates (إدخال أسعار الصرف اليومية) | *Currency Exchange Rates (`F3616`)* |
| **Master Data** | **`OB52`** | Open and Close Posting Periods (فتح وإغلاق الفترات المحاسبية) | *Manage Posting Periods (`F2293`)* |
| **Transactions** | **`FB50`** / **`F-02`** | Enter G/L Account Document (إدخال قيد يومية عام) | *Post General Journal Entries (`F0718`)* |
| **Transactions** | **`FB50L`** | Enter G/L Document for Ledger Group (قيد لدفتر أستاذ محدد كالضرائب/IFRS) | *Post General Journal Entries (`F0718`)* |
| **Transactions** | **`FV50`** | Park G/L Account Document (تعليق قيد يومية للمراجعة والاعتماد) | *Park General Journal Entries (`F2977`)* |
| **Transactions** | **`FBV0`** / **`FBV2`** | Post / Change Parked Document (ترحيل أو تعديل قيد معلق) | *Verify General Journal Entries (`F2547`)* |
| **Transactions** | **`FB02`** / **`FB03`** | Change / Display Financial Document (تعديل أو استعراض قيد مرحل) | *Manage Journal Entries (`F0717`)* |
| **Transactions** | **`FB08`** | Individual Document Reversal (عكس قيد محاسبي فردي) | *Manage Journal Entries (`F0717`)* |
| **Transactions** | **`F.80`** | Mass Reversal of Documents (عكس جماعي للقيود المحاسبية) | *Mass Reversal of Journal Entries (`F3902`)* |
| **Transactions** | **`F-03`** | Clear G/L Account Manual (مطابقة وتصفية حسابات الأستاذ العام يدوياً) | *Clear G/L Accounts - Manual Clearing (`F1579`)* |
| **Transactions** | **`FBRA`** | Reset Cleared Items (فك المطابقة وعكس التسوية) | *Reset Cleared Items (`F2223`)* |
| **Transactions** | **`FBD1`** / **`F.14`** | Enter / Execute Recurring Entry (إدخال وتشغيل القيود الدورية المتكررة) | *Manage Recurring Journal Entries (`F1598`)* |
| **Transactions** | **`FBS1`** / **`F.81`** | Enter / Reverse Accrual & Deferral Doc (إدخال وعكس قيود الاستحقاق والمقدمات) | *Manage Accrual Objects (`F3853`)* |
| **Period-End** | **`F.13`** | Automatic Clearing (GR/IR & Open Items) (المطابقة الآلية للحسابات المفتوحة) | *Clear G/L Accounts - Automatic (`F4804`)* |
| **Period-End** | **`FAGL_FCV`** | Foreign Currency Valuation (إعادة تقييم العملات الأجنبية) | *Perform Foreign Currency Valuation (`F0773`)* |
| **Period-End** | **`FAGLGVTR`** | G/L Balance Carryforward (ترحيل الأرصدة الافتتاحية للسنة الجديدة) | *Carry Forward Balances (`F1596`)* |
| **Reporting** | **`FAGLL03H`** / **`FBL3N`** | G/L Account Line Item Browser (كشف حركة حساب أستاذ عام تفصيلي) | *Display Line Items in General Ledger (`F2217`)* |
| **Reporting** | **`FS10N`** / **`FAGLB03`**| G/L Account Balance Display (عرض أرصدة حساب أستاذ عام بالشهور) | *Display G/L Account Balances (`F0707A`)* |
| **Reporting** | **`F.01`** / **`S_ALR_87012284`**| Financial Statements: Balance Sheet & P&L (الميزانية العمومية وقائمة الدخل) | *Balance Sheet / Income Statement (`F0708`)* |
| **Reporting** | **`S_ALR_87012277`** | G/L Account Balances - Trial Balance (ميزان المراجعة العام) | *Trial Balance (`F0996A`)* |
| **Reporting** | **`S_ALR_87012287`** | Document Journal (دفتر اليومية الرسمي للقيود) | *Display Document Journal (`F0997`)* |

---

### 📙 2. Accounts Payable (`FI-AP`)

| Category | SAP GUI T-Code | Description (الوظيفة) | Equivalent S/4HANA Fiori App (Name & ID) |
| :--- | :--- | :--- | :--- |
| **Master Data** | **`BP`** | Maintain Business Partner - Roles `FLVN00`/`FLVN01` (إنشاء وتعديل بيانات المورد) | *Manage Business Partner Master Data (`F3163`)* |
| **Master Data** | **`FI01`** / **`FI02`** | Create / Change Bank Master Data (تعريف البنوك وفروعها والسويفت) | *Manage Banks (`F1574`)* |
| **Master Data** | **`FI12_HBANK`** | Maintain House Banks & Bank Accounts (إدارة بنوك الشركة وحساباتها) | *Manage Bank Accounts (`F1366A`)* |
| **Transactions** | **`FB60`** / **`F-43`** | Enter Vendor Invoice (FI Direct) (تسجيل فاتورة مورد مالية مباشرة) | *Create Incoming Invoices (`F0859`)* |
| **Transactions** | **`FB65`** / **`F-41`** | Enter Vendor Credit Memo (تسجيل إشعار دائن/خصم من مورد) | *Create Incoming Invoices (`F0859`)* |
| **Transactions** | **`FV60`** / **`FV65`** | Park Vendor Invoice / Credit Memo (تعليق فاتورة أو إشعار مورد للمراجعة) | *Park Incoming Invoices (`F1756`)* |
| **Transactions** | **`MIRO`** | Enter Logistics Incoming Invoice (MM-FI) (تسجيل فاتورة مشتريات مربوطة بأمر شراء) | *Create Supplier Invoice (`F0859A`)* |
| **Transactions** | **`MIR7`** / **`MR8M`** | Park / Cancel Logistics Invoice (تعليق أو إلغاء فاتورة مشتريات لوجستية) | *Supplier Invoices List (`F1060A`)* |
| **Transactions** | **`F-47`** | Down Payment Request - Vendor (طلب دفعة مقدمة لمورد - Noted Item) | *Manage Supplier Down Payment Requests (`F1688`)* |
| **Transactions** | **`F-48`** | Post Vendor Down Payment (صرف دفعة مقدمة لمورد) | *Post Outgoing Payments (`F1612`)* |
| **Transactions** | **`F-54`** | Clear Vendor Down Payment (تسوية الدفعة المقدمة مع الفاتورة النهائية) | *Clear Outgoing Payments (`F1367`)* |
| **Transactions** | **`F-53`** | Post Outgoing Payment Manually (سداد دفعة لمورد يدوياً) | *Post Outgoing Payments (`F1612`)* |
| **Transactions** | **`F110`** | Automatic Payment Program Run (تشغيل برنامج الدفع الآلي المجمع) | *Manage Automatic Payments (`F0770`)* |
| **Transactions** | **`F-44`** | Clear Vendor Open Items (مطابقة وتصفية حساب المورد يدوياً) | *Clear Outgoing Payments (`F1367`)* |
| **Transactions** | **`FCH5`** / **`FCH8`** | Create / Cancel Check Payment (إصدار شيك يدوي أو إلغاء شيك وصرفه) | *Manage Outgoing Checks (`F1578`)* |
| **Reporting** | **`FBL1N`** / **`FBL1H`** | Vendor Line Item Browser (كشف حساب وحركات الموردين) | *Manage Supplier Line Items (`F0712`)* |
| **Reporting** | **`FK10N`** | Vendor Balance Display (عرض إجمالي أرصدة المورد بالفترات) | *Display Supplier Balances (`F0701`)* |
| **Reporting** | **`S_ALR_87012078`** | Due Date Analysis for Open Items (AP Aging) (تحليل أعمار ديون الموردين) | *Aging Analysis (`F1733`) / Total Payables (`F1746`)* |
| **Reporting** | **`S_ALR_87012082`** | Vendor Balances in Local Currency (ميزان مراجعة الموردين بالعملة المحلية) | *Display Supplier Balances (`F0701`)* |
| **Reporting** | **`S_P00_07000134`**| Generic Withholding Tax Reporting (تقرير ضريبة الخصم والتحصيل للموردين) | *Run Statutory Reports - Withholding Tax (`F1515`)* |

---

### 📗 3. Accounts Receivable (`FI-AR`)

| Category | SAP GUI T-Code | Description (الوظيفة) | Equivalent S/4HANA Fiori App (Name & ID) |
| :--- | :--- | :--- | :--- |
| **Master Data** | **`BP`** | Maintain Business Partner - Roles `FLCU00`/`FLCU01` (إنشاء وتعديل بيانات العميل) | *Manage Business Partner Master Data (`F3163`)* |
| **Master Data** | **`UKM_BP`** | Maintain Credit Management Business Partner (إدارة الحد الائتماني للعميل - Role `UKM000`) | *Manage Credit Accounts (`F4596`)* |
| **Transactions** | **`FB70`** / **`F-22`** | Enter Customer Invoice (FI Direct) (إصدار فاتورة عميل مالية مباشرة) | *Create Outgoing Invoices (`F0798`)* |
| **Transactions** | **`FB75`** / **`F-27`** | Enter Customer Credit Memo (إصدار إشعار دائن/خصم لعميل) | *Create Outgoing Invoices (`F0798`)* |
| **Transactions** | **`FV70`** / **`FV75`** | Park Customer Invoice / Credit Memo (تعليق فاتورة أو إشعار عميل) | *Park Outgoing Invoices (`F0798`)* |
| **Transactions** | **`VF01`** / **`VF02`** | Create / Change Billing Document (SD-FI) (إصدار فاتورة مبيعات مربوطة بأمر بيع) | *Create Billing Documents (`F0798`)* |
| **Transactions** | **`F-37`** | Customer Down Payment Request (طلب دفعة مقدمة من عميل) | *Manage Customer Down Payment Requests (`F1689`)* |
| **Transactions** | **`F-29`** | Post Customer Down Payment (تحصيل دفعة مقدمة من عميل) | *Post Incoming Payments (`F1345`)* |
| **Transactions** | **`F-39`** | Clear Customer Down Payment (تسوية الدفعة المقدمة للعميل مع الفاتورة) | *Clear Incoming Payments (`F0773A`)* |
| **Transactions** | **`F-28`** | Post Incoming Payments (تحصيل دفعة من عميل) | *Post Incoming Payments (`F1345`)* |
| **Transactions** | **`F-32`** | Clear Customer Open Items (مطابقة وتصفية حساب العميل يدوياً) | *Clear Incoming Payments (`F0773A`)* |
| **Transactions** | **`F150`** | Dunning Run (إصدار خطابات المطالبة والاستعجال للعملاء المتأخرين) | *My Dunning Proposals (`F2329`)* |
| **Transactions** | **`FF_5`** / **`FEBAN`** | Upload / Postprocess Electronic Bank Statement (رفع ومطابقة كشف الحساب البنكي EBS) | *Manage Incoming Payment Files (`F1680`) / Reprocess Bank Statement Items (`F1520`)* |
| **Transactions** | **`FBCJ`** | Cash Journal (حركة الخزينة والعهدة النقدية اليومية) | *Cash Journal (`FBCJ`)* |
| **Reporting** | **`FBL5N`** / **`FBL5H`** | Customer Line Item Browser (كشف حساب وحركات العملاء) | *Manage Customer Line Items (`F0711`)* |
| **Reporting** | **`FD10N`** | Customer Balance Display (عرض إجمالي أرصدة العميل بالفترات) | *Display Customer Balances (`F0703A`)* |
| **Reporting** | **`S_ALR_87012168`** | Due Date Analysis for Open Items (AR Aging) (تحليل أعمار ديون العملاء) | *Total Receivables (`F1747`) / Days Sales Outstanding (`F1741`)* |
| **Reporting** | **`S_ALR_87012172`** | Customer Balances in Local Currency (ميزان مراجعة العملاء بالعملة المحلية) | *Display Customer Balances (`F0703A`)* |
| **Reporting** | **`UDM_DISPUTE`** | Dispute Management Cases (متابعة قضايا ونزاعات فواتير العملاء) | *Manage Dispute Cases (`F0702A`)* |

---

### 📕 4. Asset Accounting (`FI-AA`)

| Category | SAP GUI T-Code | Description (الوظيفة) | Equivalent S/4HANA Fiori App (Name & ID) |
| :--- | :--- | :--- | :--- |
| **Master Data** | **`AS01`** / **`AS02`** / **`AS03`** | Create / Change / Display Asset Master Record (إنشاء/تعديل/عرض كارت الأصل الثابت) | *Manage Fixed Assets (`F3425`)* |
| **Master Data** | **`AS11`** | Create Asset Subnumber (إنشاء رقم فرعي لأصل ثابت لإضافات لاحقة) | *Manage Fixed Assets (`F3425`)* |
| **Master Data** | **`AS91`** | Create Legacy Asset (رفع بيانات الأصول التاريخية عند بدء النظام) | *Manage Legacy Assets (`F7280`)* |
| **Transactions** | **`F-90`** | Asset Acquisition with Vendor (شراء أصل ثابت بفاتورة مورد مباشرة) | *Post Asset Acquisition - With Vendor (`F-90`)* |
| **Transactions** | **`ABZON`** | Acquisition w/ Autom. Offsetting Entry (إضافة أصل مقابل حساب وسيط) | *Post Asset Acquisition - Integrated (`F6488`)* |
| **Transactions** | **`ABUMN`** | Asset Transfer Within Company Code (نقل أصل بين مراكز التكلفة أو الفروع) | *Post Asset Transfer (`F7107`)* |
| **Transactions** | **`ABT1N`** | Intercompany Asset Transfer (نقل أصل بين شركات شقيقة مختلفة) | *Intercompany Asset Transfer (`ABT1N`)* |
| **Transactions** | **`F-92`** | Asset Retirement with Customer (بيع أصل ثابت بوجود عميل وفاتورة) | *Post Asset Retirement (`F7106`)* |
| **Transactions** | **`ABAON`** | Asset Sale Without Customer (بيع أصل بدون عميل مقابل حساب وسيط) | *Post Asset Retirement - By Scrapping/Sale (`F7106`)* |
| **Transactions** | **`ABAVN`** | Asset Retirement by Scrapping (تخريد واستبعاد أصل ثابت بدون إيراد) | *Post Asset Retirement (`F7106`)* |
| **Transactions** | **`ABAA`** | Unplanned Depreciation (إثبات إهلاك استثنائي غير مخطط أو اضمحلال) | *Post Manual Depreciation (`ABAA`)* |
| **Transactions** | **`AB08`** | Reverse Asset Document (عكس حركة أصل ثابت) | *Manage Journal Entries (`F0717`)* |
| **Period-End** | **`AIAB`** / **`AIBU`** | Distribute & Settle AuC (Assets under Construction) (توزيع ورسملة المشروعات تحت التنفيذ) | *Run Settlement - Actual (`F4579`)* |
| **Period-End** | **`AFAB`** | Execute Depreciation Posting Run (تشغيل دورة الإهلاك الشهري الآلي) | *Schedule Asset Accounting Jobs (`F1914`)* |
| **Period-End** | **`AFAR`** | Recalculate Depreciation (إعادة احتساب قيم الإهلاك بعد التعديلات) | *Schedule Asset Accounting Jobs (`F1914`)* |
| **Reporting** | **`AW01N`** | Asset Explorer (مستكشف قيم وحركات وإهلاكات الأصل التفاعلي) | *Asset Values (`F1617`) / Manage Fixed Assets (`F3425`)* |
| **Reporting** | **`S_ALR_87011963`** | Asset Balances Report (تقرير أرصدة الأصول الثابتة) | *Asset Balances (`F1615`)* |
| **Reporting** | **`S_ALR_87011990`** | Asset History Sheet (شيت حركة الأصول القانوني للميزانية والإيضاحات) | *Asset History Sheet (`F1616`)* |
| **Reporting** | **`S_ALR_87012936`** | Depreciation Simulation / Forecast (تقرير التنبؤ بالإهلاكات المستقبلية) | *Depreciation Lists (`F1614`)* |

---

### 📒 5. Controlling & Management Accounting (`CO`)

| Category | SAP GUI T-Code | Description (الوظيفة) | Equivalent S/4HANA Fiori App (Name & ID) |
| :--- | :--- | :--- | :--- |
| **Master Data** | **`FS00`** | Create Primary & Secondary Cost Elements (إنشاء عناصر التكاليف في S/4HANA) | *Manage G/L Account Master Data (`F0731A`)* |
| **Master Data** | **`KS01`** / **`KS02`** / **`KS03`** | Create / Change / Display Cost Center (إنشاء وتعديل وعرض مركز التكلفة) | *Manage Cost Centers (`F1443A`)* |
| **Master Data** | **`KSH1`** | Maintain Cost Center Group / Hierarchy (إدارة الهيكل التنظيمي لمراكز التكلفة) | *Manage Cost Center Groups (`F1851`)* |
| **Master Data** | **`KE51`** / **`KE52`** / **`KE53`** | Create / Change / Display Profit Center (إنشاء وتعديل وعرض مركز الربحية) | *Manage Profit Centers (`F3516`)* |
| **Master Data** | **`KCH1`** | Maintain Profit Center Group / Hierarchy (إدارة الهيكل التنظيمي لمراكز الربحية) | *Manage Profit Center Groups (`F0764`)* |
| **Master Data** | **`KO01`** / **`KO02`** / **`KO03`** | Create / Change / Display Internal Order (إنشاء وتعديل وعرض أمر التشغيل الداخلي) | *Manage Internal Orders (`F1604`)* |
| **Master Data** | **`KL01`** | Create Activity Type (Labor/Machine Hours) (تعريف أنواع الأنشطة كساعات العمل والآلات) | *Manage Activity Types (`F1605A`)* |
| **Master Data** | **`KK01`** | Create Statistical Key Figures (SKF) (تعريف المؤشرات الإحصائية للتوزيع كالمساحة وعدد الموظفين)| *Manage Statistical Key Figures (`F1603A`)* |
| **Transactions** | **`KB11N`** | Manual Reposting of Primary Costs (إعادة توجيه التكاليف الأولية يدوياً بين المراكز) | *Reassign Costs and Revenues (`F2009`)* |
| **Transactions** | **`KB21N`** | Direct Activity Allocation (تحميل ساعات الأنشطة المباشرة على المراكز والأوامر) | *Manage Direct Activity Allocation (`F3697`)* |
| **Transactions** | **`KB31N`** | Enter Statistical Key Figures (إدخال القيم الفعلية للمؤشرات الإحصائية) | *Manage Statistical Key Figures - Values (`F4076`)* |
| **Transactions** | **`KP06`** / **`KP26`** | Cost Center Planning (Costs & Activity Prices) (تخطيط الموازنات وأسعار الأنشطة) | *Import Financial Plan Data (`F1711`)* |
| **Product Costing**| **`CK11N`** / **`CK24`** | Create Material Cost Estimate / Mark & Release (احتساب واعتماد التكلفة المعيارية للمنتج) | *Manage Material Cost Estimates (`F4062`) / Release (`CK24`)*|
| **Product Costing**| **`CK40N`** | Edit Costing Run (Mass Costing) (التشغيل الجماعي للتكاليف المعيارية للأصناف) | *Manage Costing Runs - Estimated Costs (`F1865`)* |
| **Period-End** | **`KSV1`** / **`KSV5`** | Create & Execute Actual Distribution Cycle (إنشاء وتشغيل دورات توزيع التكاليف الأولية) | *Manage Allocations (`F3338`) / Run Allocations (`F3548`)* |
| **Period-End** | **`KSU1`** / **`KSU5`** | Create & Execute Actual Assessment Cycle (إنشاء وتشغيل دورات تحميل التكاليف الثانوية) | *Manage Allocations (`F3338`) / Run Allocations (`F3548`)* |
| **Period-End** | **`KO88`** / **`CO88`** | Individual / Collective Order Settlement (تسوية وإقفال أوامر التشغيل والإنتاج) | *Run Settlement - Actual (`F4579`)* |
| **Period-End** | **`KKS1`** / **`KKS2`** | Production Variance Calculation (حساب انحرافات تكاليف أوامر الإنتاج) | *Run Variance Calculation - By Lot (`F4270`)* |
| **Period-End** | **`CKMLCP`** | Material Ledger Costing Cockpit (إقفال دفتر المواد واحتساب التكلفة الفعلية للمخزون) | *Edit Actual Costing Runs (`CKMLCP`)* |
| **Reporting** | **`KSB1`** | Cost Centers: Actual Line Items (كشف حركات مراكز التكلفة الفعلي) | *Display Line Items - Cost Accounting (`F4023`)* |
| **Reporting** | **`S_ALR_87013611`** | Cost Centers: Actual/Plan/Variance (تقرير مقارنة الفعلي بالموازنة والانحرافات للمراكز) | *Cost Centers - Plan/Actual (`F0949A`)* |
| **Reporting** | **`KOB1`** | Orders: Actual Line Items (كشف حركات أوامر التشغيل الداخلي والإنتاج) | *Display Line Items - Cost Accounting (`F4023`)* |
| **Reporting** | **`S_ALR_87012993`** | Internal Orders: Actual/Plan/Variance (تقرير مقارنة الفعلي بالمخطط لأوامر التشغيل) | *Internal Orders - Plan/Actual (`F0942A`)* |
| **Reporting** | **`KE24`** | Profitability Analysis (CO-PA) Actual Line Items (تقرير ربحية المنتجات والشرائح والعملاء) | *Market Segments - Plan/Actual (`F0943A`)* |

> [!TIP]
> **S/4HANA Architectural Shift Note:** 
> * Legacy transactions **`FD01/FK01/XD01/XK01`** are obsolete and permanently redirected to **`BP`**.
> * Legacy Cost Element transactions **`KA01/KA02/KA03/KA06`** are obsolete and merged directly into **`FS00`**.
> * In SAP Fiori Launchpad, you can search using either the **App Name**, the **Fiori App ID** (e.g., `F0718`), or the **Classic T-Code** directly in the search bar.