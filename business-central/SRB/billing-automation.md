---
title: Billing automation
description: Automate recurring billing up to a configured degree.
author: bholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: 
ms.search.form: 8067_Primary, 
ms.date: 12/04/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Billing automation overview

Automated invoicing streamlines the billing process by enabling the automatic creation, posting, and management of invoices and credit memos for customer contracts. The degree of automation is configurable, allowing organizations to tailor the process to their operational needs and compliance requirements.

Automated invoicing helps internal sales management and finance teams increase efficiency by reducing manual effort in contract billing. Depending on contract complexity, the process can be fully automated, partially automated, or manual, with clear controls and error handling to ensure accuracy and compliance.

## Automation scenarios

You can categorize contracts as follows:

- **Fully Automated:** The same invoice is posted every month; the process can be entirely automated.
- **Partially Automated:** Invoices may change; automation is used to create invoices, but manual review is required before posting.
- **Manual:** Contracts require adjustments each period; automation is limited to creating billing proposals.

> [!NOTE]
> Vendor contract invoicing isn't automated.

## How automated invoicing works

### Billing templates

Billing templates define how and when to generate invoices. Key fields include:

- **Posting Date Formula:** Determines the posting date for invoices (e.g., first of next month).
- **Document Date Formula:** Sets the document date for invoices and credit memos.
- **Document per:** Specifies how billing lines are grouped (by contract, contract partner, or invoice recipient).
- **Automation:** Controls the automation level (e.g., create proposal and documents, post documents).

> [!NOTE]
> You can set up automation for posting documents entirely in the job queue.

Templates can filter contracts by contract type and can be scheduled for automation via job queue entries.

### Job queue automation

Automated templates are processed by a dedicated job queue entry (Codeunit 8014, "Auto Contract Billing"). The job queue creates billing proposals and documents based on template settings. Invoices can be posted separately with a second job queue entry (Report 297, "Batch Post Sales Invoices").

### User permissions

To set up billing automation, first make sure users can edit billing templates and then additionally activate the **Auto Contract Billing** option on the **User Setup** page.

### Error logging and handling

All errors during automation are logged for user review. If a document line causes an error, the entire document is discarded to prevent incorrect postings. The process is designed to continue to run efficiently, skipping only problematic lines or documents.

#### Error Log fields

- **Billing Template:** Template code processed.
- **Error Text:** Detailed error message.
- **Subscription/Line, Contract No./Line, Contract Type, Assigned User, Salesperson, Timestamp:** Contextual details for troubleshooting.

A dedicated error log page ("Contract Billing Error Log") is available via the **Tell Me** search (Alt+Q).

### Technical details

#### Relevant fields

- **Billing Templates:** Posting Date Formula, Document Date Formula, Customer Document per, Automation.
- **User Setup:** Auto Contract Billing (Boolean).
- **Sales Header (Invoices/Credit Memos):** Auto Contract Billing (Boolean, system-controlled).

#### Date formula logic

- If date fields are empty, “today” (work date) is used by default.
- Date formulas like “+0D” can be used for dynamic scheduling.

#### Job queue setup, create documents

A job queue entry is created for automated contract invoicing, with retry and delay settings for reliability (Codeunit 8014, "Auto Contract Billing"). The billing template's description is taken over for the job queue entry. The automation object processes the corresponding billing template (determined by job id).

#### Job queue setup, batch posting

Create a separate job queue entry for posting sales invoices using Report 297 ("Batch Post Sales Invoices"). To avoid posting all invoices, apply filters on the report request page before running the batch. Use the **Recurring Billing** and **Auto Contract Billing** fields as filters when you post batches.

### Error handling in automation steps

If a billing line can't be created, the related document is not generated, and all affected lines are logged. If a document can't be created, it's skipped and the error is logged. The automation excludes any subscriptions or documents with errors from further processing.

> [!NOTE]
> The job queue entry determines the order of processing to ensure consistent results, even with overlapping templates.

## Best practices

- Use automation for contracts with predictable, recurring billing.
- Regularly review error logs to address setup or data issues.
- Limit permissions for automated template management to prevent accidental changes.
- Test automation with a subset of contracts before full deployment.

## Related information

[Recurring Billing](#)
[Job Queue Management](#)
[Error Log Review](#)
[User Permissions and Security](#)
