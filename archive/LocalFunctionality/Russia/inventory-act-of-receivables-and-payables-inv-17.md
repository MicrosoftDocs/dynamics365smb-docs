---
    title: Inventory Act of Receivables And Payables INV-17
    description: The inventory act of receivables and payables feature enables you to prepare an inventory of debts and liabilities, and print reports in different formats.

    documentationcenter: ''
    author: SorenGP

    ms.prod: "dynamics-nav-2017"
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Inventory Act of Receivables And Payables INV-17
The inventory act of receivables and payables feature enables you to prepare an inventory of debts and liabilities, and print reports in the following formats:  

- INV-17  
- Supplement to INV-17  

## Setting Up a Number Series for Inventory Acts  
The following procedure shows how to set up a number series for inventory acts.  

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Setup**, and then choose the related link.  
2. In the **General Ledger Setup** window, fill in the **Contractor Invent. Act Nos.** field.   

## Inventory Act Processing  
You can create and process inventory acts of contractors' accounts. You can print inventory acts.  

### Creating an Inventory Act Card  
The following procedure shows how to create an inventory act card.  

1.  Choose the **General Ledger** action, choose the **Analysis & Reporting** action, and then choose the **Contractor Invent. Act.** action.
2.  In the **Inventory Account Card** window, enter information in the following fields:  

    |Field|Description|  
    |-----------|-----------------|  
    |**No.**|This field displays the number of the act, and is filled in automatically from the number series.|  
    |**Act Date**|This field displays the act date, and is filled in with the work date.|  
    |**Inventory Date**|This field displays the date of inventory, and is filled with the work date. Debts and liabilities will be calculated on this date.|  
    |**Reason Document Type**|Select the type of reason document from the following:<br /><br /> -   **Order**<br />-   **Resolution**<br />-   **Regulation**|  

3.  Choose the **Add Lines** action.  

    > [!NOTE]  
    >  You must not set filters.  

 Debts and liabilities for vendors and customers are calculated, and lines are created. For each customer and vendor, the total debt and the total liability amount (taking posting groups into account) on the inventory date are calculated, and shown in a separate line. The line fields are listed in the following table.  

|Field|Description|  
|-----------|-----------------|  
|**Contractor Type**|This field displays the contractor type (Customer, Vendor).|  
|**Contractor No.**|This field displays the number corresponding to the contractor.|  
|**Contractor Name**|This field displays the name of the contractor.|  
|**Posting Group, G/L Account No.**|This field displays the posting group and the receivables or payables account for which the debt or liability amount is calculated.|  
|**Category**|This field displays the amount category (Debts, Liabilities).|  
|**Total Amount**|This field displays the total amount of debts or liabilities.|  
|**Confirmed Amount**|This field displays the total amount of debts or liabilities by default.|  

### Changing Separate Lines in an Inventory Act  
The following procedure shows how to change individual lines in an inventory act in the **Inventory Account Card** window.  

1. Specify whether the amount (or part of the amount) is one of the following:  

- Confirmed by contractor  
- Not confirmed  
- Overdue  

2. If the amount is not confirmed, enter the amount that is not confirmed in the **Not Confirmed Amount** field.
3. If the amount is overdue, enter the overdue amount in the **Overdue Amount** field.  
3. To correct a line that has an incorrect amount (for instance, if some documents are not posted, or not applied), choose the **Add Lines** action.  
5.  Select the vendor or customer code, and then choose the **OK** button.  

The debts and liabilities amount for the selected vendor or customer is recalculated and the lines are inserted in the document.  

## Printing the INV-17 form and the Supplement to INV-17 form  
 The following procedure shows how to print the INV-17 form and the Supplement to INV-17 form.  

1.  In the **Inventory Account Card** window, choose the **Release** action.  
3.  Choose the **Act** action, and then choose the **Signatures** action.  
4.  Select the following fields:  

- **Chairman**  
- **Member1**  
- **Member2**  
- **Member3**  
- **Accountant**  

    > [!NOTE]  
    >  All selected signatures will be reflected in the appropriate fields.  

5.  Choose the **Print** action, and then choose the **Invent. Act INV-17** action to print the inventory act.  
6.  Choose the **Print** action, and then choose the **Supplement to Invent. Act INV-17** action to print the supplement to the inventory act.  

## See Also  
 [Russian Payables Reports](russian-payables-reports.md)   
 [Russian Receivables Reports](russian-receivables-reports.md)
