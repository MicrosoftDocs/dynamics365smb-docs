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
# How to: Set Up Cost Objects
Cost objects are projects, products, or services of a company. The chart of cost objects is similar to the dimension information for the general ledger. You can set up the chart of cost objects in the following ways:  

-   Transfer dimension values in the general ledger to the chart of cost objects. You can make any necessary adjustments after the transfer.  

-   Create a new chart of cost object that is independent of the general ledger or add a new cost object to an existing chart of cost objects. You must create each cost object individually.  

### To transfer dimension values from the general ledger to the chart of cost objects  

1.  Set a dimension to be the cost object dimension in the **Update CA Dimensions** window. Only the values from this dimension are transferred.  

2.  In the **Search** box, enter **Chart of Cost Objects**, and then choose the related link.  

3.  On the **Actions** tab, in the **Functions** group, choose **Get Cost Objects from Dimension** to transfer dimension values to the chart of cost objects. The function transfers the dimension values that you defined in step 1.  

    > [!NOTE]  
    >  You can set up the **Align Cost Object Dimension**  field to define a one-way synchronization of dimension values from the general ledger to the chart of cost objects. You cannot define a synchronization of the chart of cost objects to dimension values from the general ledger.  

 The chart of cost objects now contains all specified dimension values from the general ledger and includes titles and subtotals.  

### To create new cost objects in the Chart of Cost Objects window  

1.  > [!NOTE]  
    >  You can set up and maintain cost objects in either the **Cost Object Card** card or in the **Chart of Cost Objects** window. In this procedure, you set up cost objects in the **Chart of Cost Objects** window.  

2.  Open the **Chart of Cost Objects** window in edit mode.  

3.  In the **Code** field, enter the cost object code. All cost objects must have a code.  

4.  In the **Name** field, enter the cost object name.  

5.  Choose the drop-down arrow in the **Line Type** field to specify the purpose of the cost object.  

    -   For cost objects of the **Total** line type, fill in the **Total From/To** field. Use the **or** operator, which is a vertical line (**&#124;**), to set ranges of cost objects.  

    -   For cost objects of the **End-Total** line type, this field is filled in automatically when you use  the indent function.  

6.  Fill in the **Sorting Order** field.  

7.  Chose the next empty line to create a new cost object, and then repeat steps 2 through 5.  

8.  After you have set up all the cost objects, on the **Home** tab, in the **Process** group, choose **Indent Cost Objects**. Choose the **Yes** button.  

> [!IMPORTANT]  
>  If you have entered definitions in the **Total From/To** fields for **End-Total** cost objects before you run the indent function, then you must enter them again. The function overwrites the values in all **End-Total** fields.  

## See Also  
 Chart of Cost Objects   
 Cost Object Card   
 [Defining Cost Centers and Cost Objects for Chart of Accounts](defining-cost-centers-and-cost-objects-for-chart-of-accounts.md)   
 [Balances Between Cost Type, Cost Center, and Cost Object](balances-between-cost-type-cost-center-and-cost-object.md)   
 [Set Up Cost Accounting](set-up-cost-accounting.md)   
 [Terminology in Cost Accounting](terminology-in-cost-accounting.md)   
 [About Cost Accounting](about-cost-accounting.md)
