---
    title: Design Details - Non-deductible VAT
    description: Non-deductible value-added tax (VAT) is the VAT that's payable by a purchaser but that isn't deductible from the purchaser's own VAT liability and it can occure in the purcahse process.
    author: altotovi
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/04/2023
    ms.author: altotovi

---


# Design Details: Non-deductible VAT

Non-deductible value-added tax (VAT) is the VAT that's payable by a purchaser but that isn't deductible from the purchaser's own VAT liability. Because it can be difficult to know where and how an item is used, you must contact the local tax authorities in your country to determine whether a specified percentage of the VAT is deductible or not. Even when we know the specific percentage of the VAT is not deductible, there are various models how this non-deductible amounts can be treated related with **Items** and **Fixed Assets**.   

## Prerequisites for using non-deductible VAT 

To make it possible to use and post non-deductible VAT you need to do the following: 

1.	On the **VAT Setup** page, select the **Enable Non-Deductible VAT** field to enable this feature.
2.	Set up which **VAT Posting Groups** can use non-deductible VAT in the **VAT Posting Setup** page.

## Examples  

For all those examples we have enabled non-deductible VAT and configured the following setup: 

- **VAT Product Posting Group**: NDVAT  
- In the **VAT Posting Setup** page:   
    - Set NDVAT as the **VAT Product Posting Group** in combination with DOMESTIC as the **VAT Business Posting Group** 
    - **VAT Identifier** must be unique 
    - **VAT %**: 25   
    - **Allow Non-deductible VAT**: Allow 
    - **Non-deductible VAT %**: 100  
    - **VAT Calculation Type**: Normal VAT 
    - Configured only **Sales** and **Purchase VAT Account** 

In all examples we will use the item and fixed assets with configured **VAT Product Posting Group**: NDVAT.

### Items 

We created new item where the **VAT Prod. Posting Group** is set as NDVAT. In the purchase document we used **Quantity**=1 and **Direct Unit Cost Excl. VAT**=1,000.00. 

Regardless option we used, the results in the **VAT Entry** are the same: 

|Document Type|Type|Base|Amount|Non-Deductible VAT Base|Non-deductible VAT Amount| 
|------------|--------------------|----------|---------|----------|---------| 
|Invoice |Purchase |0.00 |0.00 |1,000.00 |250.00 |  

Details we will show are in the **Value Entries**. 

> [!NOTE] 
> You can enable or disable the **Use for Item Cost** field on the **VAT Setup** page.  

#### Use for Item Cost disabled  

|Item Ledger Entry Type|Entry Type|Cost Amount (Actual)|Item Ledger Entry Quantity| 
|------------|--------------------|------------------------|---------|  
|Purchase |Direct Cost |1,000.00 |1 |   

#### Use for Item Cost enabled  

|Item Ledger Entry Type|Entry Type|Cost Amount (Actual)|Item Ledger Entry Quantity|
|------------|--------------------|------------------------|---------| 
|Purchase |Direct Cost |1,250.00 |1 |  

### Fixed Assets 

We created new fixed asset where the **Acquisition Cost Account** is set to use NDVAT as the **VAT Prod. Posting Group**. In the purchase document we used **Quantity**=1 and **Direct Unit Cost Excl. VAT**=1,000.00.  

Regardless option we used, the results in the **VAT Entry** are the same: 

|Document Type|Type|Base|Amount|Non-Deductible VAT Base|Non-deductible VAT Amount| 
|------------|--------------------|----------|---------|----------|---------|  
|Invoice |Purchase |0.00 |0.00 |1,000.00 |250.00 | 

Details we will show are in the **FA Ledger Entries**.

> [!NOTE] 
> You can enable or disable the **Use for Fixed Asset Cost** field on the **VAT Setup** page.  

#### Use for Fixed Asset Cost disabled 

|Document Type|FA Posting Type| Amount|VAT Amount|
|------------|--------------------|------------------------|---------| 
|Invoice |Acquisition Cost |1,000.00 |250.00 |  

#### Use for Fixed Asset Cost enabled  

|Document Type|FA Posting Type|Amount|VAT Amount| 
|------------|--------------------|------------------------|---------| 
|Invoice |Acquisition Cost |1,000.00 |250.00 |  
|Invoice |Acquisition Cost |250.00 |0.00 |  


## See Also  
 [Set up non-deductible VAT](finance-setup-nondeductible-vat.md)  
 [Finance](finance.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
