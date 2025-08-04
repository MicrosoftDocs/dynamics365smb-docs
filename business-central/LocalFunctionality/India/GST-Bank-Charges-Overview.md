---
title: Setting up GST for Bank Charges
description: Setting up GST for Bank Charges

author: v-debapd

    
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Setting Up GST for Bank Charges 


As per GST Law, GST is applicable on bank charges and ITC can be availed for specified services.  As per Rule 54(2) of CGST Rules, 2017, Banks shall issue a tax invoice or any other document in lieu of tax invoice. In case if an invoice is not provided by the bank, then the bank statement shall be deemed to be an invoice. Such document shall be construed as Tax invoice even if it is not serially numbered and whether or not it contains the address of recipient of taxable service. 

Bank charges can be Intrastate or Interstate. CGST & SGST are applicable if the bank and customer are located in the same state. IGST is applicable if both are in different states. 

The place of supply of banking and other financial services to any person shall be the location of the recipient of services on the records of the supplier of services. If the location of recipient of services is not on the records of the supplier, the place of supply shall be the location of the supplier of services. 

The place of supply of banking and other financial services shall be the location of the supplier of services. If any services are received from a foreign bank by an Indian customer, then the place of supply for such services becomes the place where the foreign bank is located i.e. outside India and hence any charges collected towards such services are not subject to India GST.


### The following setups are required: 

- [Bank Accounts](gst-bank-charges-overview.md#to-set-up-gst-on-a-bank-account)
- [Bank Charges Master](gst-bank-charges-overview.md#to-set-up-gst-on-bank-charges-master)
- [Bank Charges Deemed Value Setup](gst-bank-charges-overview.md#to-set-up-gst-on-bank-charges-deemed-value-setup)


## To set up GST on a bank account

This setup is required to specify that this bank is eligible to calculate GST on bank charges.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Account**, and then choose the related link.
2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**State Code**|This field is required for GST calculation in Bank Charges transactions.|
    |**GST Registration Status**|GST Registration type can be Blank or Registered. If GST registration No. is added in Bank Account Master the status will be updated as Registered.|
    |**GST Registration No.**|Registration No. of Bank shall be entered here. Registration number is mandatory, if GST Registration Status is Registered. Registration No. comprises 15-digits.|

## To set up GST on bank charges master

This setup is required to calculate GST on bank charges.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Charges**, and then choose the related link.
2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**Code**|Specifies the unique identification code of Bank Charge.|
    |**Description**|Specifies the description of the Bank Charge.|
    |**Account**|Specifies the general ledger account for Bank Charge.|
    |**Foreign Exchange**|Specifies the Bank Charges that are applicable on Foreign Exchange Sales or Purchase under GST. For foreign Exchange bank charges, the GST calculation is based on Deemed Value of purchase or sale.|
    |**GST Group Code**|Specifies the relevant GST Group Code.|
    |**GST Credit**|GST Credit can be Availment or Non-Availment. This field by default displays Availment. If credit cannot be availed on any Bank Charges, then Non-Availment shall be selected manually from the drop down. |
    |**HSN/SAC**|All HSN/SAC Codes for GST Group code selected above shall be displayed as a dropdown for this field, business user has to select appropriate code.|
    |**Exempted**|This field is checked if the Bank Charges are exempted from payment of GST.|

## To set up GST on bank charges deemed value setup

This setup is required to estimate the Deemed Value for calculation of GST on foreign exchange purchases.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Charges Deemed Value Setup**, and then choose the related link.
2. Fill in the fields as described in the following table.
    
    |Field|Description| 
    |---------------------------------|  ---------------------------------------| 
    |**Bank Charges Code**|Specifies the code of Bank Charge from drop down list.|
    |**Lower Limit**|Specifies the lower limit of the bank charge code.|
    |**Upper Limit**|Specifies the upper limit of the bank charge code.|
    |**Formula**|Specifies the formula of the charge calculation.|
    |**Min. Deemed Value**|Specifies the minimum value.|
    |**Max. Deemed Value**|Specifies the maximum value.|
    |**Deemed %**|Specifies the percentage of calculation.|
    |**Fixed Amount**|Specifies the fixed deemed value.|



## Related information 
[GST Bank Charges Transaction](GST-Bank-Charges-Transaction.md)



















[!INCLUDE[footer-include](../../includes/footer-banner.md)]