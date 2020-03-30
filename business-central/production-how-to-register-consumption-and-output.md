---
    title: Register Consumption and Output for One Production Order | Microsoft Docs
    description: This execution task is performed on the **Production Journal** page. The journal combines the functions of the separate consumption journal and output journals into one journal. The combined journal is accessed directly from a released production order. Its main purpose is to manually post the consumption of components, the quantity of end items produced, and the time spent in operations.
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
# Register Consumption and Output for One Released Production order line
This execution task is performed on the **Production Journal** page. The journal combines the functions of the separate consumption journal and output journals into one journal. The combined journal is accessed directly from a released production order. Its main purpose is to manually post the consumption of components, the quantity of end items produced, and the time spent in operations. The values are posted to ledger entries under the released production order. Consumption quantities are posted as negative item ledger entries, output quantities are posted as positive ledger entries, and times spent are posted as capacity ledger entries. Such posted values can also be viewed at the bottom of the journal as actual quantities.  

> [!NOTE]  
>  Because consumption data is processed together with output data, this journal offers an opportunity to display linked components and operations in a logical process structure. Components are indented under their respective operation. This requires that you use routing link codes.  

> [!NOTE]  
>  Components without routing link codes are listed first in the journal.  

## To register consumption and output  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon enter **Released Prod. Orders**, and then choose the related link.  
2.  Open a released production order line that is ready for registration, and then on the **Lines** FastTab, choose the **Line** action, and then choose the **Production Journal** action.  

    The **Production Journal** page opens showing journal lines for the production order line according to the **Prod. Order Component** and **Prod. Order Routing** pages. These lines originate from the production BOM and routing assigned to the item that is being produced. For more information, see [Create Production BOMs](production-how-to-create-routings.md).  

3.  In the **Posting Date** field at the top of the journal, enter a posting date that applies to all lines. The work date is entered by default. The field is meant as a quick way to align posting dates on all lines, if relevant.  

    > [!NOTE]  
    >  Posting dates entered on individual lines will override this field.  

4.  In the **Flushing Method Filter** field at the top of the journal, you can choose to also view consumption and output that is posted automatically according to the flushing methods defined for the item and resource respectively.  

    On each type of line in the journal, only the relevant fields are shown. The rest are blank and write-protected.  

    When the journal is opened, it is preset with the quantities to be posted. If nothing is posted so far, all quantity fields will show by default the expected quantities carried from the production order. If partial postings have been made, the quantity fields on the lines will show the remaining quantities. The quantities and times already posted for the order are displayed at the bottom of the journal as actual entries.  

    Concerning the quantities in the **Output Quantity** field, you have the option to set up which values to preset when the journal is first opened. This is done from the **Manufacturing Setup** page, **General** FastTab, in the **Preset Output Quantity** field.

5.  Proceed to enter the relevant consumption and output quantities in the editable fields.  

    > [!NOTE]  
    >  Only the output quantity on the last journal line of entry type **Output** will adjust the inventory level when posting the journal. Therefore, do not to post the journal, with the expected output quantity preset on the last output line, until all end items are actually produced.  

6.  Select the **Finished** field of output lines to indicate that the operation is finished. This field is related to the **Routing Status** field on a production order routing line.  
7.  Choose the **Post** action to register the quantities you have entered and then close the journal.  

If values remain to be posted, the journal will contain these remaining values next time it is opened. Posted values are shown as actual values in the bottom of the journal.  

> [!NOTE]  
>  If an item that is being consumed is blocked, the journal will not post consumption quantities for that item. If a machine or work center is blocked, the journal will not post output quantities or process times for the output line in question.  

> [!NOTE]  
>  If you close the journal without posting, the changes will be lost.  

> [!WARNING]  
>  The **Production Journal** page cannot be used by two users simultaneously. This means that if User 2 opens the page and enters data when User 1 is already working on the page, then User 2 may lose data when User 1 closes the page.  

## See Also  
[Manufacturing](production-manage-manufacturing.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
