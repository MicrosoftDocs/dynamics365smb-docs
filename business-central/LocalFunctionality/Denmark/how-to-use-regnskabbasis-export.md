---
title: Exporting accounting data to Regnskab Basis in Denmark
description: Uploading of CSV file with accounting data to Regnskab Basis in Denmark.
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

# Exporting data to Regnskab Basis in Denmark  

Required by Danish bookkeeping act, the integration of Dynamics 365 Business Central, Regnskab Basis, with CSV file uploads marks a pivotal advancement in financial data management. This streamlined process empowers businesses to effortlessly import large datasets, enhancing accuracy and efficiency. This article explores the seamless CSV upload process within Regnskab Basis and its transformative impact on Denmark's financial landscape. You can export all mandatory required data as a CSV file according to the Danish requirements for the Regnskab Basis. Before you start you must have installed the **Audit Files Extension** Microsoft app and to have mapped GL Accounts with the Standard Chart of Accounts. This process is explained in this article: [Standard Chart of Account](how-to-set-up-standard-coa.md).   

## To export accounting data to Regnskab Basis 

1. Select the search button ![Magnifying glass button that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do"), enter **RB Accounting File**, and then select the related link.
2. On the **RB Accounting File** page, on the **Mapping Header** FastTab, in the **Please select a mapping header to use for export** field, specify the code for the mapping you will use. This is mapping with standard chart of accounts you will use.
3. On the same page on the **Period for Accounting File Export** FastTab system will populate default **Starting Date** and **Ending Date** based on mapping you are using, but you can ovwerwrite them if needed.
4. Additionally you need to set up the following fields on the same FastTab: 

    1. On the **Income Statement Amount** field, you can set up amount type you want to use. By default it is **Net Change**.  
    2. On the **Balance Sheet Amount** field, you can set up amount type you want to use. By default it is **Balance at Date**.
  
5. When you finish with set up, run the **Generate File** action. The *.csv file for amounts using in calculation methods, for GL Accounts mapped in mapping, and the starting and ending dates will be generated.
6. Once when the fiel has been generated, you can upload it manually to the official service.   


For more information, see [Danish Local Functionality](denmark-local-functionality.md).

## See also
[Financial Management](finance.md)  
[Understanding the General Ledger and Chart of Accounts](finance-general-ledger.md)  
[Work with Dimensions](finance-dimensions.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
