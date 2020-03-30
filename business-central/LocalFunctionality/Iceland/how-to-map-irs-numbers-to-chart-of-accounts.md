---
    title: How to Map IRS Numbers to Chart of Accounts
    description: Companies in Iceland are required to send the tax authority a data file in a predefined format. Before you can do this, you must map predefined Internal Revenue Service (IRS) account codes to general ledger accounts.

    services: project-madeira 
    documentationcenter: ''
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
# Map IRS Numbers to Chart of Accounts
Companies in Iceland are required to send the tax authority a data file in a predefined format. Before you can do this, you must map predefined Internal Revenue Service (IRS) account codes to general ledger accounts.  

## To create an Internal Revenue Service number  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **IRS Number**, and then choose the related link.  
2.  Choose the **New** action.  
3.  On the new line, enter a number in the **IRS number** field, and provide a name in the **Name** field.  
4.  Select the **Reverse Prefix** check box if you want the negative operator to be reversed on the balance of the general ledger account that the IRS number is mapped to.  
5.  Choose the **OK** button.  

## To map an IRS number to a general ledger account  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
2.  Select a general ledger account that has an **Account Type** of **Posting**.  
3.  In the **IRS Number** field, select an IRS number from the list.  

## See Also  
 [Special Data Output and Reports for the Tax Authority](special-data-output-and-reports-for-the-tax-authority.md) 
