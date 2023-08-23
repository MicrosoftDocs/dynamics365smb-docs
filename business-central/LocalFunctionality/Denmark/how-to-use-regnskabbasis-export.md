---
title: Export accounting data to Regnskab Basis in Denmark
description: This article describes how to upload a CSV file with accounting data to Regnskab Basis in Denmark.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 5264, 5266, 5267, 5270, 
ms.date: 08/23/2023
ms.author: altotovi

---

# Export accounting data to Regnskab Basis in Denmark  

Required by Danish bookkeeping act Regnskab Basis, integrating Dynamics 365 Business Central with CSV file uploads marks a pivotal advancement in financial data management. This streamlined process empowers your business to effortlessly import large datasets, enhancing accuracy and efficiency. This article explains the seamless CSV upload process within Regnskab Basis and its transformative impact on Denmark's financial landscape. You can export all mandatory required data as a CSV file according to the Danish requirements for the Regnskab Basis. Before you start, install the **Audit Files Extension** Microsoft app and map GL Accounts with the Standard Chart of Accounts. This process is explained in this article, [Standard Chart of Account](how-to-set-up-standard-coa.md).   

## To export accounting data to Regnskab Basis 

1. Select the search button ![Magnifying glass button that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do"), enter **RB Accounting File**, and then select the related link.
2. On the **RB Accounting File** page, on the **Mapping Header** FastTab, in the **Please select a mapping header to use for export** field, specify the code for the mapping. This is the mapping with the standard chart of accounts you will use.
3. On the **Period for Accounting File Export** FastTab, the system populates a default **Starting Date** and **Ending Date** based on mapping you are using. You can update these fields as needed.
4. On the **Income Statement Amount** field, set up the amount type you want to use. The default value is **Net Change**.
5. On the **Balance Sheet Amount** field, set up amount type you want to use. The default value is **Balance at Date**.
6. When you finish with set up, select **Generate File**. The *.csv file for **amounts using in calculation methods**, **GL Accounts mapped in mapping**, and **starting and ending dates** is generated.
7. After the file is generated, upload it manually to the official service.   

For more information, see [Danish Local Functionality](denmark-local-functionality.md).

## See also
[Financial Management](finance.md)  
[Understanding the General Ledger and Chart of Accounts](finance-general-ledger.md)  
[Work with Dimensions](finance-dimensions.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
