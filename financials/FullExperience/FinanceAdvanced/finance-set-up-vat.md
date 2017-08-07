---
    title: Set Up VAT | Microsoft Docs
    description: Similar to the general posting setup described in **Set Up Posting Groups**, you must define one or more VAT business posting groups and assign one of them to each general ledger, customer, and vendor account. You must also set up one or more VAT product posting groups and assign one of them to each item and resource account. After you have set up the groups, you must set up the necessary combinations of the groups in the VAT posting setup. For each combination, specify the VAT percentage, and general ledger accounts for sales VAT, purchase VAT, and, if needed, reverse charge VAT.
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
# Set Up VAT
Similar to the general posting setup described in **Set Up Posting Groups**, you must define one or more VAT business posting groups and assign one of them to each general ledger, customer, and vendor account. You must also set up one or more VAT product posting groups and assign one of them to each item and resource account. After you have set up the groups, you must set up the necessary combinations of the groups in the VAT posting setup. For each combination, specify the VAT percentage, and general ledger accounts for sales VAT, purchase VAT, and, if needed, reverse charge VAT.  
  
 If you assign default VAT posting groups to the general posting groups, the VAT posting groups will automatically be assigned to general ledger, customer, vendor, item and resource accounts when you assign the general posting groups.  
  
## Import VAT  
 The import VAT feature is used when you need to post a document where the entire amount must be treated as VAT. This is necessary if you receive a VAT invoice from the tax authorities for imported goods. To handle import VAT, you must set up at least one VAT product posting group for import VAT, and include it in at least one combination in the VAT posting setup.  
  
## Reverse Charge VAT  
 Usually, the seller of an item calculates and withholds VAT. Companies in the EU, however, must use reversed VAT calculation when trading with other companies that are registered as VAT-liable in another EU country/region. This means that instead of VAT being calculated by the seller, it must be calculated by the purchaser.  
  
 You must set up at least one VAT business posting group for reverse charge VAT, and include it in at least one combination in the VAT posting setup. The reverse charge VAT feature can be used in connection with the standard VAT calculation principle, as well as with the unrealized VAT calculation principle.  
  
## Unrealized VAT  
 By default, VAT is calculated and posted when an invoice is posted. However, you can choose to have VAT amounts first calculated and posted to a temporary general ledger account when the invoice is posted, and then posted to the correct general ledger account and included in VAT statements when the actual payment of the invoice is posted.  
  
## Adjust Payment Discounts for VAT  
 If a payment discount has been calculated on the basis of an invoice amount including VAT, you can have the payment discount part of the VAT amount be debited to the Sales VAT account when the payment discount is granted.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them.   
  
|**To**|**See**|  
|------------|-------------|  
|Learn about setting up VAT, including setting up VAT posting groups and VAT posting setup combinations, and using reverse charge VAT.|[How to: Create a VAT Combination Setup](../how-to-create-a-vat-combination-setup.md)|  
|Set up posting groups that you can use to categorize customers and vendors for VAT posting purposes.|[How to: Set Up VAT Business Posting Groups](../how-to-set-up-vat-business-posting-groups.md)|  
|Set up posting groups that you can use to categorize items and resources for VAT posting purposes.|[How to: Set Up VAT Product Posting Groups](../how-to-set-up-vat-product-posting-groups.md)|  
|Set up the VAT percentage and default posting accounts for each combination of a VAT product group and a VAT business group.|[How to: Set Up Combinations of VAT Business Posting Groups and VAT Product Posting Groups](../how-to-set-up-combinations-of-vat-business-posting-groups-and-vat-product-posting-groups.md)|  
|Link VAT business posting groups to general business posting groups, so they are assigned automatically.|[How to: Set Up Default VAT Business Posting Groups](../how-to-set-up-default-vat-business-posting-groups.md)|  
|Link VAT product posting groups to general product posting groups, so they are assigned automatically.|[How to: Set Up Default VAT Product Posting Groups](../how-to-set-up-default-vat-product-posting-groups.md)|  
|Assign VAT posting groups to general ledger accounts manually.|[How to: Assign VAT Posting Groups to General Ledger Accounts](../how-to-assign-vat-posting-groups-to-general-ledger-accounts.md)|  
|Assign VAT business posting groups to customer and vendor accounts manually.|[How to: Assign VAT Business Posting Groups to Customer Accounts and Vendor Accounts](../how-to-assign-vat-business-posting-groups-to-customer-accounts-and-vendor-accounts.md)|  
|Assign VAT product posting groups to item and resource accounts manually.|[How to: Assign VAT Product Posting Groups to Item Accounts and Resource Accounts](../how-to-assign-vat-product-posting-groups-to-item-accounts-and-resource-accounts.md)|  
|Use the import VAT feature to post a document where the entire amount must be treated as VAT, for example, if you receive a VAT invoice from the tax authorities for imported goods.|[How to: Set Up Codes for Import VAT](../how-to-set-up-codes-for-import-vat.md)|  
|Set up at least one VAT business posting group for reverse charge VAT in order to have VAT on purchases from the EU treated appropriately.|[How to: Enter Basic Information on Reverse Charge VAT for Purchases](../how-to-enter-basic-information-on-reverse-charge-vat-for-purchases.md)|  
|Have VAT amounts calculated and posted to a temporary general ledger account when an invoice is posted, and then posted to the correct general ledger account and included in VAT statements when the actual payment of the invoice is posted.|[How to: Use Accounts for Unrealized VAT](../how-to-use-accounts-for-unrealized-vat.md)|  
|Revert the payment discount part of the VAT amount when the payment discount is granted.|[How to: Revert VAT on Payment Discounts](../how-to-revert-vat-on-payment-discounts.md)|  
|Set up periodic VAT reports that must be submitted to the tax authorities.|[VAT and VIES Report Setup](../vat-and-vies-report-setup.md)|  
  
## See Also  
 [How to: Set Up Default VAT Business Posting Groups](../how-to-set-up-default-vat-business-posting-groups.md)   
 [How to: Set Up Default VAT Product Posting Groups](../how-to-set-up-default-vat-product-posting-groups.md)   
 [How to: Set Up Combinations of VAT Business Posting Groups and VAT Product Posting Groups](../how-to-set-up-combinations-of-vat-business-posting-groups-and-vat-product-posting-groups.md)   
 [Set Up Posting Groups](../set-up-posting-groups.md)