---
    title: Tax Accounting
    description: In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can set up and maintain tax registers to track taxable profits and losses.

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
# Tax Accounting
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can set up and maintain tax registers to track taxable profits and losses. This is based on the following tax accounting principles:  

- The financial database is used for tax accounting.  
- The chart of accounts is used to track taxable profits and losses.  
- Income and expenses are recorded using separate subaccounts and dimensions.  
- Fixed asset transactions and expenses for future periods are tracked using the depreciation book for tax accounting.  
- Tax registers are grouped and totaled monthly. Each register has 12 values for a 12 month tax period.  

Because [!INCLUDE[d365fin](../../includes/d365fin_md.md)] keeps the history of all transactions, detailed information from a transaction that changes taxable profits is automatically tracked. The information collected in tax registers meets the principles of tax reliability and tax validity.  

## Tax Registers  
There are two types of tax registers that are used for tracking taxable profits and losses.  

|Tax Register Type|Description|  
|-----------------------|---------------------------------------|  
|Analytic Tax Register|An analytic register is based on ledger entries for taxable transactions. The information provides a continuous chronological reflection of business operations, which tracks taxable profits and losses based on tax codes.|  
|Synthetic Tax Register|A synthetic register is based on summarized and calculated information from an analytic register or another synthetic register.|  

Transactions are processed using specific tax accounting principles that are applied to the following types of tax registers.  

|Tax Register|Description|  
|------------------|---------------------------------------|  
|General Ledger Entry|An analytic register based on general ledger transaction entries.|  
|CV Entry|A group of analytic registers based on information associated with debtor or creditor liabilities.|  
|Fixed Asset Entry|A group of analytic registers based on tax data for fixed assets. This group is created by using a fixed asset ledger and a tax depreciation book that is not integrated with the financial accounting ledger.|  
|Item Entry|An analytic register based on posted item transactions.|  
|Future Expense Entry|A group of analytic registers based on tax data for future expenses. This group is created by using a fixed asset ledger and a tax depreciation book that is not integrated with the financial accounting ledger.|  
|Accumulation|A synthetic register based on calculated algorithms defined during tax register set up.|  

## See Also  
 [Set Up Tax Accounting](how-to-set-up-tax-accounting.md)   
 [Tax Registers](tax-registers.md)   
 [Create Tax Registers](how-to-create-tax-registers.md)   
 [Set Up Tax Register Sections](how-to-set-up-tax-register-sections.md)   
 [Tax Differences](tax-differences.md)   
 [Tax Reports](assetId:///e42ca8e7-1cee-4fb8-9f71-e596f29cabc3)
