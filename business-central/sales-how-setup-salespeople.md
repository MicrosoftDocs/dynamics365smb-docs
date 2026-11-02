---
title: Set up salespeople and purchasers
description: Set up salesperson and purchaser codes in Business Central to assign contacts and campaigns, track performance, and record commission information.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: sales rep
ms.date: 10/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# Set up and assign salespeople

Set up a code for each salesperson to track sales activity, assign responsibility for customers and contacts, and analyze commissions. Use the code on sales documents and in relationship management tasks, such as managing opportunities.

The **Salespeople/Purchasers** page stores both salespeople and purchasers. Assign a salesperson to a customer or contact by using the **Salesperson Code** field. For vendors, use **Purchaser Code** instead.

The following video introduces salesperson setup.

When you set up a salesperson on the **Salespeople/Purchasers** page, you can assign the salesperson to contacts, campaigns, and opportunities in the **Salesperson Code** field. From the salesperson card, you can also view related contacts, campaigns, segments, tasks, and opportunities.

You can also assign a salesperson to a sales invoice or credit memo in the **Salesperson Code** field. When you post the document, [!INCLUDE [prod_short](includes/prod_short.md)] copies the code to the resulting customer ledger entries.
<br><br>  
> [!Video https://learn-video.azurefd.net/vod/player?id=a6cbce42-6a16-4e85-83bc-ee4519ad4afc]

## Set up a salesperson code

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Salespeople/Purchasers**, and select the related link.
2. Select **New** to open the **Salesperson/Purchaser Card**.
3. Enter a unique **Code** and the salesperson's **Name**.
4. Fill in contact details, such as **Phone No.** and **Email**, as needed.
5. In **Commission %**, enter the percentage to use for commission calculations, if applicable.
6. Close the card.

## Assign a salesperson to a customer or contact

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and select the related link.
2. Open the customer card.
3. In **Salesperson Code**, select the salesperson. If the field isn't visible, select **Show more** on the FastTab.

To assign a salesperson to a contact, open the contact card. In **Salesperson Code**, select the salesperson.

Sales documents can use the salesperson assigned to the customer as a default. Other settings, such as the bill-to customer, ship-to address, and user setup, can affect the default. Check **Salesperson Code** on the sales document before posting.

The salesperson code on the sales document is carried to the resulting customer ledger entries when you post. You can use these entries to analyze sales by salesperson.

## Review salesperson commissions

Use the **Salesperson - Commission** report to review posted invoices and credit memos for a salesperson and posting period. The report applies **Commission %** from the salesperson's card to sales, profit, and adjusted profit amounts.

The report uses the salesperson's current commission percentage when you run it. Changing **Commission %** can therefore change the calculated commissions for previously posted transactions.

Learn more about commission calculations in [Salesperson - Commission report](reports/report-115.md).

## Use salespeople in relationship management

You can assign salespeople to contacts, campaigns, opportunities, and tasks. On the **Salesperson/Purchaser Card**, use **Contacts**, **Opportunities**, or **Tasks** to view the related records.

Learn more about assigning activities and tasks in [Set up opportunity sales cycles and cycle stages](marketing-how-setup-opportunity-sales-cycles-stages.md).

## Related information

[Set up sales](sales-setup-sales.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
