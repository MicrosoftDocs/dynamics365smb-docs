---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Create Journal Opening Balances
ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> includes several batch jobs that are provided to help in the transfer of legacy account balances to a newly configured company. You can easily transfer this data for the customer journal, the vendor journal, the item journal, and the G\/L journal. The first step is to create a configuration package that includes the setup tables for those journals. The following procedure assumes that this step is completed. The procedure describes the subsequent steps, which include applying the package that is provided by a partner.  
  
 Before you start, make sure that you are on the RapidStart Services Role Center page. It provides the correct context for your configuration work. To change your Role Center home page, see [How to: Change Role Centers](../how-to-change-role-centers.md). Choose the RapidStart Profile ID.  
  
### To apply the entries in a journal to a new company  
  
1.  Configure a new company and apply a configuration package to it. For more information, see [How to: Configure a Company with the RapidStart Wizard](../how-to-configure-a-company-with-the-rapidstart-wizard.md).  
  
     The new company does not contain information about journal opening balances.  
  
2.  Open the configuration worksheet, and import existing data about customers, items, vendors, and the general ledger. For more information, see [How to: Migrate Customer Data](../how-to-import-customer-data.md).  
  
3.  On the **Report** tab, in the **Create** group, choose the appropriate batch job, for example, **Create G\/L Journal Lines**.  
  
     Fill in the **Options** FastTab as appropriate, and set filters as needed. For example, in the **Journal Template** field, enter a name.  
  
     Choose the **OK** button. The records now are in the journal, but the amounts are empty.  
  
4.  Export the journal table to Excel and manually enter the posting and balancing account information from the legacy data. Import and apply the table information into the new company. The journal lines are ready for posting.  
  
5.  In the configuration worksheet, select the journal line table, and on the **Actions** tab, in the **Show** group, choose **Database Data**.  
  
6.  Review the information, and then on the **Home** tab, in the **Process** group, choose **Post**.  
  
7.  Repeat the steps to import and post various general ledger balances.  
  
 You can use this procedure to import journal information for each journal type.  
  
## See Also  
 [Use Templates to Prepare Customer Data for Migration](../use-templates-to-prepare-customer-data-for-migration.md)   
 Create Item Journal Lines   
 Create Customer Journal Lines   
 Create Vendor Journal Lines   
 Create G-L Acc. Journal Lines   
 [Tips and Tricks: RapidStart Services](../tips-and-tricks-rapidstart-services.md)