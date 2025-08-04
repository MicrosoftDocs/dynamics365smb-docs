---
title: Setting Up Tax Deducted at Source (TDS) on purchase of goods under Section 194Q
description: Specifies the setups required, as per the provisions of the Income Tax Act, 1961.

author: v-debapd

    
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 06/25/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Setting Up Tax Deducted at Source (TDS) on purchase of goods under Section 194Q


[!INCLUDE[vnext_preview](../../includes/vnext_preview.md)]

Business Central has included Tax Collected at Source (TCS) Feature in Indian Localization.

A new TDS section 194Q, on purchase of goods is recently introduced vide the Finance Act, 2021. 

This is going to apply to any person, being a buyer responsible for making a payment to a resident for purchase of goods when value or aggregate of purchase from a supplier or payment whichever is earlier, Rs.50 lacs during the previous year. The transaction with any supplier with the addition of which your aggregate purchase/payment for a purchase from that supplier exceeds Rs.50 lacs, will be the transaction effective which TDS must be deducted @0.10% of the Purchase transaction or payment thereof whichever is earlier. 
This new Section 194Q is applicable from 1st July 2021.


## Setting Up TDS section 194Q

### Following is the list of setups that will be required

- [TDS Rates](TDS-194Q-section-overview.md#to-set-up-tds-rates)
- [TDS 194Q Opening](TDS-194Q-section-overview.md#tds-194q-opening)


## To set up TDS rates

The rate of TDS is defined by the combination of the TDS section and assessee code. The rates of tax deduction may vary for a given period. A new field 'Calc. Over & Above Threshold' has been added on the setup. 


1. Choose the ![Search for Page or Report](image/search_small.png "Search for Page or Report icon") icon, enter **TDS Section**, and then choose the related link.
2. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Calc. Over & Above Threshold**|This field is created in TDS Setup table, by selecting this field, system will calculate TDS on amount that is over & above threshold. If this field is not selected in TDS Setup, system will calculate TDS normally, i.e., system will calculate TDS on amount exceeding the specified threshold amount. If user selects Threshold Overlook field on NOD/NOC Lines, then, system calculates TDS normally, i.e., calculate TDS from INR 1 onwards without considering threshold amount. This field can be selected for any TDS group, as its application is not limited to TDS, under Section 194Q.|


## TDS 194Q Opening

A provision has been made to upload the opening amount, if any, under TDS section 194Q. System only updates the amount in TDS Entries table for threshold calculation purposes. This amount is not posted into G/L.

1. Choose the ![Search for Page or Report](image/search_small.png "Search for Page or Report icon") icon, enter **TDS 194Q Opening**, and then choose the related link.
2. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Vendor No.**|Specifies the vendor number for which 194Q opening is to be posted.|
    |**Assessee Code**|Specifies the assessee code.|
    |**TDS Section**|Specify the TDS Section, for which opening entry is to be posted.|
    |**Document No.**|Specifies the document number, that will appear on the TDS ledger entries.|
    |**Posting Date**|Specify the date, on which the TDS ledger entries are to be posted.|
    |**Purchase Amount**|Specify the purchase amount, that must be posted into TDS Entry table as vendor’s opening entry for Section 194Q.|
    |**TDS Threshold Amount**|Specifies the TDS threshold amount, that is defined on the TDS setup for TDS Nature of Deduction.|
    |**Description**|Specifies the description of the transaction, to be posted.|
    

## To setup Customer

Provision is made available on customer master to capture whether aggregate turnover of customer in the immediate previous year was below 10 crores or above 10 crores.

1. Choose the ![Search for Page or Report](image/search_small.png "Search for Page or Report icon") icon, enter **Customer**, and then choose the related link. 
2. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|   
    |**Aggregate Turnover**|This field can be used to define aggregate Turnover in the immediate previous year exceeds Rs.10 crore to an assessee. The available options are: Less than 10 Crore, More than 10 Crore.|  


## Related information 
[TDS 194Q Transactions](TDS-194Q-Transactions.md)




