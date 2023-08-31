---
author: brentholtorf
ms.topic: include
ms.date: 04/01/2021
ms.author: bholtorf
---

Sales tax includes taxes that companies pay for using items:  

- Use tax (United States) – Use tax is a United States sales tax that is paid on items that are purchased by a company and are used by that company instead of being sold to a customer. The company must pay sales tax for those items to the government, in the form of use tax.  
- Purchase tax (Canada) – Purchase tax is a Canadian sales tax that is paid by a company on items that are purchased from a vendor. When a company purchases items for use by the company itself, the vendor charges the appropriate sales tax for the items.  

## To set up use tax for a purchase order  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
2.  On the **Purchase Orders** page, choose the **New** action.  
3.  On the **Lines** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../../includes/tooltip-inline-tip_md.md)]  
4.  On the **Invoicing** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Tax Liable**|Select to set up tax liability. **Important:**  This field is available on the **Purchase Header** page, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
    |**Tax Area Code**|The tax area code of the vendor. **Important:**  This field is available on the **Purchase Header** page, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
    |**Tax Exemption No.**|The company's tax exemption number. You can enter a maximum of 30 alphanumeric characters. **Important:**  This field is available on the **Purchase Header** page, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
    |**Provincial Tax Area Code**|The tax code for the province. **Important:**  This field is available on the **Purchase Header** page, but it is not shown by default. To select the field, you must first add the column that shows this field. [!INCLUDE[bp_customize](../../../includes/bp_customize_md.md)]|  
5.  Choose the **OK** button.  

## To set up use tax details  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tax Details**, and then choose the related link.  
2.  On the **Tax Details** page, choose the **New** action.  
3.  On the **New - Tax Details** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Tax Jurisdiction Code**|The tax jurisdiction code for the tax detail entry.|  
    |**Tax Group Code**|The tax group code for the tax detail entry.|  
    |**Tax Type**|**Sales and Use Tax** – To apply both sales tax and use tax to the tax detail entry.<br /><br /> –or–<br /><br /> **Excise Tax** – To apply excise tax to the tax detail entry.<br /><br /> –or–<br /><br /> **Sales Tax Only** – To apply only sales tax to the tax detail entry.<br /><br /> –or–<br /><br /> **Use Tax Only** – To apply only use tax to the tax detail entry.|  
4.  Choose the **OK** button.  

## To set up purchase tax for a company  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
2.  On the **Company Information** page, on the **Tax** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Tax Area Code**|The company's tax area code. The tax area code is used in conjunction with a tax group code field and the **Tax Liable** field to find the necessary information for calculating sales tax.|  
    |**Tax Exemption No.**|The company's tax exemption number. You can enter a maximum of 30 alphanumeric characters.|  
    |**Provincial Tax Area Code**|The tax code for the province.|  
3.  Choose the **OK** button.  

## To set up purchase tax for a location  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
2.  On the **Locations** page, select the required location, and then choose the **Edit** action.  
3.  On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Do Not Use For Tax Calculation**|Select to specify whether the tax information included on this location record is to be used for sales tax calculations on purchase documents.|  
    |**Tax Area Code**|The tax area code for the location. The tax area code is used in conjunction with a tax group code field and the **Tax Liable** field to find the necessary information for calculating sales tax.|  
    |**Tax Exemption No.**|The company's tax exemption number. You can enter a maximum of 30 alphanumeric characters.|  
    |**Provincial Tax Area Code**|The tax code for the province.|  
4.  Choose the **OK** button.  

## To set up purchase tax for non-recoverable tax  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tax Details**, and then choose the related link.  
2.  On the **Tax Details** page, choose the **New** action.  
3.  Select the **Expense/Capitalize** check box.  

    > [!NOTE]  
    >  This check box must be selected if the tax paid is not recoverable.  
4.  Choose the **OK** button.  
