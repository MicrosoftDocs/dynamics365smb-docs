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
# How to: Set Up Account Schedules
You can use account schedules to arrange and organize accounts in the chart of accounts. For more information, see the Acc. Schedule Name table.  
  
### To set up account schedules  
  
1.  In the **Search** box, enter **Account Schedules**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  In the **Account Schedule Names** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Name**|The name of the account schedule. You can enter a maximum of 20 alphanumeric characters.|  
    |**Description**|The description of the account schedule.|  
    |**Default Column Layout**|The default column layout name for the account schedule.|  
    |**Analysis View Name**|The name of the analysis view on which to base the account schedule. For more information, see the Analysis View table.|  
  
4.  Select the required **CASH FLOW** account schedule to create cash flow statements, and then, on the **Home** tab, choose **Edit Account Schedule**.  
  
5.  In the **Account Schedule - CASH FLOW** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Row No.**|The number for the account schedule line. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description of the account schedule line.|  
    |**Row Type**|**Net Change** – The net change in account balances during the period.<br /><br /> –or–<br /><br /> **Balance at Date** – The account balances at the end of the period.<br /><br /> –or–<br /><br /> **Beginning Balance** – The account balances at the beginning of the period.|  
  
6.  Choose the **OK** button.  
  
7.  Select the **INCOME** account schedule, and then, on the **Home** tab, choose **Edit Account Schedule**.  
  
8.  In the **Account Schedule - INCOME** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Row No.**|The number for the account schedule line. You can enter a maximum of 10 alphanumeric characters.|  
    |**Description**|The description of the account schedule line.|  
    |**Totaling Type**|**Posting Accounts** – To calculate the total from posting accounts in the chart of accounts.<br /><br /> –or–<br /><br /> **Total Accounts** – To calculate the total from the total accounts and end-total accounts in the chart of accounts.<br /><br /> –or–<br /><br /> **Formula** – To calculate the total from other rows in the account schedule.<br /><br /> –or–<br /><br /> **Underline** – To place an underline in each column for the row.<br /><br /> –or–<br /><br /> **Double Underline** – To place a double underline in each column for the row.<br /><br /> –or–<br /><br /> **Set Base for Percent** – To set a base for calculating a percentage.|  
    |**New Page**|Select to provide a page break after the current account.|  
  
9. Choose the **OK** button.  
  
## See Also  
 Account Schedule Column Layout   
 [Account Schedule-duplicate](../FullExperience/\($%20R_25%20Account%20Schedule%20$\)-duplicate.md)   
 Account Schedule Layout