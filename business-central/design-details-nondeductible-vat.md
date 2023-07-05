---
    title: Design Details - Non-deductible VAT
    description: This article provides information about non-deductible value-added tax (VAT) that's payable by a purchaser but that isn't deductible from the purchaser's own VAT liability.
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

Non-deductible value-added tax (VAT) is the VAT that's payable by a purchaser, but isn't deductible from the purchaser's own VAT liability. Because it can be difficult to know where and how an item is used, you must contact the local tax authorities in your country to determine whether a specified percentage of the VAT is deductible. Even when we know the specific percentage of the VAT isn't deductible, there are various models for how these non-deductible amounts can be treated as they relate to **Items** and **Fixed Assets**.   

## Prerequisites to use non-deductible VAT 

To use and post non-deductible VAT, do the following: 

1.	On the **VAT Setup** page, select **Enable Non-Deductible VAT** to enable the feature.
2.	Pn the **VAT Posting Setup** page, select which **VAT Posting Groups** can use non-deductible VAT.

## Examples  

For the following examples, non-deductible VAT is enabled and the following setup is configured: 

- **VAT Product Posting Group**: NDVAT  
- On the **VAT Posting Setup** page:   
    - Set NDVAT as the **VAT Product Posting Group** in combination with DOMESTIC as the **VAT Business Posting Group** 
    - **VAT Identifier** must be unique 
    - **VAT %**: 25   
    - **Allow Non-deductible VAT**: Allow 
    - **Non-deductible VAT %**: 100  
    - **VAT Calculation Type**: Normal VAT 
    - Configured only **Sales** and **Purchase VAT Account** 

In all examples, the items and fixed assets that are configured with **VAT Product Posting Group**: NDVAT are used.

### Items 

A new item has **VAT Prod. Posting Group** set as NDVAT. In the purchase document, **Quantity**=1 and **Direct Unit Cost Excl. VAT**=1,000.00 are used. 

Regardless of the option used, the results in the **VAT Entry** are the same: 

|Document Type|Type|Base|Amount|Non-Deductible VAT Base|Non-deductible VAT Amount| 
|------------|--------------------|----------|---------|----------|---------| 
|Invoice |Purchase |0.00 |0.00 |1,000.00 |250.00 |  

The details are shown in the **Value Entries**. 

> [!NOTE] 
> You can enable the **Use for Item Cost** field on the **VAT Setup** page.  

#### Use for Item Cost isn't enabled  

|Item Ledger Entry Type|Entry Type|Cost Amount (Actual)|Item Ledger Entry Quantity| 
|------------|--------------------|------------------------|---------|  
|Purchase |Direct Cost |1,000.00 |1 |   

#### Use for Item Cost is enabled  

|Item Ledger Entry Type|Entry Type|Cost Amount (Actual)|Item Ledger Entry Quantity|
|------------|--------------------|------------------------|---------| 
|Purchase |Direct Cost |1,250.00 |1 |  

### Fixed Assets 

The new fixed asset has **Acquisition Cost Account** set to use NDVAT as the **VAT Prod. Posting Group**. In the purchase document, **Quantity**=1 and **Direct Unit Cost Excl. VAT**=1,000.00 are used.  

Regardless of the option used, the results in the **VAT Entry** are the same: 

|Document Type|Type|Base|Amount|Non-Deductible VAT Base|Non-deductible VAT Amount| 
|------------|--------------------|----------|---------|----------|---------|  
|Invoice |Purchase |0.00 |0.00 |1,000.00 |250.00 | 

The details are shown in the **FA Ledger Entries**.

> [!NOTE] 
> You can enable the **Use for Fixed Asset Cost** field on the **VAT Setup** page.  

#### Use for Fixed Asset Cost isn't enabled 

|Document Type|FA Posting Type| Amount|VAT Amount|
|------------|--------------------|------------------------|---------| 
|Invoice |Acquisition Cost |1,000.00 |250.00 |  

#### Use for Fixed Asset Cost is enabled  

|Document Type|FA Posting Type|Amount|VAT Amount| 
|------------|--------------------|------------------------|---------| 
|Invoice |Acquisition Cost |1,000.00 |250.00 |  
|Invoice |Acquisition Cost |250.00 |0.00 |  


## See Also  
 [Set up non-deductible VAT](finance-setup-nondeductible-vat.md)  
 [Finance](finance.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
