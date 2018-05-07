---
    title: Use Automated Data Capture Systems (ADCS) | Microsoft Docs
    description: You can use your automatic data capture system (ADCS) to register the movement of items in the warehouse and to register some journal activities, such as quantity adjustments in the warehouse item journal and physical inventories.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 09/18/2017
    ms.author: sgroespe

---
# Enable Automated Data Capture Systems (ADCS)
You can use your automatic data capture system (ADCS) to register the movement of items in the warehouse and to register some journal activities, such as quantity adjustments in the warehouse item journal and physical inventories.  

To use ADCS, you must give each item stored in the warehouse an item identifier. You must also set up miniforms, handheld functions, data exchanges, and specify settings for fields that control ADCS. You specify whether to use ADCS on the location card of a warehouse.

Based on the needs of your warehouse, you define the amount of information displayed in the miniform setup for the particular handheld device. The following are examples of information that you can display:  

- Data from tables within [!INCLUDE[d365fin](includes/d365fin_md.md)], such as a list of pick documents from which the user can select.  
- Text information.  
- Messages to show confirmations or errors about activities performed and registered by the handheld device user.

For more information, see [Configuring an Automated Data Capture System](/dynamics-nav/Configuring-Automated-Data-Capture-System) in the developer and IT-pro help.

## To set up a warehouse to use ADCS  
To use ADCS, you must specify which warehouse locations use the technology.  

> [!NOTE]  
>  We recommend that you do not set up a warehouse to use ADCS if the warehouse also has a bin capacity policy.

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Locations**, and choose the related link.
2.  Select a warehouse from the list for which you want to enable ADCS, and then choose the **Edit** action.
3. In the **Location Card** window, select the **Use ADCS** check box.  

## To specify an item to use ADCS  
Each warehouse item that you want to use with ADCS must be assigned an identifier code to link it with its item number. For example, you can use the item's bar code as the identifier code. An item can also have multiple identifier codes. You may find this useful in the case where an item is available in various units of measures, such as pieces and pallets. In this case, assign an identifier code to each.    

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
2.  Select an item from the list that is part of your ADCS solution, and then choose the **Edit** action.
3. In the **Item Card** window, choose the **Identifiers** action.
4. In the **Item Identifiers** window, choose the **New** action.
5. In the **Code** field, specify the identifier for the item. For example, the identifier could be the item's bar code number.  

    You can also enter a **Variant Code** and a **Unit of Measure** code.  

6. If needed, enter multiple codes for each item.
7. Choose the **OK** button.  
8.  To review the information, choose the **Identifier Code** field to open the **Item Identifiers** window.

## To add an ADCS user  
You can add any user as a user of an Automated Data Capture System (ADCS). When you do this, the user must also provide a password. Optionally, you can also provide a connection that identifies the ADCS user as a warehouse employee. The ADCS user password can be different from the Windows logon password of the user. For more information, see [Manage Users and Permissions](ui-how-users-permissions.md).

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **ADCS Users**, and then choose the related link.  
2. Choose the **New** action.  
3.  In the **Name** field, enter a name for the user. The name cannot contain more than 20 characters, including spaces.  
4.  In the **Password** field, enter a password. The password is masked.  

### To specify that a warehouse employee is an ADCS user  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Warehouse Employees**, and then choose the related link.  
2.  If needed, add a new warehouse employee. For more information, see [Set Up Warehouse Employees](warehouse-how-to-set-up-warehouse-employees.md).  
3.  Choose the **Edit List** action.  
4.  Select a warehouse employee from the list. In the **ADCS User** field, choose the drop-down arrow, and then select the name of an ADCS user from the list.  

> [!NOTE]  
>  The default warehouse for the employee must be one that uses ADCS.

## To create and customize miniforms
You use miniforms to describe the information that you want to present on a handheld device. For example, you can create miniforms to support the warehouse activity of picking items. After you create a miniform, you can add functions to it for the common actions that a user takes with handheld devices, such as moving up or down a line.  

To implement or change the functionality of a miniform function, you must create a new codeunit or modify an existing one to perform the required action or response. You can learn more about ADCS functionality by examining codeunits such as 7705, which is the handling codeunit for logon functionality. Codeunit 7705 shows how a Card-type miniform works.  

### To create a miniform for ADCS  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Miniforms**, and then choose the related link.  
2. Choose the **New** action.  
3.  In the **Code** field, enter a code for the miniform. Optionally, enter values in all other fields.  

    Select the **Start Miniform** check box to indicate that the miniform is the first form that the user sees at logon.  

4.  On the **Lines** FastTab, define the fields that appear on the miniform. The order in which you enter lines is the order in which the lines appear on the handheld device.  

When you have created a miniform, the next steps are to create functions and to associate functionality for various keyboard inputs.  

### To add support for a function key  
1.  Add code similar to the following example to the.xsl file for the plug-in. This creates a function for the **F6** key. The key sequence information can be obtained from the device manufacturer.  
    ```xml  
    <xsl:template match="Function[.='F6']">  
      <Function Key1="27" Key2="91" Key3="49" Key4="55" Key5="126" Key6="0"><xsl:value-of select="."/></Function>  
    </xsl:template>  

    ```  
2.  In the [!INCLUDE[d365fin](includes/d365fin_md.md)] development environment, open table 7702 and add a code representing the new key. In this example, create a key that is named **F6**.  
3.  Add C/AL code to the relevant function of the miniform-specific codeunit to handle the function key.  

### To customize miniform functions  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Miniforms**, and then choose the related link.  
2.  Select a miniform from the list, and then choose the **Edit** action.  
3.  Choose the **Functions** action.  
4.  In the **Function Code** drop-down list, select a code to represent the function that you want to associate with the miniform. For example, you can select ESC, which associates functionality with the press of the ESC key.  

In the [!INCLUDE[d365fin](includes/d365fin_md.md)] development environment, edit the code for the **Handling Codeunit** field to create or modify code to perform the required action or response.

For more information, see [Configuring an Automated Data Capture System](/dynamics-nav/Configuring-Automated-Data-Capture-System) in the developer and IT-pro help.

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
