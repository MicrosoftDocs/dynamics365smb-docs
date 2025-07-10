---
title: Set up VERIFACTU [ES]
description: Learn how to set up and use VERIF*ACTU in the Spanish version of Business Central.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Verifactu, SFI, e-invoice, Spanish version
ms.search.form: 
ms.date: 07/11/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# VERI*FACTU rules in Spain  

VERI*FACTU is a regulatory framework introduced by the Spanish government to modernize and secure electronic invoicing systems, with the primary goal of combating tax fraud and enhancing transparency in business transactions. It is governed by Royal Decree 1007/2023, later amended by Royal Decree 254/2025, and forms part of Spain’s broader Anti-Fraud Law 11/2021. 

VERI*FACTU refers to a “verifiable invoicing system”—a type of computerized invoicing system (SIF) that can optionally send invoice records in real time to the Spanish Tax Agency (AEAT).  

Businesses in Spain have an option to use the [SII](sii-setup.md) and in this case VERI*FACTU (SIF) rules will not apply to them. [SII](sii-setup.md) can be enforced for large companies with an annual turnover exceeding the tharshhold, but businesses may also opt in voluntarily to report SII. For all other cases, SIF will be mandatory.  

## Set up VERI*FACTU in the Spanish version 

Dynamics 365 Business Central supports VERI*FACTU frameworks using integration with the B2Brouter API through our default connector. To setup this mode, follow these steps: 

### Disbale SII module   

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SII Setup**, and then select the related link.  
2. On the **General** FastTab, be sure the **Enabled** field is not selected.  

More details about how to setup the SII can be found [here](sii-setup.md).  

### Enable B2BRouter connector 

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link. 
2. Choose the **Install E-Documents integration from AppSource** action to open the **Microsoft AppSource apps** page.  
3. Choose the **B2BRouter** connector, and then select the **View on AppSource** action.  
4. Install the app from the AppSource.   
5. On the **E-Document Service** page, change the **Service Integration** to **B2BRouter**.  
6. On the **E-Document Service** page, select the **Setup Service Integration** action. 
7. On the **B2BRouter Connection Setup** page, enter the **API-KEY** to specify the key you'll use for your B2BRouter environment and the **ProjectID** field to specify the project name for the B2BRouter environment. 
8. If you want to use this connector in sandbox mode, select the **Staging Mode** field.   
9. Continue with the [nonservice provider setup steps](../../finance-how-setup-edocuments-external.md).   

> [!NOTE]
> Before you enable B2BRouter connection you must get credentials directly from B2BRouter. Please be aware that this service may be subject to charges.  

> [!IMPORTNAT]
> Microsoft is committed to continuously enhancing the E-Document Framework in Dynamics 365 Business Central to ensure full compliance with Spain’s VERI*FACTU regulation. Our goal is to deliver a fully integrated, out-of-the-box solution that enables customers to meet all legal requirements directly within Business Central—without the need for third-party integrations—as soon as possible. All updates and progress on this initiative will be shared here.  


## Related information 

- [SII - Invoice and Credit Memo Types in Sales and Purchase Documents](SII-invoice-types-sales-purchase-documents.md)
- [Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
