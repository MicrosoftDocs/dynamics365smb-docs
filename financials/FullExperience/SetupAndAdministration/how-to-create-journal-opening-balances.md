---
title: "How to: Create Journal Opening Balances"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "migrating, transactions"
  - "transctions, migrating"
  - "journals, migrating data"
  - "journals, creating opening balances"
ms.assetid: 8bdddba9-93e8-4fd7-aa86-de4c0fddc35d
caps.latest.revision: 3
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Create Journal Opening Balances
ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> includes several batch jobs that are provided to help in the transfer of legacy account balances to a newly configured company. You can easily transfer this data for the customer journal, the vendor journal, the item journal, and the G\/L journal. The first step is to create a configuration package that includes the setup tables for those journals. The following procedure assumes that this step is completed. The procedure describes the subsequent steps, which include applying the package that is provided by a partner.  
  
 Before you start, make sure that you are on the RapidStart Services Role Center page. It provides the correct context for your configuration work. To change your Role Center home page, see [How to: Change Role Centers](../GettingStarted/how-to-change-role-centers.md). Choose the RapidStart Profile ID.  
  
### To apply the entries in a journal to a new company  
  
1.  Configure a new company and apply a configuration package to it. For more information, see [How to: Configure a Company with the RapidStart Wizard](../SetupAndAdministration/how-to-configure-a-company-with-the-rapidstart-wizard.md).  
  
     The new company does not contain information about journal opening balances.  
  
2.  Open the configuration worksheet, and import existing data about customers, items, vendors, and the general ledger. For more information, see [How to: Migrate Customer Data](../SetupAndAdministration/how-to-migrate-customer-data.md) and [How to: Import Customer Data](../SetupAndAdministration/how-to-import-customer-data.md).  
  
3.  On the **Report** tab, in the **Create** group, choose the appropriate batch job, for example, **Create G\/L Journal Lines**.  
  
     Fill in the **Options** FastTab as appropriate, and set filters as needed. For example, in the **Journal Template** field, enter a name.  
  
     Choose the **OK** button. The records now are in the journal, but the amounts are empty.  
  
4.  Export the journal table to Excel and manually enter the posting and balancing account information from the legacy data. Import and apply the table information into the new company. The journal lines are ready for posting.  
  
5.  In the configuration worksheet, select the journal line table, and on the **Actions** tab, in the **Show** group, choose **Database Data**.  
  
6.  Review the information, and then on the **Home** tab, in the **Process** group, choose **Post**.  
  
7.  Repeat the steps to import and post various general ledger balances.  
  
 You can use this procedure to import journal information for each journal type.  
  
## See Also  
 [Use Templates to Prepare Customer Data for Migration](../SetupAndAdministration/use-templates-to-prepare-customer-data-for-migration.md)   
 Create Item Journal Lines   
 Create Customer Journal Lines   
 Create Vendor Journal Lines   
 Create G\-L Acc. Journal Lines   
 [Tips and Tricks: RapidStart Services](../SetupAndAdministration/tips-and-tricks-rapidstart-services.md)