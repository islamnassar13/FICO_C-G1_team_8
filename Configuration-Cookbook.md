# 🏛️ SAP S/4HANA Finance (FICO) Enterprise Implementation Blueprint

A comprehensive, production-grade repository documenting full-cycle SAP S/4HANA Finance configurations, enterprise structure mapping, SPRO implementation paths, end-to-end business scenarios, and consulting best practices.

---

## 🎯 Repository Overview & Architecture Roadmap

### 1. Enterprise Structure & Global Settings
- Company Code, Controlling Area & Segment Setup
- Fiscal Year Variants (FYV) & Posting Period Variants (PPV)
- Currency Management (Direct vs. Indirect Quotation, Translation Ratios)
- Field Status Variants (FSV) & Document Types (`OBA7`)

### 2. General Ledger Accounting (FI-GL) & Universal Journal
- Universal Journal (`ACDOCA`) Architecture & Extensibility
- Chart of Accounts (Operational, Country, Group)
- Document Splitting Rules (Business Transactions & Variants)
- Leading Ledger (`0L`) & Non-Leading / Extension Ledgers

### 3. Business Partner (BP) & Customer/Vendor Integration (CVI)
- BP Groupings, Number Ranges, and Synchronization
- Roles Architecture (`000000`, `FLCU00`, `FLCU01`, `FLVN00`, `FLVN01`)
- Reconciliation Account Mechanics & Subledger Postings
- Multi-Company Extensions & Customer-Vendor Clearing

---

## 🛠️ Step-by-Step Baseline Configuration Guide (With SPRO Paths)

### 1. Enterprise Structure & Master Definitions

#### Step 1: Define Company Code
* **T-Code:** `OX02`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Enterprise Structure -> Definition -> Financial Accounting -> Edit, Copy, Delete, Check Company Code`
* **Action:** Enter Company Code (4 characters), Legal Name, City, Country (`EG`), Currency (`EGP`), and Language (`EN`/`AR`).

#### Step 2: Define Segment (S/4HANA Standard for Segment Reporting)
* **T-Code:** `SPRO` (Table `V_FAGL_SEGM`)
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Enterprise Structure -> Definition -> Financial Accounting -> Define Segment`
* **Action:** Define 10-character Segment codes and descriptions for IFRS 8 reporting (replaces legacy Business Areas `OX03`).

#### Step 3: Define Chart of Accounts (COA)
* **T-Code:** `OB13`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> General Ledger Accounting -> Master Data -> G/L Accounts -> Preparations -> Edit Chart of Accounts List`
* **Action:** Define operational COA code, description, maintenance language, and length of G/L account numbers (standard: 6 to 8 digits).

#### Step 4: Assign Chart of Accounts to Company Code
* **T-Code:** `OB62`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> General Ledger Accounting -> Master Data -> G/L Accounts -> Preparations -> Assign Company Code to Chart of Accounts`
* **Action:** Link the operational COA to the target Company Code.

#### Step 5: Define Account Groups
* **T-Code:** `OBD4`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> General Ledger Accounting -> Master Data -> G/L Accounts -> Preparations -> Define Account Group`
* **Action:** Create account groups (Assets, Liabilities, Equity, Revenues, Expenses) and define the technical number intervals for each category.

#### Step 6: Define Retained Earnings Account
* **T-Code:** `OB53`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> General Ledger Accounting -> Master Data -> G/L Accounts -> Preparations -> Define Retained Earnings Account`
* **Action:** Enter P&L statement account type (`X`) and assign the target Retained Earnings G/L account for year-end carryforward.

---

### 2. Fiscal Controls & Posting Rules

#### Step 7: Maintain Fiscal Year Variant (FYV)
* **T-Code:** `OB29`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Ledgers -> Fiscal Year and Posting Periods -> Maintain Fiscal Year Variant`
* **Action:** Define calendar year (`K4`) or non-calendar year structure with normal posting periods (12) and special periods (4 for audits/adjustments).

#### Step 8: Assign Fiscal Year Variant to Company Code
* **T-Code:** `OB37`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Ledgers -> Fiscal Year and Posting Periods -> Assign Company Code to a Fiscal Year Variant`
* **Action:** Assign the target FYV to the Company Code.

#### Step 9: Define Variants for Open Posting Periods (PPV)
* **T-Code:** `OBBO`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Ledgers -> Fiscal Year and Posting Periods -> Posting Periods -> Define Variants for Open Posting Periods`
* **Action:** Define a 4-character identifier representing the posting period container.

#### Step 10: Assign Posting Period Variant to Company Code
* **T-Code:** `OBBP`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Ledgers -> Fiscal Year and Posting Periods -> Posting Periods -> Assign Variants to Company Code`
* **Action:** Link the PPV to the Company Code.

#### Step 11: Open and Close Posting Periods
* **T-Code:** `OB52`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Ledgers -> Fiscal Year and Posting Periods -> Posting Periods -> Open and Close Posting Periods`
* **Action:** Maintain authorized posting intervals across account types (`+`, `A`, `D`, `K`, `M`, `S`).

#### Step 12: Define Field Status Variants (FSV)
* **T-Code:** `OBC4`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Ledgers -> Fields -> Define Field Status Variants`
* **Action:** Define field attributes (Suppress, Required, Optional) across field status groups for transaction line items.

#### Step 13: Assign Field Status Variant to Company Code
* **T-Code:** `OBC5`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Ledgers -> Fields -> Assign Company Code to Field Status Variants`
* **Action:** Link the configured FSV to the Company Code.

#### Step 14: Define Tolerance Groups for G/L Accounts & Employees
* **T-Codes:** `OBA0` (G/L Accounts) & `OBA4` (Employees)
* **SPRO Path (OBA0):** `SPRO -> SAP Reference IMG -> Financial Accounting -> General Ledger Accounting -> Business Transactions -> Open Item Clearing -> Clearing Differences -> Define Tolerance Groups for G/L Accounts`
* **SPRO Path (OBA4):** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Document -> Tolerance Groups -> Define Tolerance Groups for Employees`
* **Action:** Define maximum document amounts, open-item payment differences, and cash discount limits for users.

#### Step 15: Define Document Types and Number Ranges
* **T-Codes:** `OBA7` (Doc Types) & `FBN1` (Number Ranges)
* **SPRO Path (OBA7):** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Document -> Document Types -> Define Document Types for Entry View`
* **SPRO Path (FBN1):** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Document -> Document Number Ranges -> Documents in Entry View -> Define Document Number Ranges for Entry View`
* **Action:** Configure document types (`SA`, `KR`, `DR`, `KZ`, `DZ`) and initialize annual intervals per Company Code.

#### Step 16: Global Parameters Verification
* **T-Code:** `OBY6`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> Financial Accounting Global Settings -> Global Parameters for Company Code -> Enter Global Parameters`
* **Action:** Review integrated parameters (COA, FYV, PPV, FSV, Tax settings, Negative Postings Permitted).

---

### 3. S/4HANA Master Data & Controlling (CO)

#### Step 17: Maintain Controlling Area & Activate Components
* **T-Code:** `OKKP`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Controlling -> General Controlling -> Organization -> Maintain Controlling Area`
* **Action:** Establish Controlling Area, set currency type, assign COA and FYV, activate components (Cost Centers, Profit Center Accounting, Projects), and link the Company Code.

#### Step 18: Maintain Number Ranges for Controlling Documents
* **T-Code:** `KANK`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Controlling -> General Controlling -> Organization -> Maintain Number Ranges for Controlling Documents`
* **Action:** Assign CO business transactions (`COIN`, `RKU1`, etc.) to number range groups.

#### Step 19: Create G/L Accounts & Cost Elements (S/4HANA Unified Approach)
* **T-Code:** `FS00`
* **SAP Easy Access Path:** `SAP Menu -> Accounting -> Financial Accounting -> General Ledger -> Master Records -> G/L Accounts -> Individual Processing -> Centrally`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> General Ledger Accounting -> Master Data -> G/L Accounts -> G/L Account Creation and Processing -> Edit G/L Account (Individual Processing) -> Edit G/L Accounts Centrally`
* **Action:** Create G/L accounts. In S/4HANA, Primary & Secondary Cost Elements are created directly inside `FS00` via **G/L Account Type** (`X` - Balance Sheet, `N` - Non-operating Exp/Inc, `P` - Primary Cost/Revenue, `S` - Secondary Cost).

#### Step 20: Define Standard Hierarchy & Create Profit Centers
* **T-Codes:** `KCH1` (Hierarchy) & `KE51` (Profit Center)
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Financial Accounting -> General Ledger Accounting -> Master Data -> Profit Center -> Define Standard Hierarchy / Create Profit Center`
* **SAP Easy Access Path:** `SAP Menu -> Accounting -> Financial Accounting -> General Ledger -> Master Records -> Profit Center -> Individual Processing -> Create`
* **Action:** Create Profit Centers, assign them to the standard hierarchy, link each to its corresponding **Segment**, and set status to Active (`Ctrl+F2`).

#### Step 21: Set Up Cost Centers
* **T-Code:** `KS01`
* **SAP Easy Access Path:** `SAP Menu -> Accounting -> Controlling -> Cost Center Accounting -> Master Data -> Cost Center -> Individual Processing -> Create`
* **Action:** Define Cost Center, validity period, Cost Center Category, person responsible, and attach to Standard Hierarchy and Profit Center.

---

### 4. Cross-Module Integration & Governance

#### Step 22: Business Partner (BP) & CVI Synchronization Setup
* **T-Code:** `SPRO` / `MDS_LINKS`
* **SPRO Path:** `SPRO -> SAP Reference IMG -> Cross-Application Components -> Master Data Synchronization -> Customer/Vendor Integration -> Business Partner Settings -> Settings for Customer/Vendor Integration`
* **Action:** Map BP Groupings and Number Ranges to FI Customer/Vendor Account Groups.

#### Step 23: Cross-Module Automatic Account Determination
* **MM-FI Integration (`OBYC`):**
  * **SPRO Path:** `SPRO -> SAP Reference IMG -> Materials Management -> Valuation and Account Assignment -> Account Determination -> Account Determination Without Wizard -> Configure Automatic Postings`
  * **Action:** Configure Valuation Class mappings for `BSX` (Inventory), `WRX` (GR/IR Clearing), `GBB` (Offsetting Entry), and `PRD` (Price Differences).
* **SD-FI Integration (`VKOA`):**
  * **SPRO Path:** `SPRO -> SAP Reference IMG -> Sales and Distribution -> Basic Functions -> Account Assignment/Costing -> Revenue Account Determination -> Assign G/L Accounts`
  * **Action:** Map Customer Account Assignment Group, Material Group, and Account Keys (`ERL`, `ERS`, `MWS`) to G/L accounts.

#### Step 24: Audit Verification & SoD Compliance
* **T-Code:** `PFCG` (Role Maintenance)
* **SPRO Path:** `SPRO -> SAP Reference IMG -> SAP NetWeaver -> Application Server -> System Administration -> Users and Authorizations -> Maintain Authorizations and Profiles using Profile Generator`
* **Action:** Validate transaction security using authorization objects (`F_BKPF_BLA` for Document Types, `F_BKPF_BUK` for Company Codes).

---

## 🔄 Configuration Sequence Architecture

```mermaid
flowchart TD
    subgraph Enterprise_Setup [1. Enterprise Structure]
        A[Define Company Code: OX02] --> B[Define Segment: SPRO]
        B --> C[Define Chart of Accounts: OB13]
        C --> D[Assign COA to CoCode: OB62]
        D --> E[Account Groups & Retained Earnings: OBD4 / OB53]
    end

    subgraph Ledger_Control [2. Global & Ledger Controls]
        F[Fiscal Year Variant: OB29 / OB37] --> G[Posting Period Variant: OBBO / OBBP / OB52]
        G --> H[Field Status Variant: OBC4 / OBC5]
        H --> I[Tolerance Groups: OBA0 / OBA4]
        I --> J[Doc Types & Ranges: OBA7 / FBN1]
        J --> K[Global Parameters Review: OBY6]
    end

    subgraph Core_Posting [3. Controlling & Master Data]
        L[Controlling Area & Ranges: OKKP / KANK] --> M[Profit Centers: KE51]
        M --> N[Cost Centers: KS01]
        N --> O[Unified G/L & Cost Elements: FS00]
    end

    subgraph Integration_Gov [4. Integration & Governance]
        P[BP & CVI Sync: SPRO] --> Q[MM-FI & SD-FI: OBYC / VKOA]
        Q --> R[Security & SoD: PFCG]
    end

    Enterprise_Setup
