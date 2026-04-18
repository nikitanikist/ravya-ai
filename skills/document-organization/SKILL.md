---
name: document-organization
description: >
  Scan Gmail and WhatsApp for incoming client documents, download attachments,
  classify document type, rename with standard convention, and file into the
  correct client folder. Use when the user says "organize documents",
  "scan for new documents", "check Gmail for attachments", "file client documents",
  "download and organize", "process incoming documents", "run DocFlow",
  "document organization", or any request about collecting, renaming, or filing
  CA firm client documents from email or WhatsApp.
metadata:
  version: "0.1.0"
  agent: "DocFlow (A1)"
  phase: "Phase 1"
---

# Document Organization — DocFlow Agent

This skill automates the complete document collection and filing workflow for the CA firm. It monitors Gmail and WhatsApp, downloads attachments, classifies them, renames them with the firm's standard naming convention, and files them into the correct client folder hierarchy.

## Critical Guardrails

Before doing ANYTHING, remember these non-negotiable rules from the client:

1. **NO portal access** — Never log into any government portal (GST, Income Tax, TDS, MCA). READ-ONLY monitoring of Gmail and WhatsApp only.
2. **NO client contact** — Never send any message, email, or communication to any client. Only organize documents that have already been received.
3. **Human approval before filing** — Always present the proposed rename and folder placement to the user for approval before actually moving/saving the file.
4. **Modular tools** — Don't hardcode to any specific software. The firm may switch tools. Use whatever file storage MCP or Google Drive is connected.

## Workflow Steps

### Step 1: Scan for Incoming Documents

Check these sources for new documents:

**Gmail scanning (via Claude in Chrome):**
1. Open Gmail in Chrome
2. Search for recent emails with attachments from known clients
3. Use search operators: \`has:attachment newer_than:1d\` (or the period the user specifies)
4. For each email with attachments, extract:
   - Sender name and email address
   - Subject line
   - Attachment file names
   - Date received

**WhatsApp scanning (via Claude in Chrome):**
1. Open WhatsApp Web in Chrome
2. Check recent messages in client groups and individual chats
3. Look for shared documents, images of documents, PDFs, Excel files
4. For each document found, note:
   - Sender name
   - Group/chat name
   - File name
   - Date shared

Present a summary table to the user:

| # | Source   | From          | Document        | Date       |
|---|----------|---------------|-----------------|------------|
| 1 | Gmail    | sharma@...    | bank_stmt.pdf   | 2026-04-18 |
| 2 | WhatsApp | Gupta Group   | sales_apr.xlsx  | 2026-04-18 |

Ask the user: "I found these documents. Which ones should I process? (all / specific numbers)"

### Step 2: Download Documents

For approved documents:
- Download each attachment from Gmail or WhatsApp
- Save temporarily to the working directory
- If a document is an image (photo of a physical document), note this — it may need OCR later

### Step 3: Classify Each Document

Read/analyze each downloaded document to determine:

**A. Document Type** — What kind of document is this?

Refer to \`references/document-types.md\` for the full classification list. Common types:
- Bank Statement
- Sales Invoice / Sales Bill
- Purchase Invoice / Purchase Bill
- TDS Certificate (Form 16/16A)
- GST Return (GSTR-1, GSTR-3B, etc.)
- Income Tax Return / Form
- Audit Report
- Balance Sheet / Financial Statement
- PAN Card / Aadhaar (identity documents)
- Loan Statement
- Rent Agreement
- Miscellaneous

**B. Client Identification** — Which client does this belong to?

Match using:
- Sender email address → known client email
- WhatsApp sender/group name → known client
- Content of the document (business name, PAN, GSTIN)
- If unclear, ASK the user: "I couldn't identify the client for [filename]. Which client does this belong to?"

**C. Period Detection** — What financial period does this cover?

Look for:
- Date ranges in the document (e.g., "April 2025 to March 2026")
- Statement period headers
- Invoice dates
- Financial year references (FY 2025-26)
- If single-date document (like an invoice), use that date's financial year
- If unclear, ASK the user

### Step 4: Rename with Standard Convention

Apply the firm's naming convention:

**Format:** \`[Client Name] - [Document Type] - [Period]\`

**Examples:**
- \`Sharma Enterprises - Bank Statement - Apr 2025 to Mar 2026.pdf\`
- \`Gupta Traders - Sales Invoice - Jan 2026.pdf\`
- \`Patel & Co - TDS Certificate - Q3 FY2025-26.pdf\`
- \`Mehta Industries - GSTR-3B - Mar 2026.pdf\`

**Rules:**
- Client name: Use the official short name from the client list
- Document type: Use standardized type names (see references/document-types.md)
- Period: Use the most specific period available (month, quarter, or full FY)
- File extension: Keep the original extension (.pdf, .xlsx, .jpg, etc.)

### Step 5: Determine Folder Path

Build the correct folder path using the 3-level hierarchy:

[Client Name] / [Financial Year] / [Work Type Folder]

**Level 1 — Client Name:** Match to existing client folder
**Level 2 — Financial Year:** Format as YYYY-YY (e.g., 2025-26)
**Level 3 — Work Type:** Map document type to the correct subfolder

Refer to \`references/folder-structure.md\` for the complete folder mapping.

Quick reference:
| Document Type | Folder Name |
|---|---|
| Bank Statement | Bank Statements |
| Sales Invoice | Sales |
| Purchase Invoice | Purchase |
| TDS Certificate / TDS Return | TDS |
| GST Return / GST Invoice | GST |
| Income Tax Return / IT Forms | Income Tax |
| Audit Report / Financial Statement | Audit |
| Everything else | Miscellaneous |

### Step 6: Present for Approval

**ALWAYS** present the complete plan before filing.

### Step 7: Execute Filing

Only after user approval:
1. Rename the file
2. Check if the target folder exists — if not, create it
3. Move/copy the file to the correct location
4. Confirm each file was filed successfully

Use whichever file storage is connected:
- If Google Drive MCP is available → use Google Drive tools
- If local filesystem → use file tools
- If another storage MCP → adapt accordingly

### Step 8: Summary Report

After all documents are filed, present a summary with processed count, success count, errors, and a table.

## Handling Edge Cases

- **Unknown client:** Ask the user. Never guess.
- **Duplicate document:** Warn the user: "This file appears to already exist at [path]. Skip or replace?"
- **Unreadable document:** Flag it: "I couldn't read [filename]. It may need manual review."
- **Multiple clients in one email:** Process each attachment separately, ask for client mapping if needed.
- **No period found:** Ask the user to specify the period.
- **New folder needed:** Inform the user before creating: "The folder [path] doesn't exist yet. Create it?"

## Tool Usage

- **Claude in Chrome** (mcp__Claude_in_Chrome__*): For scanning Gmail and WhatsApp Web
- **Google Drive MCP**: For searching, creating folders, and uploading files (if connected)
- **Read tool**: For reading downloaded document contents
- **Agent tool**: Spawn parallel sub-agents for simultaneous Gmail + WhatsApp scanning
- **Bash tool**: For file operations (rename, move, copy)

## Important Notes

- Run this skill at least once daily (ideally morning) to keep documents organized
- The user can also trigger it on-demand for specific emails or documents
- Always maintain the exact folder hierarchy — never create shortcuts or alternative structures
- When in doubt about anything, ASK. It's better to ask than to misfile a document.
