---
    title: How to Create Journal Opening Balances
    description: Batch jobs are provided to help transfer legacy account balances to a newly configured company. You can easily transfer this data with journals postings.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/14/2021
    ms.author: edupont

---
# Create Journal Opening Balances

[!INCLUDE[prod_short](includes/prod_short.md)] includes several batch jobs that are provided to help in the transfer of legacy account balances to a newly configured company. You can easily transfer this data with the customer journal, the vendor journal, the item journal, or the G/L journal.

The first step is to create a configuration package that includes the setup tables for those journals. The following procedure assumes that this step is completed. For more information, see [Set Up Company Configuration](admin-set-up-company-configuration.md). This procedure describes the subsequent steps, which include applying the package that is provided by a partner.  

Before you start, make sure that you are using the Administration Role Center page because it provides the correct context for your configuration work. For more information, see [Change Basic Settings](ui-change-basic-settings.md).

## To apply the entries in a journal to a new company

1. Configure a new company and apply a configuration package to it. For more information, see [Configure a Company with the RapidStart Wizard](admin-how-to-configure-a-company-with-the-rapidstart-wizard.md).  

    The new company does not contain information about journal opening balances.  

2. Open the configuration worksheet and import existing data about customers, items, vendors, and the general ledger. For more information, see [Migrate Customer Data](admin-migrate-customer-data.md).  

    Now you have master data in place. Next, you add the opening balances. The following steps describe how to create journal lines for G/L accounts, but the same apply to creating journal lines for customers, vendors, and items.  
3. Choose the **Create G/L Acct. Journal Lines** action.  
4. Fill in the **Options** FastTab as appropriate, and set filters as needed. For example, in the **Journal Template** field, enter a name.  
5. Choose the **OK** button. The records are now in the journal, but the amounts are empty.  
6. Export the journal table to Excel and manually enter the posting and balancing account information from the legacy data.
7. Import and apply the table information into the new company. The journal lines are ready for posting.  
8. In the configuration worksheet, select the journal line table, and then choose the **Database Data** action.  
9. Review the information, and then choose the **Post** action.  
10. Repeat the steps to import and post any other opening balances.  

> [!TIP]
> You can use the same batch jobs to add opening balances whenever you register a new customer or vendor that you have done business with before but not registered in [!INCLUDE [prod_short](includes/prod_short.md)]. Just search for the relevant task, and then choose the relevant link.

## See Also

[Apply Configurations to New Companies](admin-apply-configuration-to-new-companies.md)  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]