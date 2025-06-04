---
title: GST Reconciliation
description: GST Reconciliation

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# GST Reconciliation


This topic explains the setups and process of GST reconciliation.

## Overview

- Line wise details of all invoices, supplementary invoices, debit notes and credit notes issued by a vendor or supplier towards Outward supplies made during a month shall be reported in GSTR-1 by 10th of the succeeding month.
- Sales uploaded by the supplier or vendor in GSTR-1 are auto-reflected in GSTR-2A and GSTR-2 of the buyer as Inward supplies. For example, if the buyer purchases goods or services from 100 vendors in a month, the details of all such purchases will be reflected in GSTR-2A & GSTR-2 of the buyer, provided all 100 vendors have uploaded their sales in GSTR-1.
- Purchase transactions posted in the system for preceding month shall be reconciled with the supplier-uploaded information in GSTR-2A. However, there may be certain discrepancies between the two, due to the following reasons:
  - Supplier or suppliers have ignored to upload invoice details in their GSTR-1
  - Supplier entered wrong GSTIN of the buyer
  - Omission of entering any invoice by the buyer
  - Invoice No. & Date, Tax Amounts may have wrongly entered by the buyer in there books of account.
- The buyer can add, modify and delete the auto-populated information in GSTR-2. Such information is made available to supplier in GSTR-1A. The supplier can accept or reject the modifications made by the buyer and supplier’s GSTR-1 shall stand amended to the extent of modifications accepted.
- Buyer can avail credit with respect to invoice lines matched with the information in GSTR-2A. Though buyer can avail mismatched credit on a provisional basis, the same will get auto-reversed, if the supplier fails to upload invoices.
- To summarize, Reconciliation feature is required to:
  - Identify the purchase transactions, which are matched or unmatched with GSTR-2A. 
  - To ascertain the modifications required to be made in GSTR-2 and follow up the supplier to accept the same
  - Monitor unmatched transaction lines, if credit is availed on a provisional basis.
- Purchases as per the books of account of buyer shall be matched with the supplier-uploaded information in GSTR-2A,  every month before uploading GSTR-2 by the buyer.


## To set up GST component mapping reconciliation.

- Mapping GST reconciliation fields with GST components is a pre-requisite for GST Reconciliation. Unless it is done, reconciliation can not happen in the system.

   1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Component Mapping Recon.**, and then choose the related link.
   2. Fill in the fields as described in the following table.
    
        |Field|Description| 
        |---------------------------------|  ---------------------------------------| 
        |**GST Component Code**|Specifies the different components of GST.|
        |**GST Reconciliation Field No.**|Specifies the relevant reconciliation field against the component.|
        |**GST Reconciliation Field Name**|Specifies the description of the reconciliation field.|
        |**ISD Ledger Field No.**|Specifies the relevant input service distribution field against the component.|
        |**ISD Ledger Field Name**|Specifies the description of the input service distribution field.|

## GST reconciliation process

- Reconciliation feature enables the user to reconcile the posted purchase transactions with GSTR-2A downloaded from GSTN portal.

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Reconciliation List.**, and then choose the related link, and click **New** to create a new reconciliation document.
  2. Select relevant GST registration number in **GSTIN No.** field for which reconciliation needs to be done. **Month**, **Year**, **Posting Date** fields should not be blank.
  3. **GST Recon. Tolerance** field will be updated with the value mentioned on **General Ledger Setup**.
  4. **Input Service Distributor** field will be marked true if the GSTIN is assigned for input service distribution location.
  5. Click on Action on the ribbon -> Functions -> Import GSTR-2A, choose the relevant file and the data will be updated in **Periodic GSTR-2A Data**.
  6. Click on **Fill GST Reconciliation** and the posted GST transactions will be populated in **GST Reconciliation Lines**.
 
- Purchase Transactions with Vendor Type – Unregistered, Imports and Composite are excluded from Reconciliation. [This is due to the reason that unregistered and import vendors are not registered with GSTN authorities and hence will not upload their supplies in GSTR-1. Hence the same are not reflected in GSTR-2]
- Invoice having multiple lines are clubbed together and shown as one line in GST Reconciliation feature i.e. Total Taxable amount and Tax Amounts (CGST, SGST, IGST).
- Periodic GSTR-2A can be downloaded in Excel or XML format. The following fields in GSTR-2A are matched with GST Reconciliation lines
   - External Document No.
   - Tax Amounts (IGST, CGST, SGST)
   - Vendor Invoice Date
   - GSTIN of the Supplier
   - Document Date
- GSTR-2A can be downloaded and reconciled with existing GST Reconciliation lines multiple times, but posting can be done only once in a month.
- For a given month, GST Reconciliation includes lines pertaining to purchase transactions (Registered Vendor including Reverse Charge) posted during the month and the lines, which are posted and unmatched during the previous months.
- GST Reconciliation lines shown in GST Reconciliation page are coming from following transactions:
    - Registered Vendor (Including Reverse Charge Posting Group)
    - Sub-Contracting Invoices (Registered Vendor)
    - Service Transfers 
    - Transfer Orders
- GST Reconciliation Lines shown in the selected month are having purchase transaction (Invoice & Credit Memo) till the End Date for selected month.
- Once the GST Reconciliation lines are posted, system will not generate any accounting entries. 'Reconciled', 'Reconciliation Month' and 'Reconciliation Year' will be updated in Detailed GST Ledger Entries. GST Reconciliation lines with status 'Reconciled' will not be considered again for reconciliation.

## Related information 
[GST E-Way Bill](GST-E-Way-Bill.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
