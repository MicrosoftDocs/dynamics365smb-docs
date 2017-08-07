---
    title: How to: Link from Records to External Information or Programs | Microsoft Docs
    description: You may want to attach a hyperlink to a document or website to a specific record, such as a customer or document in ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> to the corresponding invoice on Microsoft SharePoint Server. Or, you can make a link from an item card to the corresponding page in your vendor's online catalog.
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
# How to: Link from Records to External Information or Programs
You may want to attach a hyperlink to a document or website to a specific record, such as a customer or document in ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> to the corresponding invoice on Microsoft SharePoint Server. Or, you can make a link from an item card to the corresponding page in your vendor's online catalog.  
  
 The following procedures describe how to add links to records, how to view links, and how to delete links.  
  
### To link to a document or website outside ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->  
  
1.  Open the record that you want to attach the link to, such as a customer card or sales order. If you want to attach the link to a specific line, such as a journal line, select the line.  
  
2.  If the **Links** FactBox is not displayed on the page, customize the page to display Links. For more information, see [How to: Customize FactBoxes](../FullExperience/how-to-customize-factboxes.md).  
  
3.  In **Links**, choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), and then choose **New**.  
  
4.  In the **Link Address** field, enter an address for the file or website, such as **C:My Documentsinvoice1.doc** or **www.microsoft.com**.  
  
5.  Fill in the **Description** field with information about the link.  
  
6.  Choose the **Save** button.  
  
### To open a program outside ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->  
  
1.  Open the record that you want to attach the link to, such as a customer card or sales order. If you want to attach the link to a specific line, such as a journal line, select the line.  
  
2.  If the **Links** FactBox is not displayed on the page, customize the page to display Links. For more information, see [How to: Customize FactBoxes](../FullExperience/how-to-customize-factboxes.md)  
  
3.  In **Links**, choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), and then choose **New**.  
  
4.  In the **Link Address** field, enter a specific string to open different programs, for example:  
  
    -   To open OneNote with a specific page, enter **onenote:///C:My Documentstest.one**.  
  
    -   To open Outlook with a new empty email to a specific alias, enter **mailto:testalias**.  
  
5.  Fill in the **Description** field with information about the link.  
  
6.  Choose the **Save** button.  
  
### To view a link  
  
1.  Open the relevant record, such as the sales order. If the link is attached to a specific line, select the line.  
  
2.  In **Links**, choose the link in the **Link Address** field. The appropriate program, such as Microsoft Word or Microsoft Internet Explorer, opens and displays the link target.  
  
### To delete a link from a record  
  
1.  Open the record that contains the link that you want to delete. If the link is attached to a specific line, select the line.  
  
2.  In **Links**, select the link that you want to delete.  
  
3.  Choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), and then choose **Delete**.  
  
4.  Choose the **Yes** button to confirm the deletion.  
  
> [!NOTE]  
>  You can only delete a link if the IT administrator has assigned the necessary user permissions to you.  
>   
>  If a user deletes a single record, such as a sales order line, a sales order, or a customer card, then all the links attached to the record are deleted. However, if you delete records using a batch job, such as the **Delete Invoiced Sales Orders** batch job, then the links are still stored in the **Record Links** table. To delete the links from the database, run the **Delete Orphaned Record Links** codeunit.  
  
### To run delete orphaned record links  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Data Deletion**, and then choose the related link.  
  
2.  On the **Data Deletion** page, choose **Tasks**, and then choose **Delete Orphaned Record Links**.  
  
## See Also  
 [Working with Product Name](../FullExperience/working-with-$-p_1-product-name-$-.md)