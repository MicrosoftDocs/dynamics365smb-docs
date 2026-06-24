---
title: Use the E-Document Format for E-Reporting [FR]
description: Learn how to send French e-reporting transactions by using the E-Reporting FR format and an e-document service.
author: altotovi
ms.author: altotovi
ms.reviewer: v-soumramani
ms.topic: how-to
ms.date: 06/23/2026
ms.service: dynamics-365-business-central
ms.search.keywords: e-document format, e-reporting, e-document service, Pagero, Avalara, French version
ms.country: fr
---

# E-Reporting in France

> [!NOTE]
> This feature applies to Business Central online and Business Central on-premises (France).

In France, businesses must report certain transactions that fall outside the mandatory B2B e-invoicing scope to the tax authority under the e-reporting obligation. Examples include sales to private consumers (B2C), cross-border B2B transactions, exports outside the EU, intra-community deliveries and acquisitions, and transactions involving overseas territories.

Business Central supports this requirement through the **E-Reporting FR e-document format**, which generates the structured XML payload for each transaction. An e-document service then sends the payload to the tax authority through a partner-dissemination platform (PDP), such as Pagero or Avalara, that you configure on the **E-Document Service** page.

> [!NOTE]
> - Pagero and Avalara are examples of PDP connectors. The format also works with any e-document service connector that can transmit data to the French tax authority.
> - Learn more about the complete list of supported service providers in [Set up the E-Documents connector with external endpoints](../../finance-how-setup-edocuments-external.md#available-service-providers). Alternatively, users can install and use connectors from AppSource.

## Prerequisites

To submit e-reporting transactions, complete the following steps.

### Set the e-reporting transaction type for customers and vendors

Assign an **E-Reporting Transaction Type** to each customer or vendor whose transactions you report through e-reporting. This setting determines how Business Central categorizes the transaction in the XML payload that is sent to the tax authority. If you leave the field blank, the transaction is reported without a category and might be rejected by the platform.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers** or **Vendors**, and then choose the related link.
1. Open the relevant **Customer Card** or **Vendor Card**.
1. On the **Invoicing** FastTab, in the **E-Reporting Transaction Type** field, select the value that describes the transactions you exchange with this party.

   | Value | When to use it |
   |-------|----------------|
   | *(blank)* | The party isn't in scope for e-reporting |
   | **Business-to-consumer** | Sales to private individuals (B2C) |
   | **Cross-border business-to-business** | B2B transactions with parties established outside France |
   | **Exports outside of EU** | Goods or services exported outside the European Union |
   | **Intra-community deliveries and acquisitions** | Intra-EU goods and services subject to the intra-community VAT regime |
   | **Transactions involving overseas territories** | Transactions with French overseas territories (DOM/COM) |

> [!NOTE]
> Each posted document inherits the **E-Reporting Transaction Type** from the customer or vendor at the time of posting. Update the master data before you post the documents you want to report.

### Configure the e-document service

E-Reporting FR is a *document format* that runs within an e-document service. The service connects to a PDP such as Pagero or Avalara and forwards the generated XML to the French tax authority.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then choose the related link.
1. Choose **New** to create a service, or open an existing one.
1. In the **Document Format** field, select **E-Reporting FR**.
1. In the **Service Integration** field, select the connector for your PDP, such as **Pagero** or **Avalara**. Enter the required connection details, such as endpoint URLs and authentication credentials.
1. Close the page.

When you set **Document Format** to **E-Reporting FR**, Business Central automatically registers the following supported source document types for the service. You don’t need to maintain them manually on the **E-Document Service Supported Source Document Types** page:

- Sales Invoice
- Sales Credit Memo
- Purchase Invoice
- Purchase Credit Memo
- Service Invoice
- Service Credit Memo

Use the e-document service with a **Workflow** value, which is set on the **E-Document Services** page to control whether documents are sent individually or in batches. The E-Reporting FR format supports both single and batch submissions.

## Submit transactions for e-reporting

After you complete the prerequisites, submit e-reporting transactions by using the standard e-document flow:

1. Post the sales, purchase, or service document as usual. If the document is in scope for the configured e-document service, Business Central automatically creates an **E-Document** record.
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Documents**, and then choose the related link.
1. Select the document, and then choose **Send** to generate the XML payload and pass it to the configured PDP connector. If you use a batch workflow, send multiple documents together.

The connector for Pagero, Avalara, or another PDP submits the XML that the E-Reporting FR format generates to the French tax authority on your behalf.

## Track acceptance and rejection by the tax authority

The submission result is returned through the standard e-document **Service Status** and is shown directly on the **E-Documents** page.

The **E-Reporting FR** app adds the **E-Reporting Acceptance Date** column to the **E-Documents list** and updates it automatically based on the latest service status:

| Service status reported by the PDP | E-reporting acceptance date |
|------------------------------------|-----------------------------|
| **Approved** or **Cleared** | Set to the date and time the status was reported (transaction accepted by the tax authority) |
| **Rejected** or **Not Cleared** | Cleared (empty) — the transaction hasn't been accepted |
| Any other (in-progress) status | Unchanged |

To check status:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Documents**, and then choose the related link.
1. Review the **Status** and **E-Reporting Acceptance Date** columns.
   - If **E-Reporting Acceptance Date** contains a value, the tax authority has accepted the transaction.
   - If the column is blank and **Status** is **Rejected** or **Not Cleared**, open the document to review the error returned by the PDP, fix the underlying issue (for example, a missing **E-Reporting Transaction Type**), and resend it.

## Related information

- [E-Documents overview](../../finance-edocuments-overview.md)  
- [Electronic invoicing in France with UBL 2.1 and Factur-X](enable-electronic-invoicing-france.md)
- [Set up e-documents](../../finance-how-setup-edocuments.md)  
- [Export General Ledger Entries Tax Audits [FR]](how-to-export-general-ledger-entries-for-tax-audits.md)  
- [France local functionality](france-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
