---
    title: How to Set Up Multiple Interest Rates
    description: You can calculate finance charges with multiple interest rates for a specific period. The interest calculation is similar for all financial charges, with variation only in the rate of interest for a specific period.

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
# How to: Set Up Multiple Interest Rates
Multiple interest rates are used for different periods for delayed payments in trade transactions. For example, a government specifies the maximum interest to be levied for a consumer. This interest rate can be changed twice a year on 01 January and 01 July. The interest rate between businesses (B2B) is agreed by the parties and there is no limit to that customer group. The announced rate is usually four percent more than the normal bank interest.

For each finance charge term code, you can specify multiple interest rates so that you can calculate finance charges with multiple interest rates for a specific period. This is helpful if you charge different interest on payments that are late. The interest calculation is the same for each financial charge, with variation only in the rate of interest for a specific period. For more information, see [How to: Collect Outstanding Balances](receivables-collect-outstanding-balances.md).

When you create a finance charge memo, the memo lines show the finance charges with different interest rates for each time period. For finance charge terms, you can define descriptions for each term, and you can define a description that is used when multiple interest rates are used. If no multiple interest rates exist, [!INCLUDE[navnow](includes/navnow_md.md)] will use the interest rate and period that is defined in the **Finance Charge Terms** window for the whole period of calculation.

## To set up multiple interest rates  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Finance Charge Terms**, and then choose the related link.  
2.  In the **Finance Charge Terms** window, select the required finance term, and then choose the **Interest Rates** action.  
3.  Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  Choose the **OK** button.  
5.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Reminder Terms**, and then choose the related link.  
6.  In the **Reminder Terms** window, select the required reminder term, and then choose the **Levels** action.  
7.  In the **Reminder Levels** window, select the **Calculate Interest** field.  

When you issue a finance charge memo, the memo shows the finance charges with multiple interest rates for a specific time period. The memo also contains the contact details of the customer, the company issuing the memo, the additional amount, and the total amount. The opening entry on the memo is displayed in bold. The finance charges are calculated with multiple interest rates for a specific time period and are printed after the opening entry of the memo.  

## See Also  
[How to: Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Setting Up Finance](finance-setup-finance.md)
