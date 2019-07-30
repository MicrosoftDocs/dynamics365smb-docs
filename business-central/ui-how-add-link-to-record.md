---
    title: Add Attachments, Links, and Notes on Records| Microsoft Docs
    description: Attach a hyperlink to a document or website to a specific record, such as a customer or document.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/30/2019
    ms.author: sgroespe
---
# Manage Attachments, Links, and Notes on Cards and Documents

> [!NOTE]
> [!INCLUDE[vnext_preview](includes/vnext_preview.md)]

In the FactBox on most cards and documents, you can attach files, add links, and write notes. For links and notes, you can also do this on the list page by first selecting the related line.

To view or change any of these attached information types, you must first open the **Attachments** tab in the FactBox. The number behind the tab title indicates how many attached files, links, or notes exist for the card or document.

## To attach a file to a sales order
You can attach any type of file, image, video, or text, to a card or document. The file stays attached as the card or document is processed into other states, such as from an ongoing sales order to a posted sales invoice. Note, however, that attachments are not output from the system, for example, when printing and saving to file.

> [!NOTE]
> In general, the maximum file size for attachments is 150 MB. However, the limit can be lower for some features.

The following procedure is based on a sales order. The steps are similar for all other supported documents and cards.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Open the sales order that you want to attach a file to.
3. In the FactBox, open the **Attachments** tab.
4. Choose the value behind the **Documents** field, such as "0".
5. On the **Attached Documents** page, in the **Attachment** field, choose the **Select File** button.
5. Select a file from any location, and then choose the **Open** button.

## To add a link on a record   
Another example could be when you receive printed invoices from vendors. You can scan them and store them as .pdf files on a SharePoint site. Then you can make a link from a purchase invoice in [!INCLUDE[d365fin_md](includes/d365fin_md.md)] to the corresponding invoice on  SharePoint. Or, you can make a link from an item card to the corresponding page in your vendor's online catalog.
1.  Open the record that you want to attach the link to, such as a customer card or sales order. If you want to attach the link to a specific line, such as a journal line, select the line.  

2.  Choose the **Links** action to open the **Links** pages that shows all the current links that are added to the record.

3. To add a new link, choose **+new**.

4.  In the **Link Address** field, enter

    -   To link to a file on your computer or network, enter the full path and file name, such as  **C:\My Documents\invoice1.doc**.
    -   To link to website, enter the Internet address (URL), such as **www.microsoft.com**.
    -   To link to a program, enter a specific string to open the program. For example, to open OneNote with a specific page, enter **onenote:///C:\My Documents/test.one**. Or, to open Outlook with a new empty email to a specific alias, enter **mailto:testalias**.  

5.  Fill in the **Description** field with information about the link.  

6.  Choose the **Save** button.  

## To delete a link from a record  

To delete a link, on the **Links** page, you can select **...** and then **Delete**.

If you delete a single record, such as a sales order line, a sales order, or a customer, then all the links attached to the record are deleted. However, if you delete records using a batch job, such as the **Delete Invoiced Sales Orders** batch job, then the links are still stored in the database. To delete the links from the database, run the **Delete Orphaned Record Links** codeunit. To do this, choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Orphaned Record Links**, and then choose the related link.   

<!-- ### To run delete orphaned record links  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Deletion**, and then choose the related link.  

2.  On the **Data Deletion** page, choose **Tasks**, and then choose **Delete Orphaned Record Links**.  -->

## See Also  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
