---
    title: How to Prepare for VAT Transactions Reports | Microsoft Docs
    description: You must submit periodic reports to the tax authorities to list all transactions that include VAT. The tax authority establishes the thresholds at which reporting is required. Currently, the threshold is set at zero, meaning that all transactions are to be reported. To prepare for these reports, you must set up VAT posting to include VAT transaction report amounts.
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
# How to: Prepare for VAT Transactions Reports
You must submit periodic reports to the tax authorities to list all transactions that include VAT. The tax authority establishes the thresholds at which reporting is required. Currently, the threshold is set at zero, meaning that all transactions are to be reported. To prepare for these reports, you must set up VAT posting to include VAT transaction report amounts.  
  
### To set up VAT transaction amounts  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Posting Setup**, and then choose the related link.  
  
2.  On the **Navigate** tab, choose **VAT Transaction Report Amount**.  
  
3.  Fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---
    title: How to Prepare for VAT Transactions Reports | Microsoft Docs
    description: You must submit periodic reports to the tax authorities to list all transactions that include VAT. The tax authority establishes the thresholds at which reporting is required. Currently, the threshold is set at zero, meaning that all transactions are to be reported. To prepare for these reports, you must set up VAT posting to include VAT transaction report amounts.
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

------
    title: How to Prepare for VAT Transactions Reports | Microsoft Docs
    description: You must submit periodic reports to the tax authorities to list all transactions that include VAT. The tax authority establishes the thresholds at which reporting is required. Currently, the threshold is set at zero, meaning that all transactions are to be reported. To prepare for these reports, you must set up VAT posting to include VAT transaction report amounts.
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

------
    title: How to Prepare for VAT Transactions Reports | Microsoft Docs
    description: You must submit periodic reports to the tax authorities to list all transactions that include VAT. The tax authority establishes the thresholds at which reporting is required. Currently, the threshold is set at zero, meaning that all transactions are to be reported. To prepare for these reports, you must set up VAT posting to include VAT transaction report amounts.
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

---------------------------------|---------------------------------------|  
    |**Individual Person**|Select if this customer is an individual person.|  
    |**Resident**|Specify if the customer is a resident in Italy.<br /><br /> If a customer is not a resident, you must also specify a tax representative on the **Foreign Trade** FastTab.|  
    |**First Name**|Specifies the first name of the person.|  
    |**Last Name**|Specifies the last name of the person.|  
    |**Date of Birth**|Specifies the date of birth of the person.|  
    |**Place of Birth**|Specifies the place of birth of the person.|  
  
3.  If the customer is not resident in Italy and is not an individual person, you must specify a tax representative for the customer.  
  
    > [!NOTE]  
    >  Before you can specify a tax representative, you must have created the tax representative as a contact.  
  
#### To specify a tax representative for a non-resident customer  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customer Card**, and then choose the related link.  
  
2.  On the **Foreign Trade** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Tax Representative Type**|Specifies if the tax representative is a customer or a contact. You must set this field to **Contact**.|  
    |**Tax Representative No.**|Specify the contact that is the tax representative for this customer.|  
  
 You have set up information so that ADD INCLUDE<!--[!INCLUDE[navnow](how-to-create-electronic-vat-transactions-reports.md).  
  
## See Also  
 [How to: Update VAT Transactions Data](how-to-update-vat-transactions-data.md)   
 [How to: Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md)   
 [Italian VAT](italian-vat.md)   
 VAT Report Setup