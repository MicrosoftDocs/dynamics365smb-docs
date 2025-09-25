---
title: Connect e-documents to Microsoft 365 applications
description: Learn how to integrate e-documents with Microsoft 365 applications.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: e-documents, Microsoft 365
ms.search.form: 
ms.date: 09/04/2025
ms.custom: bap-template
ROBOTS: NOINDEX
---

# Connect e-documents to Microsoft 365 applications

Streamline accounts payable processes by enabling purchasers to add multiple invoice and receipt documents to e-documents in a single action. That makes it easier for them to process vendor invoices and receipts because it's faster to import the documents from a single point of entry.

This article describes how to set up connections to Microsoft 365 applications.

## Set up connections to Microsoft 365 applications

Connecting e-documents with Microsoft 365 applications requires that you set up e-documents in [!INCLUDE [prod_short](includes/prod_short.md)]. If you haven't done that already, follow the steps in [Set up e-documents](finance-how-setup-edocuments.md) to get started.

> [!NOTE]
>
> * The connections only work for the online version of [!INCLUDE [prod_short](includes/prod_short.md)].
> * The Microsoft 365 access point that you connect with must be in the same Microsoft Entra tenant as your [!INCLUDE [prod_short](includes/prod_short.md)] environment.

### Configure an access point

When your e-document setup is complete and you're ready to connect to a Microsoft 365 application, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then choose the related link.
1. In the **Service Integration V2** field, choose **Outlook**.
1. Choose the **Setup Service Integration** action.

The steps to connect e-documents to a Microsoft 365 access point depend on the type of connector you choose.

### Set up the connector for Outlook

> [!NOTE]
> Currently, the connector for Outlook only lets you download PDF file attachments.

1. On the **Outlook Document Import Setup** page, choose the assist edit button :::image type="content" source="media/assist-edit-icon.png" alt-text="The AssistEdit icon."::: in the **Account** field, and then choose the Microsoft 365 mailbox that you want to download documents from.

   > [!NOTE]
   > The account you're signed in with must have Read/Write access to the Microsoft 365 e-mail account.

1. Turn on the **Enabled** toggle, and then close the page.
1. On the **E-Document Service** page, choose the **Receive** action. This action reads the unread emails from the specified mailbox that were received after the last time you downloaded them. It creates one e-document for each PDF attachment, and marks the emails as read.

## Related information

[E-documents overview](finance-edocuments-overview.md)  
[Set up e-documents](finance-how-setup-edocuments.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]