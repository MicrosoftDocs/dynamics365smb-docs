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
# How to: Validate the Configuration Questionnaire
It is important to validate the setup questionnaire before you apply it to the ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> format. It is also a way to make sure that data formatting is preserved during the import from Excel.  
  
 A common validation task is to check that text strings are not entered into date fields. This review process is necessary because the format of the answer in the questionnaire is not validated automatically when the **Apply Answers** function is run.  
  
> [!NOTE]  
>  In general, validation of the setup questionnaire is a manual process only. However, there are checks for regional formatting inconsistencies. In addition, you will have errors if the structure of your ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> database does not match the structure of the migration database.  
  
### To validate the setup questionnaire  
  
1.  In the **Configuration Questionnaire** window, select the questionnaire you want. On the **Home** tab, in the **Process** group, choose **Question Areas**.  
  
2.  Select a **Question Area** and choose **Edit**.  
  
3.  For each question, validate that the value in the **Answer** field corresponds to the format provided in the **Answer Option** field. For example, validate that the address of a company is in text format.  
  
4.  If you find errors, you can troubleshoot and make corrections in Excel by exporting the questionnaire, and then importing it again. Alternatively, you can also correct errors directly in ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> as you review the answers in the **Question Areas** window.  
  
5.  Repeat these steps for each **Question Area**.  
  
 After you have completed your validation, your data is ready to be applied to the database.  
  
## See Also  
 [How to: Apply Answers from the Configuration Questionnaire](../FullExperience/how-to-apply-answers-from-the-configuration-questionnaire.md)