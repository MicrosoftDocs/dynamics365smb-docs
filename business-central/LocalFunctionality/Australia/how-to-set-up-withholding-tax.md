---
    title: How to Set Up Withholding Tax
    description: Withholding tax (WHT) is the tax withheld by a company when it makes a payment to a vendor, in which the full amount owed to the vendor is reduced by the tax withheld. The withheld tax is then remitted to the Australian Taxation Office (ATO) when the next Business Activity Statement (BAS) is submitted.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up Withholding Tax
Withholding tax (WHT) is the tax withheld by a company when it makes a payment to a vendor, in which the full amount owed to the vendor is reduced by the tax withheld. The withheld tax is then remitted to the Australian Taxation Office (ATO) when the next Business Activity Statement (BAS) is submitted.  

If a supplier without an Australian Business Number (ABN) provides an invoice, a withholding tax amount must be withheld if the total amount of the invoice is more than the threshold amount.  

To use withholding tax, you must set up the business posting groups and product posting groups for withholding tax so that the correct WHT calculations are made for each vendor.  

> [!NOTE]  
>  As a prerequisite, you need to set up source codes for WHT settlement on the **Source Code Setup** page.  

The following procedure describes how to set up product posting groups for WHT, but the same steps also apply to setting up business posting groups for WHT.  

## To set up a product posting group for withholding tax  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **WHT Product Posting Group**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify the code for the product posting group. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|Specify the description for the product posting group. You can enter a maximum of 50 alphanumeric characters.|  

3.  Choose the **OK** button.  

## To set up posting for withholding tax  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **WHT Posting Setup**, and then choose the related link.  

2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**WHT Business Posting Group**|Specifies the business posting group code for withholding tax.|  
    |**WHT Product Posting Group**|Specifies the product posting group code for withholding tax.|  
    |**WHT Calculation Rule**|Specifies the calculation rule for WHT, which is used with the amount specified in the **WHT Minimum Invoice Amount** field. This will help identify the transactions for which WHT will not be deducted.<br /><br /> For example, if you select the **Less than** option here and enter 100 in the **WHT Minimum Invoice Amount** field, then WHT will not be deducted for those transactions with an amount less than 100.|  
    |**WHT Minimum Invoice Amount**|Specifies the threshold amount that is below which WHT will not be deducted.|  
    |**WHT %**|Specifies the WHT rate. You must enter the rate without the percent sign.|  
    |**Realized WHT Type**|Specifies the mode of WHT calculation for purchases or sales of items.|  
    |**Prepaid WHT Account Code**|Specifies the general ledger account number to which sales WHT is to be posted.|  
    |**Payable WHT Account Code**|Specifies the general ledger account number to which purchase WHT is to be posted.|  
    |**WHT Report**|Specifies the withholding tax report type.|  
    |**Bal. Prepaid Account Type**|Specifies the type of balancing account for sales WHT transactions.|  
    |**Bal. Prepaid Account No.**|Specifies the account number or bank name for sales WHT transactions, based on the type selected in the **Bal. Prepaid Account Type** field.|  
    |**Bal. Payable Account Type**|Specifies the type of balancing account for purchase WHT transactions.|  
    |**Bal. Payable Account No.**|Specifies the account number or bank name for purchase WHT transactions. This is based on the type selected in the **Bal. Payable Account Type** field.|  
    |**WHT Report Line No. Series**|Specifies the number series for the WHT report line.|  
    |**Revenue Type**|Specifies the revenue type. For more information, see [Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md).|  
    |**Purch. WHT Adj. Account No.**|Specifies the account number on which to post purchase credit memo adjustments.|  
    |**Sales WHT Adj. Account No.**|Specifies the account number on which to post sales credit memo adjustments.|  
    |**Sequence**|Specifies the sequence in which the withholding tax posting setup information must be displayed in reports.|  

3.  Choose the **OK** button.  

## See Also  
 [Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)   
 [View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)   
 [Calculate and Post Withholding Tax Settlements](how-to-calculate-and-post-withholding-tax-settlements.md)   
 [Withholding Tax](withholding-tax.md)   
 [Australian Taxation Office (ATO)](https://www.ato.gov.au/)
