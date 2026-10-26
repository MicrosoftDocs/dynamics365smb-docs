---
title: TDS Certificate Tracking
description: Track and update TDS certificates for customer transactions, including certificate details and related actions in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS certificate, certificate tracking
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# TDS certificate tracking

This article explains how to track and update the TDS certificate receivable or received from a customer.

## TDS certificate details assign, update, and rectification process

- Assign TDS certificate details

  Customer Ledger entries, which aren't marked, against which TDS certificate is receivable can be assigned separately. Provision is available to mark the posted customer transactions (invoices or payments) for which TDS certificate is receivable.

  1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Update TDS Certificate Details**, and then choose the related link.
  1. Select **Customer No.**, then choose **Assign TDS Cert. Details**. Select **TDS Certificate Receivable** for the relevant customer ledger entries. These entries become available on **Update TDS Cert. Details**.
  1. System updates the 'TDS Certificate Receivable' field as true in Customer Ledger Entry.

- Update TDS certificate details

  After receiving the TDS Certificate, it's required to update the TDS certificate details.

  1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Update TDS Certificate Details**, and then choose the related link.
  1. Fill in **Customer No.**, **Certificate No.**, **Date of Receipt**, **Certificate TDS Amount**, **Financial Year**, and **TDS Section Code**, then choose **Update TDS Cert. Details**. The certificate amount and financial year must be greater than zero. The page shows entries marked **TDS Certificate Receivable** that don't yet have a received certificate.
  1. Select **TDS Certificate Received** for the relevant documents, then choose **Update TDS Cert. Details** to save the certificate information. These entries become available on **Rectify TDS Cert. Details**.
  1. System updates the customer ledger entry of the selected document with the input data.

- Rectify TDS certificate details

  Rectification of updated details may also be required just in case some wrong information is provided earlier.

  1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Update TDS Certificate Details**, and then choose the related link.
  1. Select **Customer No.**, then choose **Rectify TDS Cert. Details**. The page shows entries with a received TDS certificate.
  1. Clear **TDS Certificate Received** for the relevant documents. This action clears their certificate details while retaining **TDS Certificate Receivable**, so the entries are available again on **Update TDS Cert. Details**.
  1. Return to **Update TDS Certificate Details** and enter the corrected information using the update procedure.

> [!NOTE]
> If you reuse a certificate number for the same customer, its receipt date, amount, financial year, and TDS section must match the details already recorded.

## Related information

[TDS for Customer Overview](TDS-for-Customer-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
