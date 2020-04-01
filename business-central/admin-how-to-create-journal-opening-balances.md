---
    title: How to Create Journal Opening Balances | Microsoft Docs
    description: Business Central includes several batch jobs that are provided to help in the transfer of legacy account balances to a newly configured company. You can easily transfer this data with journals postings.
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
# Create Journal Opening Balances
[!INCLUDE[d365fin](includes/d365fin_md.md)] includes several batch jobs that are provided to help in the transfer of legacy account balances to a newly configured company. You can easily transfer this data with the customer journal, the vendor journal, the item journal, or the G/L journal.

The first step is to create a configuration package that includes the setup tables for those journals. The following procedure assumes that this step is completed. For more information, see [Set Up Company Configuration](admin-set-up-company-configuration.md). This procedure describes the subsequent steps, which include applying the package that is provided by a partner.  

Before you start, make sure that you are using the Administration Role Center page because it provides the correct context for your configuration work. For more information, see [Change Basic Settings](ui-change-basic-settings.md).

## To apply the entries in a journal to a new company  
1. Configure a new company and apply a configuration package to it. For more information, see [Configure a Company with the RapidStart Wizard](admin-how-to-configure-a-company-with-the-rapidstart-wizard.md).  

    The new company does not contain information about journal opening balances.  

2. Open the configuration worksheet and import existing data about customers, items, vendors, and the general ledger. For more information, see [Migrate Customer Data](admin-migrate-customer-data.md).  
3. Choose, for example, the **Create G/L Acct. Journal Lines** action.  
4. Fill in the **Options** FastTab as appropriate, and set filters as needed. For example, in the **Journal Template** field, enter a name.  
5. Choose the **OK** button. The records are now in the journal, but the amounts are empty.  
6. Export the journal table to Excel and manually enter the posting and balancing account information from the legacy data.
7. Import and apply the table information into the new company. The journal lines are ready for posting.  
8. In the configuration worksheet, select the journal line table, and then choose the **Database Data** action.  
9. Review the information, and then choose the **Post** action.  
10. Repeat the steps to import and post any other opening balances.  

## See Also  
[Apply Configurations to New Companies](admin-apply-configuration-to-new-companies.md)  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
