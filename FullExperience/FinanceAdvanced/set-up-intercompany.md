---
title: "Set Up Intercompany"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "intercompany (posting), setting up"
ms.assetid: 4b8a3fca-2087-4631-b0f6-5383f9cae8d8
caps.latest.revision: 3
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Set Up Intercompany
You can use intercompany postings to transfer transactions electronically from one partner company to another. This allows you to save time on data entry and reduce the number of errors.  
  
## Intercompany Chart of Accounts and Intercompany Dimensions  
 To send a transaction \(such as a sales journal line\) from one company and have the corresponding transaction \(such as a purchase journal line\) automatically created in the partner company, the companies involved need to agree on a common chart of accounts and set of dimensions for use on intercompany transactions. The intercompany chart of accounts can be, for example, a simplified version of the parent company's chart of accounts. Each company maps their full chart of accounts to the shared intercompany chart of accounts, and each company maps their dimensions to the intercompany dimensions.  
  
## IC Partner Codes  
 You also need to set up an IC partner code for each partner company. The partner codes must also be agreed upon by all of the companies.  
  
 If you have set up your intercompany partners as customers or vendors, fill in the **IC Partner Code** field on the relevant customer and vendor cards.  
  
## Items and Resources  
 If you will create or receive intercompany lines with items, you can either use your own item numbers, or you can set up your partner's item numbers for each relevant item, either in the **Vendor Item No.** field or the **Common Item No.** field on the item card, or by using the **Item Cross Reference Entries** window linked to the item card.  
  
 If you will make intercompany sales transactions that include resources, you must fill in the **IC Partner Purch. G\/L Acc. No.** field on the resource card for each relevant resource. This is the number of the intercompany general ledger account that the amount for this resource will be posted to in your partner's company.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Fill in intercompany related fields in the Company Information window.|See step 1 in: [Setting Up Intercompany Postings](../Finance/how-to-set-up-intercompany-postings.md)|  
|Create intercompany partner cards.|See step 2 in: [Setting Up Intercompany Postings](../Finance/how-to-set-up-intercompany-postings.md)|  
|Link intercompany partners to customer or vendor cards.|See step 3 in: [Setting Up Intercompany Postings](../Finance/how-to-set-up-intercompany-postings.md)|  
|Learn about setting up the intercompany chart of accounts.|[Setup of the Intercompany Chart of Accounts](../Finance/setup-of-the-intercompany-chart-of-accounts.md)|  
|Define the intercompany chart of accounts that your partner companies will use to make intercompany transactions.|[How to: Define the Intercompany Chart of Accounts](../Finance/how-to-define-the-intercompany-chart-of-accounts.md)|  
|Import an XML file containing the intercompany chart of accounts that you and your partner companies have agreed to use.|[How to: Import the Intercompany Chart of Accounts](../Finance/how-to-import-the-intercompany-chart-of-accounts.md)|  
|Associate each of the intercompany general ledger accounts with one of your company's general ledger accounts.|[How to: Map the Intercompany Chart of Accounts to Your Company’s Chart of Accounts](../Finance/how-to-map-the-intercompany-chart-of-accounts-to-your-company’s-chart-of-accounts.md)|  
|Learn about intercompany dimensions setup so that you can exchange transactions with dimensions linked to them with your intercompany partners.|[Setup of the Intercompany Dimensions](../Finance/setup-of-the-intercompany-dimensions.md)|  
|Define the intercompany dimensions that you and your partner companies will use to make intercompany transactions.|[How to: Define Intercompany Dimensions](../Finance/how-to-define-intercompany-dimensions.md)|  
|Import an XML file containing the intercompany dimensions that you and your partner companies have agreed to use.|[How to: Import Intercompany Dimensions](../Finance/how-to-import-intercompany-dimensions.md)|  
|Associate each of the intercompany dimensions with one of your company's dimensions, and vice versa.|[How to: Map Intercompany Dimensions to Your Company’s Dimensions](../Finance/how-to-map-intercompany-dimensions-to-your-company’s-dimensions.md)|  
|Assign the default intercompany payables and receivables accounts that will be entered on intercompany transactions. This is the account in your partner's company that the amount will be posted to.|[How to: Set Up Default Intercompany Partner General Ledger Accounts](../Finance/how-to-set-up-default-intercompany-partner-general-ledger-accounts.md)|  
  
## See Also  
 [Manage Intercompany Transactions](../Finance/manage-intercompany-transactions.md)   
 [Manage Intercompany Inbox](../Finance/manage-intercompany-inbox.md)