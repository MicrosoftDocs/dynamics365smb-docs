---
    title: How to Set Up Interest on Arrears
    description: For each finance charge term, you can specify how interest on arrears must be calculated. You can set up finance charge calculations with different interest rates for different periods.

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
# How to: Set Up Interest on Arrears
For each finance charge term, you can specify how interest on arrears must be calculated. You can set up finance charge calculations with different interest rates for different periods.  

When you apply a finance charge term with interest on arrears to a customer or vendor, interest on arrears will be calculated. Then, you can run the Calculate Interest on Arrears report to view details about interest on arrears for customers or vendors.  

After you run the report, if a customer owes interest on arrears, the information about the amount of interest on arrears to pay is added to the customer statement.  

## To set up interest on arrears  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Finance Charge Terms**, and then choose the related link.  
2.  In the **Finance Charge Terms** window, select the required finance charge term entry, and then choose the **Int. on Arrears** action.  
3.  In the **Interest on Arrears** window, choose the **New** action.  
4.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Specify the date from which you want to calculate interest on arrears. **Important:**  The start date for the first interest transaction cannot be later than the earliest posting date for the finance transactions.|  
    |**Interest Rate**|Specify the rate of interest to be calculated for the arrears.|  
    |**Description**|Specify the description for the interest on arrears.|  

5.  Choose the **OK** button.  

The following procedure describes how to apply interest on arrears to a customer, but the same steps also apply for interest on arrears to a vendor.  

## To apply interest on arrears to a customer  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
2.  Select the customer to whom interest on arrears must be applied, and then choose the **Edit** action.  
3.  On the **Payments** FastTab, in the **Int. on Arrears Code** field, select the appropriate finance charge term that includes interest on arrears.  
4.  Choose the **OK** button.  

## See Also  
 [Interest on Arrears Overview](interest-on-arrears-overview.md)   
