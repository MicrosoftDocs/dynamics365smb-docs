---
    title: How to: Enter Data | Microsoft Docs
    description: In ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->, there are many general functions that help you enter data  in a quick and easy way. The general functions for entering data are described in this topic.
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
# How to: Enter Data
In ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->, there are many general functions that help you enter data  in a quick and easy way. The general functions for entering data are described in this topic.  
  
 The examples in this topic use the ADD INCLUDE<!--[!INCLUDE[demolong](../../includes/demolong_md.md)]-->.  
  
## Find Data As You Type  
 When you start to type characters in a field, a drop-down list is displayed and shows possible field values. The list changes as you type more characters, and you can select the correct value when it is displayed.  
  
 Many fields in ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> have a Down Arrow button that you can choose. You choose the arrow to get a list of data that is available to enter in the field. The button has two functions depending on the type of field:  
  
-   Lookup - Displays information from another table that you can enter in the field. You can select one piece of data at a time.  
  
-   Drop-down - Displays the set of options that exist for the field. You can select only one of the options.  
  
#### To enter a sell-to customer by typing two characters  
  
1.  Open a new empty **Sales Order** window.  
  
2.  Choose the **Sell-to Customer No.** field on the **General** FastTab.  
  
3.  Enter **01** in the field. A drop-down list displays the sell-to customer numbers that begin with the numbers 01. The first column is the first filter column by default.  
  
4.  Select **01121212** from the drop-down list. The field is populated with this sell-to customer number.  
  
#### To search in the name column and make it your default filter column  
  
1.  While the drop-down list is open for sell-to customer numbers, press the Down Arrow key to move control into the drop-down, then press the Right Arrow key to move to the **Name** column.  
  
2.  Type **S**, and then select **Spotsmeyer's Furniture** from the drop-down list.  
  
3.  If you prefer to find sell-to customers by customer name, select **Set as default filter column** in the lower-right corner. Next time that you type something in that field, the **Customer Name** field will be used for filtering, even if you leave the field without opening the drop-down list.  
  
## Copy Fields or Lines  
 Depending on the type of writable document, you can copy individual line fields or whole lines to other lines in the document. Read-only data, such as posted entries, cannot be copied inside ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->.  
  
 Several database dependencies are used to determine if fields or lines can be copied. One way to determine these dependencies is to view the shortcut menu. The content of the shortcut menu indicates which copy functions are supported by displaying either of these functions:  
  
-   Copy Cell  
  
-   Copy Rows  
  
-   Paste Rows  
  
 For example, database records, such as lines on a sales order, and master data, such as cards in the **Items** window, cannot be duplicated. For this kind of data, the shortcut menu typically has the **Copy Cell** or **Copy Rows**  functions. If the **Paste** function is not available this indicates that you can only paste the data into external documents. Single fields on a sales line, however, can be copied to the same column in other sales lines.  
  
 Journal lines are very flexible and can be copied freely in the same journal, indicated by the presence of **Paste** on the shortcut menu.  
  
#### To copy previous field  
  
-   To enter the value of the field immediately above the active field, select **Copy Previous** from the shortcut menu.  
  
## Enter Quantities by Calculation  
 When entering numbers into quantity fields, such as the **Quantity** field on an item journal line, you can enter the formula instead of the sum quantity.  
  
#### Examples  
  
-   If you enter 19+19, the field is calculated to 38.  
  
-   If you enter 41-9, the field is calculated to 32.  
  
-   If you enter 12*4, the field is calculated to 48.  
  
-   If you enter 12/4, the field is calculated to 3.  
  
## See Also  
 [How to: Set Filters](../FullExperience/how-to-set-filters.md)   
 [Sorting](../FullExperience/sorting.md)   
 [How to: Enter Dates and Times](../FullExperience/how-to-enter-dates-and-times.md)   
 [Keyboard Shortcuts](../FullExperience/keyboard-shortcuts.md)