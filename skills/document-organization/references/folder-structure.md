# Folder Structure Reference

The CA firm's document storage follows a strict 3-level hierarchy. Every document must be filed into this exact structure.

## Hierarchy

Root (Google Drive or Local Storage)
  └── [Client Name]                    ← Level 1: Client
      └── [Financial Year]             ← Level 2: FY (e.g., 2025-26)
          ├── Bank Statements          ← Level 3: Work Type
          ├── Sales
          ├── Purchase
          ├── TDS
          ├── GST
          ├── Income Tax
          ├── Audit
          ├── ROC
          ├── Notices
          └── Miscellaneous

## Level 1: Client Name

- Use the client's official short name as known by the firm
- Must match the existing folder name exactly (case-sensitive)
- If no folder exists for a new client, ask the user before creating one
- Examples: Sharma Enterprises, Gupta Traders, Patel & Co, Mehta Industries

## Level 2: Financial Year

- Format: YYYY-YY (e.g., 2025-26)
- Indian Financial Year runs April 1 to March 31
- Determining FY from a date:
  - January 2026 → FY 2025-26 (because it's before March 31, 2026)
  - April 2026 → FY 2026-27 (new FY starts)
  - March 2026 → FY 2025-26 (still the same FY)
- For documents spanning multiple FYs, file under the FY they primarily belong to
- Assessment Year (AY) is FY + 1: AY 2026-27 = FY 2025-26

## Level 3: Work Type Folders

### Document Type to Folder Mapping

| Document Type | Target Folder | Notes |
|---|---|---|
| Bank Statement | Bank Statements | All banks, all account types |
| Sales Invoice / Sales Bill | Sales | Outward supply documents |
| Purchase Invoice / Purchase Bill | Purchase | Inward supply documents |
| Credit Note (sales) | Sales | Filed with sales documents |
| Debit Note (purchase) | Purchase | Filed with purchase documents |
| TDS Certificate (Form 16/16A) | TDS | All TDS-related docs |
| Form 26AS / AIS | TDS | Annual tax credit statements |
| Advance Tax Challan | TDS | Tax payment receipts |
| TDS Return Filing Acknowledgment | TDS | Return confirmations |
| GSTR-1 | GST | Outward supply return |
| GSTR-3B | GST | Summary return |
| GSTR-2A / GSTR-2B | GST | Inward supply auto-populated |
| GSTR-9 / GSTR-9C | GST | Annual return / reconciliation |
| GST Registration Certificate | GST | GSTIN certificate |
| E-way Bill | GST | Transport documents |
| ITR (any form) | Income Tax | All income tax returns |
| Computation of Income | Income Tax | Tax computation sheets |
| Tax Audit Report | Audit | Section 44AB audit |
| Statutory Audit Report | Audit | Company audit reports |
| Balance Sheet / P&L | Audit | Financial statements |
| Trial Balance | Audit | Or Miscellaneous if working paper |
| AOC-4, MGT-7, DIR-3 KYC | ROC | MCA/ROC filings |
| Company incorporation docs | ROC | MOA, AOA, COI |
| Income Tax Notice | Notices | IT department notices |
| GST Notice | Notices | GST department notices |
| ROC Notice | Notices | MCA notices |
| Any other notice | Notices | Government correspondence |
| Rent Agreement | Miscellaneous | Unless specific folder exists |
| Loan Statement | Miscellaneous | Unless specific folder exists |
| PAN / Aadhaar / ID docs | Miscellaneous | Identity documents |
| Partnership Deed | Miscellaneous | Entity documents |
| Anything unclassified | Miscellaneous | When in doubt, ask user |

### Creating New Subfolders

- **Never** create a new work type folder without user approval
- If a client has a unique need (e.g., a Payroll folder), the user will specify it
- Standard folders listed above should cover 95%+ of documents

## Example: Complete Filing Path

**Document:** A bank statement from HDFC Bank for Sharma Enterprises covering April 2025 to June 2025

Rename: "Sharma Enterprises - Bank Statement - Apr to Jun 2025.pdf"
Path: Sharma Enterprises / 2025-26 / Bank Statements / Sharma Enterprises - Bank Statement - Apr to Jun 2025.pdf

**Document:** GSTR-3B return for Gupta Traders for March 2026

Rename: "Gupta Traders - GSTR-3B - Mar 2026.pdf"
Path: Gupta Traders / 2025-26 / GST / Gupta Traders - GSTR-3B - Mar 2026.pdf

**Document:** Income Tax Notice for Patel & Co dated January 2026

Rename: "Patel & Co - Notice - Income Tax - Jan 2026.pdf"
Path: Patel & Co / 2025-26 / Notices / Patel & Co - Notice - Income Tax - Jan 2026.pdf

## Financial Year Quick Reference (India)

| Period | Financial Year | Assessment Year |
|---|---|---|
| Apr 2024 - Mar 2025 | 2024-25 | 2025-26 |
| Apr 2025 - Mar 2026 | 2025-26 | 2026-27 |
| Apr 2026 - Mar 2027 | 2026-27 | 2027-28 |
