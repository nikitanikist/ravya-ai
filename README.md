# Ravya AI

AI automation system for CA (Chartered Accountant) firms. Automates document organization, compliance tracking, and workflow management.

## Overview

Ravya AI is designed to automate 70%+ of a CA firm's daily operations — starting with document collection and organization, and expanding to cover GST, TDS, ITR preparation, deadline tracking, and client communication management.

## Skills

### Document Organization (DocFlow)
**Trigger phrases:** "organize documents", "scan for new documents", "check Gmail", "file client documents", "run DocFlow"

Scans Gmail and WhatsApp for incoming client documents, downloads attachments, classifies document type (bank statement, invoice, TDS, GST, etc.), renames with standard convention (`Client Name - Doc Type - Period`), and files into the correct folder hierarchy (Client → Financial Year → Work Type).

**Tools required:**
- Claude in Chrome (for Gmail and WhatsApp scanning)
- Google Drive MCP (for file organization) — or local filesystem
- Read/Write tools (for file operations)

## Setup

1. Install the plugin in Claude Cowork
2. Connect Google Drive (if using Drive for file storage)
3. Ensure Claude in Chrome extension is installed for Gmail/WhatsApp access
4. Open Gmail and WhatsApp Web in Chrome tabs

## Client Guardrails

- No government portal access (GST, IT, MCA portals are off-limits)
- No direct client communication
- Human approval required before filing any document
- Modular tool integration (not hardcoded to specific software)

## Roadmap

Future skills to be added:
- **Deadline Tracker** — Monitor compliance deadlines across GST, TDS, ITR, ROC
- **Chase Bot** — Track pending documents from clients
- **Bookkeeping Prep** — Prepare Tally-ready data from bank statements and invoices
- **GST Draft** — Prepare GST return drafts
- **TDS Draft** — Prepare TDS return drafts
- **ITR Draft** — Prepare income tax return drafts
- **Notice Guard** — Monitor and respond to government notices
- **Client Onboarding** — Automate new client setup
