---
    title: Gather Customer Setup Values | Microsoft Docs
    description: You use the setup questionnaire to help reduce your implementation workload by streamlining the task of setting up the new company. You can generate the setup questionnaire in Business Central and then provide it to your customer as an Excel (.xls) or XML file.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 03/05/2018
    ms.author: sgroespe

---
# Gather Customer Setup Values
You use the setup questionnaire to help reduce your implementation workload by streamlining the task of setting up the new company. You can generate the setup questionnaire in [!INCLUDE[d365fin](includes/d365fin_md.md)] and then provide it to your customer as an Excel (.xls) or XML file.  

You can change all default values in a questionnaire to more closely match customer needs.  

> [!TIP]  
>  For more information about defining setup values in supply planning fields, see [Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md).  

When your customer completes the questionnaire, you import the file into the customer's new [!INCLUDE[d365fin](includes/d365fin_md.md)] company, which you have created based on industry-specific data templates that match the questionnaire. You and your customer validate the questionnaire answers before you apply them to the database, and then work directly in the database to set up the company.  

## To create a configuration questionnaire
You can use a questionnaire to help you determine the scope and needs of configuration. You can create a new questionnaire, or modify an existing questionnaire by adding new questions or question areas.  

 You can create questionnaires for setup-type tables only. For example you can use the tool to provide information to the following windows:  

-   Company Information  
-   Fixed Asset Setup  
-   General Ledger Setup  
-   Inventory Setup  
-   Assembly setup
-   Manufacturing Setup  
-   Purchases and Payables Setup  
-   Marketing Setup  
-   Service Setup  
-   Sales and Receivables Setup  
-   Warehouse Setup  

> [!NOTE]  
>  To see a complete list of setup tables, choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Setup**, and then choose the related link. To determine the scope of migration of records data, use migration functionality. For more information, see [Migrating Customer Data](admin-migrate-customer-data.md).  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Configuration Questionnaire**, and choose the related link.  
2. On the **Home** tab, choose **New**. The **Config. Questionnaire** window opens.  
3. Provide a code and description.  
4. On the **Home** tab, in the **Process** group, choose **Questions Areas**. The **Question Areas** window opens.  
5. On the **Home** tab, choose **New**. The **Question Area** window opens.  
6. In the **Code** field, enter a code for the question area.  
7. In the **Table ID** field, choose the ID of the table for which you want to collect information. The **Table Name** field is automatically filled in.  
8.  Optionally, in the **Description** field, enter a description. In general, the description should describe the type of information that is being collected.  
9. On the **Home** tab, choose **Update Questions**. Each field in the table is added to the questionnaire with a question mark following its label. You can rephrase the label to make it clear how the question should be answered. For example, if a field is called "Name," you could edit it to state "What is the name of <data being collected>." You can also provide additional information, for example, prescriptive guidance, in the **Reference** field. You can also use this field to provide a url address of a page that provides additional information.  

    As needed, you can also delete questions that you do not want to include in the questionnaire.  

    > [!NOTE]  
    >  The **Answer Option** field describes the type and format of the answer of the data that is appropriate. The **Answer** field contains user-supplied information.  
    >   
    >  As needed, you can also define default answers in the **Answer** field. These values are used by default for custom setup. However, the person filling in the questionnaire can modify and update the answer.  

10. Choose the **OK** button to close the window.  
11. Repeat these steps to add additional question areas.  
12. Choose the **Close** button.  

## See Also  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
