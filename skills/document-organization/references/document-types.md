# Document Type Classification Guide

Complete reference for identifying and classifying documents received by the CA firm.

## Financial Documents

### Bank Statements
- **Identifiers:** "Statement of Account", "Account Summary", bank logo, transaction list with debit/credit columns, opening/closing balance
- **Common formats:** PDF, Excel
- **Naming keyword:** Bank Statement
- **Period:** Usually monthly or quarterly — extract from statement header

### Sales Invoices / Sales Bills
- **Identifiers:** "Tax Invoice", "Invoice", seller's GSTIN, buyer details, HSN/SAC codes, IGST/CGST/SGST breakup, invoice number
- **Common formats:** PDF, image (photo of physical invoice)
- **Naming keyword:** Sales Invoice
- **Period:** Use invoice date's month

### Purchase Invoices / Purchase Bills
- **Identifiers:** Same as sales invoice but the client is the BUYER (client's name/GSTIN appears in "Bill To" or "Ship To")
- **Common formats:** PDF, image
- **Naming keyword:** Purchase Invoice
- **Period:** Use invoice date's month

### Credit Notes / Debit Notes
- **Identifiers:** "Credit Note", "Debit Note", reference to original invoice
- **Naming keyword:** Credit Note or Debit Note
- **Period:** Use note date's month

## Tax Documents

### TDS Certificates
- **Form 16:** Salary TDS certificate — "Certificate under Section 203 of the Income-tax Act, 1961 for Tax deducted at source on Salary"
- **Form 16A:** Non-salary TDS certificate — similar header but for non-salary payments
- **Form 26AS / AIS:** Annual tax statement from TRACES
- **Identifiers:** TRACES logo, TAN of deductor, PAN of deductee, quarter reference (Q1/Q2/Q3/Q4)
- **Naming keyword:** TDS Certificate or Form 16 or Form 16A
- **Period:** Quarter-based (Q1 Apr-Jun, Q2 Jul-Sep, Q3 Oct-Dec, Q4 Jan-Mar) + Financial Year

### GST Returns
- **GSTR-1:** Outward supplies return
- **GSTR-3B:** Summary return with tax payment
- **GSTR-2A/2B:** Auto-populated inward supplies
- **GSTR-9:** Annual return
- **Identifiers:** "Goods and Services Tax" header, GSTIN, return period, ARN number
- **Naming keyword:** GSTR-1, GSTR-3B, GSTR-2B, etc.
- **Period:** Monthly or quarterly + Financial Year

### Income Tax Returns / Forms
- **ITR-1 to ITR-7:** Various income tax return forms
- **Form 26AS:** Annual tax credit statement
- **AIS (Annual Information Statement)**
- **Computation of Income**
- **Identifiers:** "Income Tax Department", PAN, Assessment Year, "Return of Income"
- **Naming keyword:** ITR or specific form name
- **Period:** Assessment Year (AY 2026-27 = FY 2025-26)

### Advance Tax Challans
- **Identifiers:** "Challan No. 280", BSR code, challan serial number, PAN
- **Naming keyword:** Advance Tax Challan
- **Period:** Quarter + Financial Year

## Compliance Documents

### ROC / MCA Documents
- **Identifiers:** "Ministry of Corporate Affairs", CIN, DIN, Form AOC-4, MGT-7, DIR-3 KYC
- **Naming keyword:** Use form name (e.g., AOC-4, MGT-7)
- **Period:** Financial Year

### PAN Card / Aadhaar / Identity Documents
- **Identifiers:** "Income Tax Department", "UIDAI", photo ID
- **Naming keyword:** PAN Card, Aadhaar, ID Document
- **Period:** N/A (use "Current")

## Business Documents

### Rent Agreements / Lease Deeds
- **Identifiers:** "Rent Agreement", "Lease Deed", lessor/lessee details, monthly rent amount
- **Naming keyword:** Rent Agreement
- **Period:** Agreement validity period

### Loan Documents / Loan Statements
- **Identifiers:** Bank/NBFC letterhead, loan account number, EMI schedule, interest certificate
- **Naming keyword:** Loan Statement or Interest Certificate
- **Period:** Financial Year or statement period

### Partnership Deed / Company Documents
- **Identifiers:** "Partnership Deed", "Memorandum of Association", "Articles of Association"
- **Naming keyword:** Use document title
- **Period:** N/A or date of execution

## Other Documents

### Notices
- **Identifiers:** "Notice", reference number, from government department (Income Tax, GST, ROC)
- **Naming keyword:** Notice - [Department] (e.g., Notice - GST, Notice - Income Tax)
- **Period:** Date of notice

### Correspondence / Letters
- **Identifiers:** Formal letter format, addressed to/from the client
- **Naming keyword:** Letter or Correspondence
- **Period:** Date of letter

### Miscellaneous
- Anything that doesn't fit the above categories
- **Naming keyword:** Miscellaneous + brief descriptor
- **Period:** Best available date

## Classification Decision Tree

Is it a bank/financial statement? → Bank Statement
Is it an invoice? → Client is seller? → Sales Invoice / Client is buyer? → Purchase Invoice
Does it mention TDS/Form 16? → TDS Certificate
Does it mention GST/GSTR? → GST Return (use specific form number)
Does it mention Income Tax/ITR? → Income Tax Return
Does it mention ROC/MCA/CIN? → ROC Document
Is it a notice from government? → Notice - [Department]
Is it a loan/interest document? → Loan Statement
Is it an identity document? → ID Document
None of the above? → Miscellaneous
