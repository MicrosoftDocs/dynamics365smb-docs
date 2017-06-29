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
# How to: Complete the Configuration Questionnaire
You use the setup questionnaire to structure and document a detailed discussion about the customer’s specific needs. You also use it to collect setup data from the customer to configure the relevant FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> setup tables, such as the general ledger, inventory, and customers.  
  
> [!NOTE]  
>  You can also create your own setup questionnaire to meet your needs.  
  
### To complete the setup questionnaire  
  
1.  In the FIX INCLUDE HERE<!--[!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)] -->, select the company for which you want to complete the questionnaire. For more information, see [\($ S\_COMPANY How to: Select a Company $\)](../WorkingWithDynamics/-$-s_company-how-to-select-a-company-$-.md).  
  
2.  In the **Search** box, enter **Configuration Questionnaire**, and then choose the related link.  
  
3.  In the list, select the questionnaire for the company.  
  
4.  You can export the questionnaire into either Excel or XML.  
  
     On the **Actions** tab, choose **Export to Excel** and save the file.  
  
     \-or\-  
  
     On the **Actions** tab, choose **Export to XML**.  
  
     The following steps assume that you have exported the questionnaire to Excel.  
  
5.  Complete the configuration questionnaire by entering the answers in the Excel workbook. There are worksheets for each of the question areas that have been created for the questionnaire. Save the file.  
  
6.  On the **Home** tab, choose **Import from Excel**. Select the .xlsx file that you have saved.  
  
     On the **Home** tab, in the **Process** group, choose **Question Areas** to begin the process of validating and applying the answers to the setup questionnaire.  
  
 You can now review the completed setup questionnaire before applying the data to the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] database.  
  
 The next procedure provides an alternative way of accessing configuration questionnaires. It assumes that the configuration package that you have been provided includes questionnaires.  
  
### To complete a questionnaire from the configuration worksheet  
  
1.  After you import a configuration package, open the configuration worksheet.  
  
2.  For each table for which there is a question area, on the **Navigate** tab, in the **Setup** group, choose **Questions**. The questionnaire page opens.  
  
3.  Answer the questions, and then on the **Home** tab, in the **Process** group, choose **Apply Answers**.  
  
4.  Choose the **OK** button to close the questionnaire.  
  
## See Also  
 [How to: Create a New Company](../SetupAndAdministration/how-to-create-a-new-company.md)   
 [How to: Validate the Configuration Questionnaire](../SetupAndAdministration/how-to-validate-the-configuration-questionnaire.md)   
 [How to: Create Configuration Questionnaires](../SetupAndAdministration/how-to-create-configuration-questionnaires.md)