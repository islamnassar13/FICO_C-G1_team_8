## 💻 SAP S/4HANA Finance (FI) End-User T-Codes & Fiori Apps Reference

### 📘 1. General Ledger Accounting (`FI-GL`)

#### Master Data & Organizational Maintenance
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`FS00`** | Manage G/L Account Centrally | *Manage G/L Account Master Data (`F0731A`)* |
| **`FSP0`** | Maintain G/L Account in Chart of Accounts | *Manage G/L Account Master Data (`F0731A`)* |
| **`FSS0`** | Maintain G/L Account in Company Code | *Manage G/L Account Master Data (`F0731A`)* |
| **`OB58`** / **`FSE2`** | Maintain Financial Statement Versions | *Manage Financial Statement Versions (`F2759`)* |
| **`OB08`** | Maintain Currency Exchange Rates | *Currency Exchange Rates (`F3616`)* |
| **`OB52`** | Open and Close Posting Periods | *Manage Posting Period Variants (`F2586`) / Open and Close Posting Periods (`F2293`)* |

#### Document Entry, Parking & Reversals
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`FB50`** | Enter G/L Account Document | *Post General Journal Entries (`F0718`)* |
| **`FB50L`** | Enter G/L Account Document for Ledger Group | *Post General Journal Entries (`F0718`)* |
| **`F-02`** | General Journal Entry Posting | *Post General Journal Entries (`F0718`)* |
| **`FB01L`** | General Posting for Ledger Group | *Post General Journal Entries (`F0718`)* |
| **`FV50`** | Park G/L Account Document | *Park General Journal Entries (`F3664`)* |
| **`FBV0`** | Post / Delete Parked Document | *Manage Journal Entries (`F0717`)* |
| **`FBV2`** / **`FBV3`** | Change / Display Parked Document | *Manage Journal Entries (`F0717`)* |
| **`FB02`** | Change Journal Entry Document | *Manage Journal Entries (`F0717`)* |
| **`FB03`** | Display Journal Entry Document | *Manage Journal Entries (`F0717`)* |
| **`FB08`** | Individual Reversal of Document | *Manage Journal Entries (`F0717`)* |
| **`F.80`** | Mass Reversal of Documents | *Mass Reversal of Journal Entries (`F5131`)* |
| **`F-03`** | Clear G/L Account Open Items | *Clear G/L Accounts - Manual Clearing (`F1579`)* |
| **`F.13`** | Automatic Clearing of Open Items | *Clear Open Items Automatically (`F5143`)* |
| **`FBRA`** | Reset Cleared Items | *Reset Cleared Items (`F2223`)* |
| **`FBD1`** | Enter Recurring Entry Document | *Manage Recurring Journal Entries (`F1598`)* |
| **`F.14`** | Execute Recurring Entries | *Manage Recurring Journal Entries (`F1598`)* |
| **`F-01`** | Enter Sample Document | *Manage Journal Entry Templates (`F3484`)* |

#### Period-End Closing & Reporting
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`FAGLL03H`** | G/L Account Line Item Browser (S/4HANA) | *Display Line Items in General Ledger (`F2217`)* |
| **`FAGLB03`** | Display G/L Account Balances | *Display G/L Account Balances (`F0707A`)* |
| **`FAGL_FCV`** | Foreign Currency Valuation (S/4HANA) | *Perform Foreign Currency Valuation (`F2837`)* |
| **`FAGLF101`** | Regrouping Receivables / Payables | *Regroup Receivables and Payables (`F5142`)* |
| **`FAGLGVTR`** | Balance Carryforward (S/4HANA) | *Carry Forward Balances (`F1596`)* |
| **`ACACACT`** | Accrual Engine - Periodic Posting Run | *Schedule Accruals Jobs (`F3777`) / Manage Manual Accruals (`F3539`)* |
| **`S_ALR_87012284`** | Financial Statements (Balance Sheet / P&L) | *Balance Sheet / Income Statement (`F0708`)* |
| **`S_ALR_87012277`** | G/L Account Balances (Trial Balance) | *Trial Balance (`F0996A`)* |
| **`S_ALR_87012287`** | Document Journal | *Display Document Journal (`F0997`)* |
| **`S_ALR_87012357`** | Advance Return for Tax on Sales/Purchases | *Run Statutory Reports (`F1515`)* |

---

### 📙 2. Accounts Payable (`FI-AP`)

#### Master Data
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`BP`** | Maintain Business Partner (Roles `FLVN00` / `FLVN01`) | *Manage Business Partner Master Data (`F3163`) / Maintain Business Partner (`BP`)* |
| **`FK15`** / **`FK16`** | Extend Supplier Master to Company Code | *Manage Supplier Master Data (`F1053A`)* |

#### Invoice Processing, Payments & Down Payments
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`FB60`** | Enter Vendor Invoice (Non-PO) | *Create Incoming Invoices (`F0859`)* |
| **`FB65`** | Enter Vendor Credit Memo (Non-PO) | *Create Incoming Invoices (`F0859`)* |
| **`FV60`** | Park Incoming Vendor Invoice | *Park Incoming Invoices (`F1690`)* |
| **`FV65`** | Park Incoming Vendor Credit Memo | *Park Incoming Invoices (`F1690`)* |
| **`MIRO`** | Enter Incoming Invoice (PO-Based / MM-FI) | *Create Supplier Invoice (`F0859A`)* |
| **`MIR7`** | Park Incoming Invoice (PO-Based) | *Create Supplier Invoice (`F0859A`)* |
| **`MR8M`** | Cancel Logistics Invoice Document | *Manage Supplier Invoices (`F1060A`)* |
| **`MRBR`** | Release Blocked Invoices | *Release Blocked Invoices (`F1766`)* |
| **`F-53`** | Post Outgoing Payments | *Post Outgoing Payments (`F1612`)* |
| **`F-58`** | Outgoing Payment with Printout | *Post Outgoing Payments (`F1612`)* |
| **`F110`** | Automatic Payment Program | *Manage Automatic Payments (`F0770`)* |
| **`F-47`** | Down Payment Request (Vendor) | *Manage Supplier Down Payment Requests (`F1688`)* |
| **`F-48`** | Post Vendor Down Payment | *Post Outgoing Payments (`F1612`)* |
| **`F-54`** | Clear Vendor Down Payment | *Clear Outgoing Payments (`F1367`)* |
| **`F-44`** | Clear Vendor Open Items | *Clear Outgoing Payments (`F1367`)* |
| **`FCH5`** | Create Check Information Manually | *Manage Outgoing Checks (`F1578`)* |
| **`FCH8`** | Cancel Check Payment | *Manage Outgoing Checks (`F1578`)* |
| **`FCHN`** | Check Register | *Manage Outgoing Checks (`F1578`)* |

#### Account Analysis & Reporting
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`FBL1H`** | Vendor Line Item Browser (S/4HANA) | *Manage Supplier Line Items (`F0712`)* |
| **`FK10N`** | Vendor Balance Display | *Display Supplier Balances (`F0701`)* |
| **`S_ALR_87012078`** | Due Date Analysis for Open Items (AP Aging) | *Aging Analysis (`F1733`) / Future Payables (`F1746`)* |
| **`S_ALR_87012082`** | Vendor Balances in Local Currency | *Display Supplier Balances (`F0701`)* |
| **`S_ALR_87012086`** | Vendor List | *Manage Supplier Master Data (`F1053A`)* |

---

### 📗 3. Accounts Receivable (`FI-AR`)

#### Master Data & Credit Management (`FSCM`)
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`BP`** | Maintain Business Partner (Roles `FLCU00` / `FLCU01`) | *Manage Business Partner Master Data (`F3163`) / Manage Customer Master Data (`F0850A`)* |
| **`UKM_BP`** | Maintain Credit Management BP (Role `UKM000`) | *Manage Credit Accounts (`F4596`)* |
| **`UKM_CASE`** | Credit Limit Requests & Documented Credit Decisions | *Manage Documented Credit Decisions (`F2541`)* |
| **`VKM1`** / **`UKM_MY_DCDS`** | Release Credit-Blocked Sales Documents | *Manage Documented Credit Decisions (`F2541`)* |

#### Billing, Incoming Payments & Dunning
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`FB70`** | Enter Outgoing Customer Invoice (Non-SD) | *Create Outgoing Invoices (`FB70`)* |
| **`FB75`** | Enter Outgoing Customer Credit Memo | *Create Outgoing Invoices (`FB75`)* |
| **`FV70`** | Park Outgoing Customer Invoice | *Park Outgoing Invoices (`FV70`)* |
| **`FV75`** | Park Outgoing Customer Credit Memo | *Park Outgoing Credit Memos (`FV75`)* |
| **`F-28`** | Post Incoming Payments | *Post Incoming Payments (`F1345`)* |
| **`F-37`** | Customer Down Payment Request | *Manage Customer Down Payment Requests (`F1689`)* |
| **`F-29`** | Post Customer Down Payment | *Post Incoming Payments (`F1345`)* |
| **`F-39`** | Clear Customer Down Payment | *Clear Incoming Payments (`F0773`)* |
| **`F-32`** | Clear Customer Open Items | *Clear Incoming Payments (`F0773`)* |
| **`F150`** | Dunning Run | *My Dunning Proposals (`F2435`) / Schedule Dunning Jobs (`F5140`)* |
| **`UDM_DISPUTE`** | Dispute Management Processing | *Manage Dispute Cases (`F0702A`)* |

#### Account Analysis & Reporting
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`FBL5H`** | Customer Line Item Browser (S/4HANA) | *Manage Customer Line Items (`F0711`)* |
| **`FD10N`** | Customer Balance Display | *Display Customer Balances (`F0703A`)* |
| **`S_ALR_87012168`** | Due Date Analysis for Open Items (AR Aging) | *Total Receivables (`F1747`) / Overdue Receivables (`F1748`)* |
| **`S_ALR_87012172`** | Customer Balances in Local Currency | *Display Customer Balances (`F0703A`)* |
| **`S_ALR_87012179`** | Customer List | *Manage Customer Master Data (`F0850A`)* |

---

### 📕 4. Asset Accounting (`FI-AA` - New Asset Accounting in S/4HANA)

#### Asset Master Data
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`AS01`** | Create Asset Master Record | *Manage Fixed Assets (`F3425`)* |
| **`AS02`** | Change Asset Master Record | *Manage Fixed Assets (`F3425`)* |
| **`AS03`** | Display Asset Master Record | *Manage Fixed Assets (`F3425`)* |
| **`AS11`** | Create Asset Subnumber | *Manage Fixed Assets (`F3425`)* |
| **`AS05`** | Lock / Block Asset Master Record | *Manage Fixed Assets (`F3425`)* |
| **`AS06`** | Delete Asset Master Record | *Manage Fixed Assets (`F3425`)* |
| **`AS91`** | Create Legacy Asset (Data Transfer) | *Manage Legacy Assets (`F7280`)* |
| **`ABLDT`** | Post Legacy Asset Transfer Values | *Manage Legacy Assets (`F7280`)* |

#### Asset Transactions & Capitalization
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`F-90`** | Asset Acquisition from Purchase with Vendor | *Post Asset Acquisition - Integrated with AP (`F-90`)* |
| **`ABZON`** | Acquisition with Automatic Offsetting Entry | *Post Asset Acquisition (`F6488`)* |
| **`ABUMN`** | Asset Transfer Within Company Code | *Transfer Asset (`ABUMN`)* |
| **`ABT1N`** | Intercompany Asset Transfer | *Intercompany Asset Transfer (`ABT1N`)* |
| **`F-92`** | Asset Retirement from Sale with Customer | *Post Asset Retirement - With Customer (`F-92`)* |
| **`ABAON`** | Asset Sale Without Customer | *Post Asset Retirement (`F7107`)* |
| **`ABAVN`** | Asset Retirement by Scrapping | *Post Asset Retirement (`F7107`)* |
| **`ABZU`** | Write-Up of Asset Value | *Post Write-Up (`ABZU`)* |
| **`ABAA`** | Unplanned Depreciation | *Post Unplanned Depreciation (`ABAA`)* |
| **`ABSO`** | Miscellaneous Asset Transactions | *Post Miscellaneous Transactions (`ABSO`)* |
| **`AB08`** | Reverse Asset Line Items | *Reverse Journal Entries (`FB08`)* |
| **`AIAB`** | Distribute Asset Under Construction (AuC) | *Distribute AuC Settlement Rules (`AIAB`)* |
| **`AIBU`** | Settle Asset Under Construction (AuC) | *Run Settlement - Actual (`F4578`)* |

#### Periodic Processing, Explorer & Reporting
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`AW01N`** | Asset Explorer | *Asset Values (`F1617`) / Manage Fixed Assets (`F3425`)* |
| **`AFAB`** | Execute Depreciation Posting Run | *Schedule Asset Accounting Jobs (`F1914`)* |
| **`AFAR`** | Recalculate Depreciation Values | *Schedule Asset Accounting Jobs (`F1914`)* |
| **`FAA_CMP`** | Maintain Fiscal Year / Period Closure for AA | *Manage Asset Accounting Fiscal Years (`FAA_CMP`)* |
| **`S_ALR_87011963`** | Asset Balances by Asset Number | *Asset Balances (`F1616`)* |
| **`S_ALR_87011990`** | Asset History Sheet | *Asset History Sheet (`F1615`)* |
| **`S_ALR_87012048`** | Asset Transactions Report | *Asset Transactions (`F1614`)* |
| **`S_ALR_87012936`** | Depreciation Simulation / Forecast | *Depreciation Lists (`F1618`)* |

---

### 🏦 5. Bank Accounting & Cash Management (`FI-BL` / `FSCM-CLM`)

#### Bank Master Data (BAM - Bank Account Management)
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`FI01`** / **`FI02`** / **`FI03`** | Create / Change / Display Bank Directory (Bank Keys) | *Manage Banks (`F1574`)* |
| **`FI12_HBANK`** | Maintain House Banks (S/4HANA) | *Manage Banks (`F1574`)* |
| **`NWBC`** (BAM) | Maintain House Bank Accounts (S/4HANA Fiori Required) | *Manage Bank Accounts (`F1366A`)* |

#### Bank Statements, Cash Journal & Liquidity
| T-Code | Description | Equivalent S/4HANA Fiori App (App ID) |
| :--- | :--- | :--- |
| **`FF_5`** | Import Electronic Bank Statement (EBS) | *Manage Incoming Payment Files (`F1680`)* |
| **`FF67`** | Manual Bank Statement Entry | *Manage Bank Statements (`F1564`)* |
| **`FEBAN`** / **`FEB_BSPROC`** | Postprocess Electronic Bank Statement | *Reprocess Bank Statement Items (`F1520`)* |
| **`FBCJ`** | Petty Cash Journal | *Cash Journal (`FBCJ`)* |
| **`FF7AN`** | Cash Position (S/4HANA) | *Cash Flow Analyzer (`F2332`)* |
| **`FF7BN`** | Liquidity Forecast (S/4HANA) | *Cash Flow Analyzer (`F2332`)* |
| **`FQM_INITIALIZE`** | One Exposure from Operations Load | *Schedule Cash Management Jobs (`F3397`)* |

> [!NOTE]
> In SAP S/4HANA, maintaining House Bank Accounts (`FI12` in ECC) is strictly migrated to Fiori App **Manage Bank Accounts (`F1366A`)**, and line item reports (`FBL1N`, `FBL5N`, `FBL3N`) are augmented by HANA-optimized browsers (`FBL1H`, `FBL5H`, `FAGLL03H`) and native Fiori analytical apps.