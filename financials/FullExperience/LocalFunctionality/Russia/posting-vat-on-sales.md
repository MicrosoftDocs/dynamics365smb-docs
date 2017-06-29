---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Posting VAT on Sales
The following fields have been added to the VAT Posting Setup form \(ID 472\):  
  
|Field|Description|  
|-----------|-----------------|  
|**Trans. VAT Type**|Used to define the rule for extracting VAT.|  
|**Trans. VAT Account**|Used to specify an account to register the VAT amount from the gain and from the customer's prepayments to be paid to the federal budget.|  
|**Tax Invoice Amount Type**|Used to select the value of VAT. Depending on the value in this field, VAT entry amounts are used in different columns of the VAT purchase or sales ledgers.|  
  
 The above actions are taken for each combination of the Sales VAT Product posting group and Sales VAT posting group.  
  
 In the **Trans. VAT Type** field, the following options are available:  
  
-   **\<Blank\>**  
  
-   **Amount \+ Tax**  
  
-   **Amount & Tax**  
  
 To account for VAT, choose **Amount \+ Tax**.  
  
 The following procedure shows how the accounting entries are created.  
  
1.  Enter Subaccount 90-3, Gain VAT, in the **Trans. VAT Account No.** field.  
  
2.  Enter Subaccount 68, VAT to Federal Budget, in the **Sales VAT Account** field.  
  
 The following accounting entries create the different settings.  
  
|Accounting Entries|Settings|  
|------------------------|--------------|  
|**Amount \+ Tax**|Debit 62 Payables and Receivables - Credit 90-1 Gain and Sales Amount Including VAT<br /><br /> Debit 90-3 Gain VAT<br /><br /> Credit 68 VAT to Federal Budget<br /><br /> Sales VAT Amount|  
|**Amount & Tax**|Debit 62 Payables and Receivables<br /><br /> Credit 90-1 Gain<br /><br /> Amount Excluding VAT<br /><br /> Debit 62 Payables and Receivables<br /><br /> Credit 90-3 Gain VAT<br /><br /> Sales VAT Amount<br /><br /> Debit 90-3 Gain VAT<br /><br /> Credit 68 VAT to Budget<br /><br /> Sales VAT amount|  
|**\<Blank\>**|Debit 62 Payables and Receivables<br /><br /> Credit 90-1 Gain<br /><br /> Amount Excluding VAT<br /><br /> Debit 62 Payables and Receivables<br /><br /> Credit 68 VAT to Budget<br /><br /> Sales VAT Amount|  
  
## Trans. VAT Account Field  
 In the **Trans. VAT Account** field, enter Subaccount 90-3 Gain VAT or Subaccount 62 Prepayment VAT. If this field is blank, the postings use the account from the Customer posting groups from the **Receivables Account** field.  
  
## See Also  
 [VAT Ledgers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/vat-ledgers.md)