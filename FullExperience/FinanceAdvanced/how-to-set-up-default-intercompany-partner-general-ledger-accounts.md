---
title: "How to: Set Up Default Intercompany Partner General Ledger Accounts"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "intercompany (posting), partner accounts"
ms.assetid: dff2c092-2f71-4f40-aff0-b7b266133037
caps.latest.revision: 7
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
# How to: Set Up Default Intercompany Partner General Ledger Accounts
When you create an intercompany sales or purchase line to send as an outgoing transaction, you will enter an account from the IC chart of accounts as a default for which account in your partner's company the amount should be posted to. In the **Chart of Accounts** window, for accounts that you often use on outgoing IC sales or purchase lines, you can specify a default IC partner general ledger account. For example, for your receivables accounts, you can enter the corresponding payables accounts from the IC chart of accounts.  
  
> [!NOTE]  
>  Repeat the following procedure for each account that you often enter in the **Bal. Account No.** field on a line in an intercompany journal or document.  
  
### To set up default intercompany partner general ledger accounts  
  
1.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
2.  In the **Default IC Partner G\/L Account** field, enter the IC general ledger account that your partner will post to when you post to the general ledger account on the line.  
  
    > [!IMPORTANT]  
    >  This field is available in the **Chart of Accounts** window, but it is not shown by default. [!INCLUDE[bp_customize](../Finance/includes/bp_customize_md.md)]  
  
> [!NOTE]  
>  When you enter a general ledger account in the **Bal. Account No.** field on an intercompany line with **IC Partner** in the **Account Type** field, the **IC Partner G\/L Account** field will be automatically filled in.  
  
## See Also  
 [Chart of Accounts](assetId:///fa407624-b670-44b6-8397-91aa606e4c39)   
 [IC Partner G\/L Acc. No.](assetId:///588f5f9b-6315-4e9f-b19b-f8801ff8381a)