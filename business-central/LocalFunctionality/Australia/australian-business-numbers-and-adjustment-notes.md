---
title: Australian Business Numbers and Adjustment Notes
description: An Australian Business Number (ABN) is a single identifier for all business dealings with the tax office and for dealings with other government departments and agencies.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# Australian Business Numbers and Adjustment Notes
An Australian Business Number (ABN) is a single identifier for all business dealings with the tax office, and for dealings with other government departments and agencies.  

 ABNs and adjustment notes—or credit memos—are used to satisfy tax requirements.  

## ABN  
 All companies must register and apply for an ABN to report the details of payment summaries issued to their payees during the financial year. The payment summary includes the Tax File Numbers (TFN) or business numbers of the payees.  

## Adjustment Notes  
 Adjustment notes are issued by suppliers to a business when the amount of consideration for taxable supplies changes. The recipient needs an adjustment note to claim more or less GST credits than previously claimed.  

 Section 19-10 of A New Tax System (Goods and Services Tax) Act 1999 defines an adjustment event as any event that has the effect of:  

-   Canceling a supply or acquisition.  
-   Changing the consideration for a supply or acquisition.  
-   Causing a supply or acquisition to start or stop being a taxable supply or creditable acquisition.  

An adjustment event may result in an increase or decrease to your net amount for the tax period.  

Adjustment notes—or credit memos—should be connected to an invoice.  

Because credit memos are used for adjustment notes, each credit memo should satisfy all of the legal requirements for an adjustment note. Each credit memo should have an original invoice number, date, and reason code assigned to it. The following fields are included in the adjustment note:  

- **Adjustment Applies to**: The number of the document to which the adjustment note applies. If you use the **Copy Document** function, this field populates automatically. You must enter a reason code before the transaction can be posted. You can use this field to create an adjustment note for a paid or closed transaction.  

- **Adjustment Reference No**: The number of the adjustment note. For **Sales & Receivables**, the number assigned to the posted document populates automatically in this field.  

- **Adjustment Note Date**: Automatically populated from the document date.  

- **Adjustment** and **BAS Adjustment**: These entries populate automatically. Some credit memos are Business Activity Statement (BAS) adjustments. Adjustment notes can only be applied against a single document.  

## See Also  
 [Enter Australian Business Numbers](how-to-enter-australian-business-numbers.md)   
 [Australia Local Functionality](australia-local-functionality.md)
