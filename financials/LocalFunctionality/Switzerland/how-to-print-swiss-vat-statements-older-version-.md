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
# How to: Print Swiss VAT Statements (older version)
> [!NOTE]  
>  This topic is retained for backward compatibility with the **Swiss VAT Statement** report. For information about using the newer Swiss VAT Statement, see Swiss VAT Statement.  
  
 The **Swiss VAT Statement** is the standard calculation report for realizing VAT. You can print this report, and use it for quarterly tax reporting. The **Swiss VAT Statement** ../../includes:  
  
-   A VAT entry.  
  
-   VAT adjusting entries.  
  
-   An accounting sheet.  
  
### To print the Swiss VAT statement  
  
1.  In the **Search** box, enter **Swiss VAT Statement**, and then choose the related link.  
  
    > [!NOTE]  
    >  You will receive a message stating that the **Swiss VAT Statement** will open in the local language.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_11518\_F\_1\_6 Closed with Journal no. $\)**|Select the general ledger journals that contain the posting source of the VAT adjusting entries. This field evaluates accounting periods that have already been settled.|  
    |**\($ R\_11518\_F\_1\_8 Open until date $\)**|Select the last date for settling open or unsettled VAT entries.|  
    |**\($ R\_11518\_F\_1\_1 Show Postings $\)**|Specifies if all of the VAT entries for each group will be printed.|  
    |**\($ R\_11518\_F\_1\_5 Show Chargeback $\)**|Specifies if VAT entries and general ledger entries with closed summaries or reposted tax will be printed.|  
    |**\($ R\_11518\_F\_1\_11 Normal rate VAT % $\)**|Select the current typical VAT rates used to assign the correct rates to the business and product groups defined in the VAT settings.|  
    |**\($ R\_11518\_F\_1\_13 Reduced rate VAT % $\)**|Select the current reduced tax rates used to assign the correct rates to the business and product groups defined in the VAT settings.|  
    |**\($ R\_11518\_F\_1\_15 Special rate VAT % $\)**|Select the current special tax rates used to assign the correct rates to the business and product groups defined in the VAT settings.|  
    |**\($ R\_11518\_F\_1\_17 Investment\/Operating Purchase VAT G\/L Account $\)**|Select the VAT general ledger account.|  
    |**\($ R\_11518\_F\_1\_19 Own Consumption Bus. Group $\)**|Select the business and product group for own consumptions.|  
    |**\($ R\_11518\_F\_1\_4 Service Foreign Bus. Group $\)**|Select the foreign service business and product group.|  
    |**\($ R\_11518\_F\_1\_1150001 Export Bus. Group $\)**|Select the business and product group for exports.|  
  
3.  Choose the **Print** button to print the VAT statement or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [Swiss Value Added Tax](swiss-value-added-tax.md)   
 [VAT Rates for Switzerland](vat-rates-for-switzerland.md)   
 VAT Posting Setup   
 General Ledger Setup   
 VAT Entry