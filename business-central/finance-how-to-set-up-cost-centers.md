---
    title: How to Set Up Cost Centers | Microsoft Docs
    description: Cost centers are departments that are responsible for costs and income. The chart of cost centers is similar to the dimension information for the general ledger.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Set Up Cost Centers
Cost centers are departments that are responsible for costs and income. The chart of cost centers is similar to the dimension information for the general ledger. You can set up the chart of cost centers in the following ways:  

-   Transfer dimension values in the general ledger to the chart of cost centers. You can make any necessary adjustments after the transfer.  
-   Create a new chart of cost center that is independent of the general ledger or add a new cost center to an existing chart of cost center. You must create each cost center individually.  

## To transfer dimension values in the general ledger to the chart of cost centers  
1.  Set up a dimension to be the cost center dimension in the **Update Cost Acctg. Dimensions** window. Only the values from this dimension are transferred.  
2.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Cost Centers**, and then choose the related link.  
3.  On the **Actions** tab, in the **Functions** group, choose **Get Cost Centers from Dimension** to transfer dimension values to the chart of cost centers. The function transfers the dimension values that you defined in step 1.  

    > [!NOTE]  
    >  You can set up the **Align Cost Center Dimension**  field to define a one-way synchronization of dimension values from the general ledger to the chart of cost centers. You cannot define a synchronization of the chart of cost centers to dimension values from the general ledger.  

The chart of cost centers now contains all specified dimension values from the general ledger and includes titles and subtotals.  

## To create new cost centers in the Chart of Cost Centers window  
You can set up and maintain cost centers in either the **Cost Center Card** card or in the **Chart of Cost Centers** window. In this procedure, you set up cost centers in the **Chart of Cost Centers** window.  

1. Open the **Chart of Cost Centers** window in edit mode.  
2. In the **Code** field, enter the cost center code. All cost centers must have a code.  
3. In the **Name** field, enter the cost center name.  
4. Choose the drop-down arrow in the **Line Type** field to specify the purpose of the cost center.  

    - For cost centers of the **Total** type, you must fill in the **Totaling** field. Use the **or** operator, which is a vertical line (**&#124;**) to set ranges of cost centers.  
    - For cost centers of the **End-Total** line type, this field is filled in automatically when you use the indent function.  
5.  Fill in the **Sorting Order** and **Cost Subtype** fields.  
6.  Choose the next empty line to create a new cost center, and then repeat steps 2 through 5.  
7.  After you have set up all the cost centers, choose the **Indent Cost Centers** action. Choose the **Yes** button.  

> [!IMPORTANT]  
>  If you have entered definitions in the **Totaling** fields for **End-Total** cost centers before you run the indent function, then you must enter them again. The function overwrites the values in all **End-Total** fields.  

## See Also  
[Accounting for Costs](finance-manage-cost-accounting.md)  
[Setting Up Cost Accounting](finance-set-up-cost-accounting.md)   
[Terminology in Cost Accounting](finance-terminology-in-cost-accounting.md)   
[About Cost Accounting](finance-about-cost-accounting.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
