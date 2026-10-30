## 🖥️ SAP FICO End-User Transaction Codes & S/4HANA Fiori Equivalents

SAP FICO consultants and end-users should be familiar with commonly used transaction codes across core financial and controlling sub-modules, along with their modern SAP S/4HANA Fiori counterparts.

---

### 📘 General Ledger (`FI-GL`)

#### Master Data
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FS00`** | G/L Account Master Data (Central) | *Manage G/L Account Master Data (F0731A)* |
| **`FSP0`** | G/L Account Master Data (Chart of Accounts) | *Manage G/L Account Master Data (F0731A)* |
| **`FSS0`** | G/L Account Master Data (Company Code) | *Manage G/L Account Master Data (F0731A)* |
| **`OB_GLACC11`** / **`OB_GLACC12`** / **`OB_GLACC13`** | Mass Maintenance of G/L Accounts | *Mass Maintenance of G/L Accounts* |
| **`FSE2`** | Maintain Financial Statement Version | *Manage Global Hierarchies (F2918) / Maintain Financial Statement Versions (F4409)* |

#### Document Entry & Posting
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FB50`** | G/L Account Posting (Single Screen) | *Post General Journal Entries (F0718)* |
| **`FB50L`** | Enter G/L Account Document for Ledger Group | *Post General Journal Entries - For Ledger Group* |
| **`F-02`** | General Ledger Document Posting (Header/Items) | *Post General Journal Entries (F0718)* |
| **`FV50`** | Park G/L Account Document | *Park General Journal Entries (F2547)* |
| **`FBV0`** | Post / Delete Parked Document | *Verify General Journal Entries (F2548)* |
| **`FBV2`** / **`FBV3`** | Change / Display Parked Document | *Manage Journal Entries (F0717)* |
| **`F-65`** | General Document Parking | *Park General Journal Entries (F2547)* |
| **`FBR2`** | Post Document with Reference | *Manage Journal Entries (F0717)* |
| **`FBM1`** / **`FBM2`** / **`FBM3`** | Enter / Change / Display Sample Document | *Manage Sample Journal Entries* |
| **`FBD1`** / **`FBD2`** / **`FBD3`** | Enter / Change / Display Recurring Entry | *Manage Recurring Journal Entries (F1598)* |
| **`F.14`** | Execute Recurring Entries | *Manage Recurring Journal Entries (F1598)* |
| **`F.15`** | Recurring Entries List | *Manage Recurring Journal Entries (F1598)* |
| **`FBS1`** | Enter Accrual / Deferral Document | *Post General Journal Entries (F0718)* |
| **`F.81`** | Reverse Accrual / Deferral Document | *Reverse Accrual/Deferral Document* |
| **`ACACACT`** | Manual Accruals: Calculate & Post Accruals | *Manage Manual Accruals (F3697)* |

#### Document Control, Clearing & Reversal
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FB02`** | Change Document | *Manage Journal Entries (F0717)* |
| **`FB03`** | Display Document | *Manage Journal Entries (F0717)* |
| **`FB09`** | Change Line Items | *Manage Journal Entries (F0717)* |
| **`FB08`** | Individual Document Reversal | *Manage Journal Entries (F0717) / Reverse Document* |
| **`F.80`** | Mass Document Reversal | *Mass Reversal of Documents* |
| **`F-03`** | Clear G/L Account | *Clear G/L Accounts - Manual Clearing (F1579)* |
| **`F.13`** | Automatic Clearing without Currency Specification | *Clear G/L Accounts / Schedule Automatic Clearing (F5477)* |
| **`FBRA`** | Reset Cleared Items | *Reset Cleared Items (F2223)* |
| **`FBU2`** / **`FBU3`** | Change / Display Intercompany Document | *Display Intercompany Journal Entries* |
| **`FBU8`** | Reverse Cross-Company Code Document | *Reverse Intercompany Journal Entries* |

#### Period-End Closing & Currencies
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`OB08`** | Maintain Exchange Rates | *Currency Exchange Rates (F3616)* |
| **`OB52`** | Open and Close Posting Periods | *Manage Posting Periods (F2293)* |
| **`FAGL_FCV`** | Foreign Currency Valuation (New) | *Perform Foreign Currency Valuation (F3338)* |
| **`FAGL_FC_TRANS`** | Currency Translation of Balances | *Currency Translation of Balances* |
| **`F.19`** | GR/IR Clearing / Reclassification | *Reconcile GR/IR Accounts (F3302)* |
| **`FAGLF101`** | Regrouping Receivables / Payables | *Regroup Receivables / Payables* |
| **`FAGLGVTR`** | G/L Balance Carryforward | *Carry Forward Balances (F1596)* |

#### Reporting & Line Item Analysis
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FBL3N`** / **`FAGLL03`** / **`FAGLL03H`** | G/L Account Line Item Display / Browser | *Display Line Items in General Ledger (F2217) / Display G/L Account Line Items (F0706)* |
| **`FS10N`** / **`FAGLB03`** | G/L Account Balance Display | *Display G/L Account Balances (F0707A)* |
| **`F.01`** / **`S_ALR_87012284`** | Financial Statements (Balance Sheet & P&L) | *Balance Sheet / Income Statement (F0708)* |
| **`S_ALR_87012277`** / **`S_PL0_86000030`** | G/L Account Balances (Trial Balance) | *Trial Balance (F0996)* |
| **`S_ALR_87012287`** | Document Journal | *Document Journal (S_ALR_87012287)* |
| **`S_ALR_87012289`** | Compact Document Journal | *Compact Document Journal* |
| **`S_ALR_87012291`** | Line Item Journal | *Line Item Journal* |
| **`S_ALR_87012326`** | Chart of Accounts List | *Manage Chart of Accounts (F0763A)* |
| **`S_ALR_87012357`** | Advance Return for Tax on Sales/Purchases | *Run Statutory Reports (F1515)* |

---

### 📙 Accounts Payable (`FI-AP`) & Bank Accounting (`FI-BL`)

#### Master Data
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`BP`** | Maintain Business Partner (Supplier Roles `FLVN00`/`FLVN01`) | *Manage Business Partner Master Data (F3163) / Maintain Business Partner (BP)* |
| **`FK01`** / **`FK02`** / **`FK03`** | Create / Change / Display Vendor (FI) *(Redirects to BP)* | *Manage Supplier Master Data (F1053A)* |
| **`XK01`** / **`XK02`** / **`XK03`** | Create / Change / Display Vendor (Central) *(Redirects to BP)* | *Manage Supplier Master Data (F1053A)* |
| **`FK05`** | Block / Unblock Vendor (Accounting) | *Manage Supplier Master Data (F1053A)* |
| **`FK06`** | Mark Vendor for Deletion | *Manage Supplier Master Data (F1053A)* |
| **`XK99`** | Mass Maintenance of Vendor Master Data | *Mass Maintenance of Business Partners* |
| **`FI01`** / **`FI02`** / **`FI03`** | Create / Change / Display Bank Key | *Manage Banks (F1574)* |
| **`FI12_HBANK`** | Maintain House Banks & Bank Accounts | *Manage Bank Accounts (F1366A)* |

#### Invoice & Credit Memo Entry
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FB60`** | Enter Vendor Invoice (Non-PO) | *Create Incoming Invoices (F0859)* |
| **`FB65`** | Enter Vendor Credit Memo (Non-PO) | *Create Incoming Invoices (F0859)* |
| **`F-43`** | Enter Vendor Invoice (General Header/Items) | *Create Incoming Invoices (F0859)* |
| **`F-41`** | Enter Vendor Credit Memo (General) | *Create Incoming Invoices (F0859)* |
| **`FV60`** | Park Vendor Invoice | *Park Incoming Invoices (F1683)* |
| **`FV65`** | Park Vendor Credit Memo | *Park Incoming Credit Memos* |
| **`MIRO`** | Enter Incoming Invoice (MM Logistics PO-Based) | *Create Supplier Invoice - Advanced (MIRO) / Create Supplier Invoice (F0859)* |
| **`MIR7`** | Park Incoming Logistics Invoice | *Create Supplier Invoice (F0859)* |
| **`MIR4`** | Display Logistics Invoice Document | *Manage Supplier Invoices (F1060A)* |
| **`MR8M`** | Cancel Logistics Invoice Document | *Manage Supplier Invoices (F1060A)* |
| **`MRBR`** | Release Blocked Invoices | *Release Blocked Invoices (MRBR) / Manage Supplier Invoices (F1060A)* |
| **`FB10`** | Invoice / Credit Memo Fast Entry | *Create Incoming Invoices (F0859)* |

#### Outgoing Payments, Down Payments & Clearing
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`F-53`** | Post Outgoing Payments (Manual) | *Post Outgoing Payments (F1612)* |
| **`F-58`** | Outgoing Payment with Printout / Check | *Post Outgoing Payments (F1612)* |
| **`F110`** | Automatic Payment Program (APP) | *Manage Automatic Payments (F0770)* |
| **`F-47`** | Down Payment Request (Vendor) | *Manage Supplier Down Payment Requests (F1689)* |
| **`F-48`** | Post Vendor Down Payment | *Post Outgoing Payments (F1612)* |
| **`F-54`** | Clear Vendor Down Payment | *Clear Outgoing Payments (F1367)* |
| **`F-44`** | Clear Vendor Account (Manual Clearing) | *Clear Outgoing Payments (F1367)* |
| **`F-51`** | Post with Clearing (Vendor) | *Clear Outgoing Payments (F1367)* |

#### Checks, Cash Journal & Bank Statements
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FCH1`** / **`FCH2`** | Display Check Information / Payment Document Checks | *Manage Outgoing Checks (F1578)* |
| **`FCH5`** | Create Check Information Manually | *Manage Outgoing Checks (F1578)* |
| **`FCH6`** | Change Check Information / Cash Check | *Manage Outgoing Checks (F1578)* |
| **`FCH3`** / **`FCH8`** / **`FCH9`** | Void Unused Check / Cancel Payment / Void Issued Check | *Manage Outgoing Checks (F1578)* |
| **`FCHN`** | Check Register | *Manage Outgoing Checks (F1578)* |
| **`FBCJ`** | Cash Journal (Petty Cash) | *Cash Journal (FBCJ)* |
| **`FF67`** | Manual Bank Statement | *Manage Bank Statements (F1564)* |
| **`FF_5`** | Import Electronic Bank Statement (EBS) | *Manage Incoming Payment Files (F1680) / Manage Bank Statements (F1564)* |
| **`FEBAN`** / **`FEB_BSPROC`** | Postprocessing Bank Statement | *Reprocess Bank Statement Items (F1520)* |

#### Reporting & Line Item Analysis
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FBL1N`** / **`FBL1H`** | Vendor Line Item Display / Browser | *Manage Supplier Line Items (F0712)* |
| **`FK10N`** | Vendor Balance Display | *Display Supplier Balances (F0701)* |
| **`S_ALR_87012077`** | Vendor Information System | *Overdue Payables (F1746) / Aging Analysis (F1733)* |
| **`S_ALR_87012078`** | Due Date Analysis for Open Items (AP Aging) | *Aging Analysis (F1733) / Future Payables (F1744)* |
| **`S_ALR_87012082`** | Vendor Balances in Local Currency | *Display Supplier Balances (F0701)* |
| **`S_ALR_87012083`** | List of Vendor Open Items for Printing | *Manage Supplier Line Items (F0712)* |
| **`S_ALR_87012086`** | Vendor List (Master Data Overview) | *Manage Supplier Master Data (F1053A)* |
| **`S_ALR_87012093`** | Vendor Business (Transaction Figures) | *Supplier Payment Analysis (F1750)* |
| **`S_P99_41000099`** | Payment List | *Manage Automatic Payments (F0770)* |
| **`S_P00_07000134`** | Generic Withholding Tax Reporting | *Run Statutory Reports - Withholding Tax (F1515)* |
| **`F.07`** | Carry Forward Payables / Receivables Balances | *Carry Forward Balances (F1596)* |

---

### 📗 Accounts Receivable (`FI-AR`) & Credit Management (`FSCM`)

#### Master Data
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`BP`** | Maintain Business Partner (Customer Roles `FLCU00`/`FLCU01`) | *Manage Business Partner Master Data (F3163) / Maintain Business Partner (BP)* |
| **`FD01`** / **`FD02`** / **`FD03`** | Create / Change / Display Customer (FI) *(Redirects to BP)* | *Manage Customer Master Data (F0850A)* |
| **`XD01`** / **`XD02`** / **`XD03`** | Create / Change / Display Customer (Central) *(Redirects to BP)* | *Manage Customer Master Data (F0850A)* |
| **`FD05`** | Block / Unblock Customer (Accounting) | *Manage Customer Master Data (F0850A)* |
| **`FD06`** | Mark Customer for Deletion | *Manage Customer Master Data (F0850A)* |
| **`XD99`** | Mass Maintenance of Customer Master Data | *Mass Maintenance of Business Partners* |
| **`UKM_BP`** | Credit Management Business Partner (Role `UKM000`) | *Manage Credit Accounts (F4596)* |

#### Invoice & Credit Memo Entry
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FB70`** | Enter Customer Invoice (Non-SD) | *Create Outgoing Invoices (FB70)* |
| **`FB75`** | Enter Customer Credit Memo (Non-SD) | *Create Outgoing Credit Memos (FB75)* |
| **`F-22`** | Enter Customer Invoice (General Header/Items) | *Create Outgoing Invoices (FB70)* |
| **`F-27`** | Enter Customer Credit Memo (General) | *Create Outgoing Credit Memos (FB75)* |
| **`FV70`** | Park Customer Invoice | *Park Outgoing Invoices (FV70)* |
| **`FV75`** | Park Customer Credit Memo | *Park Outgoing Credit Memos (FV75)* |
| **`VF01`** / **`VF02`** / **`VF03`** | Create / Change / Display Billing Document (SD Integration) | *Create Billing Documents (F0798) / Manage Billing Documents (F0797)* |
| **`VF11`** | Cancel Billing Document | *Manage Billing Documents (F0797)* |
| **`VFX3`** | Release Billing Documents for Accounting | *Manage Billing Document Requests / Release Billing Documents* |

#### Incoming Payments, Down Payments & Clearing
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`F-28`** | Post Incoming Payments | *Post Incoming Payments (F1345)* |
| **`F-26`** | Incoming Payments Fast Entry | *Post Incoming Payments (F1345)* |
| **`F-37`** | Customer Down Payment Request | *Manage Customer Down Payment Requests (F1688)* |
| **`F-29`** | Post Customer Down Payment | *Post Incoming Payments (F1345)* |
| **`F-39`** | Clear Customer Down Payment | *Clear Incoming Payments (F0773)* |
| **`F-32`** | Clear Customer Account (Manual Clearing) | *Clear Incoming Payments (F0773)* |
| **`F-30`** | Post with Clearing (Customer) | *Clear Incoming Payments (F0773)* |
| **`F-36`** | Bill of Exchange Payment | *Post Bill of Exchange Receivable* |

#### Dunning, Correspondence & Credit Control
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`F150`** | Dunning Run | *My Dunning Proposals (F2435) / Dunning Run (F150)* |
| **`F.27`** | Periodic Account Statements | *Create Correspondence (F0744)* |
| **`FB12`** | Request Correspondence | *Create Correspondence (F0744)* |
| **`F.64`** | Maintain CorrespondenceRequests | *Manage Correspondence* |
| **`VKM1`** / **`VKM4`** / **`UKM_CASE`** | Blocked SD Documents / Credit Cases Management | *Manage Documented Credit Decisions (F2541)* |
| **`UKM_MY_DCDS`** | My Documented Credit Decisions | *Manage Documented Credit Decisions (F2541)* |
| **`UDM_DISPUTE`** | Dispute Management | *Manage Dispute Cases (F0702A)* |

#### Reporting & Line Item Analysis
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FBL5N`** / **`FBL5H`** | Customer Line Item Display / Browser | *Manage Customer Line Items (F0711)* |
| **`FD10N`** | Customer Balance Display | *Display Customer Balances (F0703)* |
| **`S_ALR_87012167`** | Accounts Receivable Information System | *Overdue Receivables (F1747) / Total Receivables (F1748)* |
| **`S_ALR_87012168`** | Due Date Analysis for Open Items (AR Aging) | *Overdue Receivables (F1747) / Future Receivables (F1745)* |
| **`S_ALR_87012172`** | Customer Balances in Local Currency | *Display Customer Balances (F0703)* |
| **`S_ALR_87012173`** | List of Customer Open Items | *Manage Customer Line Items (F0711)* |
| **`S_ALR_87012179`** | Customer List (Master Data Overview) | *Manage Customer Master Data (F0850A)* |
| **`S_ALR_87012186`** | Customer Sales / Transaction Figures | *Customer Payment Analysis (F1749)* |
| **`UKM_COMMITMENTS`** | Credit Exposure / Commitments Display | *Analyze Credit Exposure (F2540)* |

---

### 📕 Asset Accounting (`FI-AA`)

#### Master Data
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`AS01`** | Create Asset Master Record | *Manage Fixed Assets (F3425)* |
| **`AS02`** | Change Asset Master Record | *Manage Fixed Assets (F3425)* |
| **`AS03`** | Display Asset Master Record | *Manage Fixed Assets (F3425)* |
| **`AS11`** | Create Asset Subnumber | *Manage Fixed Assets (F3425)* |
| **`AS05`** | Block Asset Master Record | *Manage Fixed Assets (F3425)* |
| **`AS06`** | Delete / Mark Asset for Deletion | *Manage Fixed Assets (F3425)* |
| **`AS91`** / **`AS92`** / **`AS93`** | Create / Change / Display Legacy Asset | *Manage Legacy Assets (F7280)* |
| **`ABLDT`** | Legacy Asset Transfer Values | *Post Transfer Values - For Legacy Asset* |

#### Asset Acquisitions, Transfers & Retirements
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`F-90`** | Asset Acquisition from Purchase with Vendor | *Post Asset Acquisition - With Vendor* |
| **`ABZON`** | Acquisition with Automatic Offsetting Entry | *Post Asset Acquisition - Integrated* |
| **`ABSO`** | Miscellaneous Asset Transactions | *Post Miscellaneous Asset Transactions* |
| **`ABUMN`** | Asset Transfer Within Company Code | *Post Asset Transfer - Within Company Code* |
| **`ABT1N`** | Intercompany Asset Transfer | *Post Intercompany Asset Transfer* |
| **`F-92`** | Asset Retirement from Sale with Customer | *Post Asset Retirement - With Customer* |
| **`ABAON`** | Asset Sale Without Customer | *Post Asset Retirement - Without Customer* |
| **`ABAVN`** | Asset Retirement by Scrapping | *Post Asset Retirement - By Scrapping (F7106)* |
| **`ABZU`** | Asset Write-Up | *Post Asset Write-Up* |
| **`ABAA`** | Unplanned Depreciation | *Post Unplanned Depreciation* |
| **`ABAW`** | Balance Sheet Revaluation | *Post Asset Revaluation (F7279)* |
| **`ABNK`** | Subsequent Costs / Revenues | *Post Subsequent Costs* |
| **`ABGL`** / **`ABGF`** | Enter Credit Memo in Year of Invoice / Following Year | *Post Credit Memo in Year of Invoice* |
| **`AB02`** / **`AB03`** | Change / Display Asset Document | *Manage Journal Entries (F0717)* |
| **`AB08`** | Reverse Asset Line Items | *Reverse Journal Entries* |

#### Asset Under Construction (AuC) & Periodic Processing
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`AIAB`** | Distribute Asset Under Construction (AuC) | *Distribute Asset Under Construction (AIAB)* |
| **`AIBU`** | Settle Asset Under Construction (AuC) | *Execute Settlement - For AuC (AIBU)* |
| **`AFAB`** | Execute Depreciation Run | *Schedule Asset Accounting Jobs (F1914) - DepreciationPostingRun* |
| **`AFAR`** | Recalculate Depreciation Values | *Schedule Asset Accounting Jobs (F1914) - RecalculateDepreciation* |
| **`FAA_CMP`** | Legacy Data Transfer & Fiscal Year Parameters | *Make Company Code Settings - Asset Accounting-Specific (F2670)* |
| **`AJAB`** | Asset Year-End Closing *(Obsolete/Via FAA_CMP in S/4HANA)* | *Make Company Code Settings - Asset Accounting-Specific (F2670)* |
| **`AJRW`** | Asset Fiscal Year Change *(Handled via FAGLGVTR in S/4HANA)* | *Carry Forward Balances (F1596)* |

#### Reporting & Asset Explorer
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`AW01N`** | Asset Explorer | *Asset Values (F1617) / Manage Fixed Assets (F3425)* |
| **`S_ALR_87011963`** / **`S_ALR_87011964`** | Asset Balances (by Asset Number / Asset Class) | *Asset Balances (F1616)* |
| **`S_ALR_87011990`** | Asset History Sheet | *Asset History Sheet (F1615)* |
| **`S_ALR_87012004`** | Total Depreciation | *Depreciation Lists (F2497)* |
| **`S_ALR_87012048`** | Asset Transactions | *Asset Transactions (F1618)* |
| **`S_ALR_87012050`** | Asset Acquisitions | *Asset Acquisitions* |
| **`S_ALR_87012052`** | Asset Retirements | *Asset Retirements* |
| **`S_ALR_87012936`** | Depreciation Simulation / Forecast | *Asset Depreciation Forecast* |

---

### 📒 Controlling (`CO`)

#### Cost Element & Cost Center Accounting (`CO-OM-CCA`)
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`FS00`** | Create / Change / Display Cost Elements *(Replaced `KA01`/`KA02`/`KA03`/`KA06` in S/4HANA)* | *Manage G/L Account Master Data (F0731A)* |
| **`KAH1`** / **`KAH2`** / **`KAH3`** | Create / Change / Display Cost Element Group | *Manage Cost Element Groups (F0764) / Manage Global Hierarchies (F2918)* |
| **`KS01`** / **`KS02`** / **`KS03`** | Create / Change / Display Cost Center | *Manage Cost Centers (F1443A)* |
| **`KS04`** | Delete Cost Center | *Manage Cost Centers (F1443A)* |
| **`KS12`** / **`KS13`** | Change / Display Cost Centers Collectively | *Manage Cost Centers (F1443A)* |
| **`OKEON`** | Change Standard Hierarchy (Cost Centers) | *Manage Global Hierarchies (F2918)* |
| **`KSH1`** / **`KSH2`** / **`KSH3`** | Create / Change / Display Cost Center Group | *Manage Cost Center Groups (F1563A)* |
| **`KL01`** / **`KL02`** / **`KL03`** | Create / Change / Display Activity Type | *Manage Activity Types (F1605A)* |
| **`KLH1`** / **`KLH2`** / **`KLH3`** | Create / Change / Display Activity Type Group | *Manage Activity Type Groups (F1577)* |
| **`KK01`** / **`KK02`** / **`KK03`** | Create / Change / Display Statistical Key Figure (SKF) | *Manage Statistical Key Figures (F1603A)* |
| **`KB11N`** / **`KB13N`** / **`KB14N`** | Enter / Display / Reverse Manual Reposting of Costs | *Reassign Costs and Revenues (F2009)* |
| **`KB21N`** / **`KB23N`** / **`KB24N`** | Enter / Display / Reverse Direct Activity Allocation | *Manage Direct Activity Allocation (F3696)* |
| **`KB31N`** / **`KB33N`** / **`KB34N`** | Enter / Display / Reverse Statistical Key Figures | *Manage Statistical Key Figure Values (F3772)* |
| **`KP06`** / **`KP07`** | Change / Display Cost Element / Activity Input Planning | *Import Financial Plan Data (F1711)* |
| **`KP26`** / **`KP27`** | Change / Display Activity Type / Price Planning | *Manage Cost Rates - Plan (F3162)* |
| **`KSII`** | Actual Activity Price Calculation | *Actual Cost Rate Calculation - Cost Centers (KSII)* |
| **`KSV1`** / **`KSV2`** / **`KSV3`** | Create / Change / Display Actual Distribution Cycle | *Manage Allocations (F3338A)* |
| **`KSV5`** | Execute Actual Distribution | *Run Allocations (F3548)* |
| **`KSU1`** / **`KSU2`** / **`KSU3`** | Create / Change / Display Actual Assessment Cycle | *Manage Allocations (F3338A)* |
| **`KSU5`** | Execute Actual Assessment | *Run Allocations (F3548)* |

#### Internal Orders (`CO-OM-OPA`)
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`KO01`** / **`KO02`** / **`KO03`** | Create / Change / Display Internal Order | *Manage Internal Orders (F1604A)* |
| **`KOH1`** / **`KOH2`** / **`KOH3`** | Create / Change / Display Internal Order Group | *Manage Internal Order Groups (F1606)* |
| **`KPF6`** / **`KPF7`** | Change / Display Internal Order Cost Element Planning | *Import Financial Plan Data (F1711)* |
| **`KO22`** / **`KO23`** | Change / Display Original Budget for Internal Order | *Manage Internal Order Budgets* |
| **`KO24`** / **`KO26`** | Change Supplement / Return Budget for Internal Order | *Manage Internal Order Budgets* |
| **`KO88`** / **`KO8G`** | Actual Settlement: Individual / Collective Internal Orders | *Run Settlement - Actual (F4568)* |

#### Profit Center Accounting (`EC-PCA` / `FI-GL`) & Profitability Analysis (`CO-PA`)
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`KE51`** / **`KE52`** / **`KE53`** | Create / Change / Display Profit Center | *Manage Profit Centers (F3516)* |
| **`KE54`** | Delete Profit Center | *Manage Profit Centers (F3516)* |
| **`KCH1`** / **`KCH2`** / **`KCH3`** | Create / Change / Display Profit Center Group | *Manage Profit Center Groups (F0765)* |
| **`KCH5N`** / **`KCH6N`** | Change / Display Profit Center Standard Hierarchy | *Manage Global Hierarchies (F2918)* |
| **`9KE0`** / **`1KEF`** | Profit Center Document Entry / Control Parameters | *Post General Journal Entries (F0718)* |
| **`KE21N`** / **`KE24`** | Create CO-PA Line Item / Display Actual Line Items | *Market Segments - Actuals (F0943A)* |
| **`KE30`** | Execute Profitability Report | *Market Segments - Plan/Actual (F0926A)* |

#### Product Costing (`CO-PC`) & Material Ledger (`CO-PC-ACT`)
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`MM01`** / **`MM02`** / **`MM03`** | Create / Change / Display Material Master (Accounting/Costing Views) | *Manage Product Master Data (F1602)* |
| **`CS01`** / **`CS02`** / **`CS03`** | Create / Change / Display Bill of Materials (BOM) | *Maintain Bill of Material (F1813)* |
| **`CA01`** / **`CA02`** / **`CA03`** | Create / Change / Display Routing | *Manage Routings* |
| **`CR01`** / **`CR02`** / **`CR03`** | Create / Change / Display Work Center | *Manage Work Centers* |
| **`CK11N`** / **`CK13N`** | Create / Display Material Cost Estimate with Quantity Structure | *Create Material Cost Estimates (CK11N) / Manage Material Cost Estimates (F4062)* |
| **`CK24`** | Price Update: Mark & Release Standard Cost Estimate | *Release Material Cost Estimates (F4063)* |
| **`CK40N`** | Edit Costing Run (Mass Costing) | *Manage Costing Runs - Estimated Costs (F1865)* |
| **`MR21`** | Material Price Change | *Change Material Costs (MR21)* |
| **`MR22`** | Material Debit / Credit | *Material Debit/Credit (MR22)* |
| **`CKM3`** / **`CKM3N`** | Material Price Analysis (Material Ledger) | *Material Price Analysis (CKM3N)* |
| **`CKMLCP`** | Material Ledger Costing Cockpit: Actual Costing Run | *Edit Actual Costing Runs (F3671)* |
| **`KKAX`** / **`KKAO`** | Calculate Work in Process (WIP): Individual / Collective | *Run WIP Calculation / Event-Based Production Cost Posting (F3957)* |
| **`KKS2`** / **`KKS1`** | Calculate Production Variances: Individual / Collective | *Run Variance Calculation* |
| **`KO88`** / **`CO88`** | Actual Settlement: Production / Process Orders | *Run Settlement - Actual (F4568)* |

#### Controlling Reporting & Line Item Analysis
| T-Code | Description | Equivalent S/4HANA Fiori App |
| :--- | :--- | :--- |
| **`KSB1`** | Cost Centers: Actual Line Items | *Display Line Items - Cost Accounting (F4023)* |
| **`KSB5`** | Controlling Documents: Actual Costs | *Display Line Items - Cost Accounting (F4023)* |
| **`S_ALR_87013611`** | Cost Centers: Actual / Plan / Variance | *Cost Centers - Plan/Actual (F0949A)* |
| **`S_ALR_87013612`** | Range: Cost Centers | *Cost Centers - Actuals (F0940A)* |
| **`S_ALR_87013613`** | Range: Cost Elements | *Cost Centers - Plan/Actual (F0949A)* |
| **`S_ALR_87013614`** | Cost Centers: Current Period / Cumulative | *Cost Centers - Plan/Actual (F0949A)* |
| **`S_ALR_87013623`** | Cost Centers: Quarterly Comparison | *Cost Centers - Plan/Actual (F0949A)* |
| **`KOB1`** | Orders: Actual Line Items | *Display Line Items - Cost Accounting (F4023)* |
| **`S_ALR_87012993`** | Orders: Actual / Plan / Variance | *Internal Orders - Plan/Actual (F0948A)* |
| **`S_ALR_87013019`** | List: Budget / Actual / Commitments for Orders | *Internal Orders - Actuals (F0939A)* |
| **`KE5Z`** | Profit Center: Actual Line Items | *Profit Centers - Actuals (F0945A)* |
| **`S_ALR_87013326`** | Profit Center Group: Plan / Actual / Variance | *Profit Centers - Plan/Actual (F0929A)* |
| **`S_ALR_87013127`** | Order Selection (Product Cost by Order Analysis) | *Production Cost Analysis (F1780)* |
| **`KKBC_ORD`** | Analyze Production Order Costs | *Analyze Costs by Work Center/Operation (F3331)* |
| **`KKBC_HOE`** | Analyze Product Cost Summarization Hierarchy | *Production Cost Analysis (F1780)* |

---

> [!NOTE]
> Transaction codes and Fiori App IDs can vary depending on the SAP S/4HANA release version, active business functions, and whether Universal Journal (`ACDOCA`), Margin Analysis, or Event-Based Production Cost Posting is enabled in the environment.