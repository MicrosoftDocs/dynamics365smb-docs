---
    title: Find Any Entry with Navigate | Microsoft Docs
    description: Shows the number and type of entries that have the same document number or posting date. You can also use this feature to find the documents and entries where certain lot numbers and serial numbers are used. This feature is useful if you want to find the ledger entries that resulted from certain transactions. When you search by document number, you can print the summary from the **Document Entries** report.
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
# Find Any Entry with Navigate
Shows the number and type of entries that have the same document number or posting date. You can also use this feature to find the documents and entries where certain lot numbers and serial numbers are used. This feature is useful if you want to find the ledger entries that resulted from certain transactions. When you search by document number, you can print the summary from the **Document Entries** report.  
  
## Working with Navigate  
 You can open the **Navigate** window in two ways:  
  
-   By opening an empty **Navigate** window. On the **Home** tab, in the **Find by** group, you can choose the type of data that you want to navigate from. You can navigate from a document, a business contact, or the lot number or serial number for an item.  
  
-   From all windows that display posted entries and in posted sales invoices, purchase invoices, credit memos, sales receipts, and purchase shipments. In this case, the **Navigate** window will show the document number and posting date of the entries that you selected. The **Navigate** window also lists the documents that have the same document number and posting date as the entries that you selected.  
  
 The **Navigate** window has a different first FastTab, depending on your selection in the **Find by** group. You must enter information about the documents or item tracking numbers that you want to search for before information is filled in from the records located.  
  
 After you have entered the relevant search information, on the **Actions** tab, choose **Find** to start the search. If you change any of the filters, you must choose **Find** again.  
  
 The **Navigate** window shows the following information for the located documents.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
|---------------------------------|---------------------------------------|  
|**Document Type, Source Type, Source No., and Source Name**|These fields contain information about the source document that was found by searching for the document number. If the search finds more than one document number, these fields will be empty.|  
|**Table Name**|This column shows a list of the ledger entry tables that contain the ledger entries located by the search.|  
|**No. of Records**|This column shows the number of records found in each of the ledger entry tables that are listed.|  
  
 After the Navigate feature has located the ledger entries, they are listed in the **Related Entries** column. You can quickly see the individual entries in each table by choosing the relevant line and then choosing the **Show Details** command.  
  
 The following sections describe the filters you can specify.  
  
### Find by Document  
 On the **Document** FastTab, enter the document numbers and posting dates as described in the following table.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
|---------------------------------|---------------------------------------|  
|**Document No.**|Enter the document numbers on which you require additional information. You can insert a filter if you want ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> to search for a certain interval of document numbers.|  
|**Posting Date**|Enter the posting date on which the document you are searching for was posted. You can insert a date filter if the documents that you are searching for were posted in a certain time interval.|  
  
### Find by Business Contact  
 On the **Business Contact** FastTab, you can enter document information that was assigned by a vendor or a customer. You can use the options on this tab to search for vendor documents by using the numbers that the vendor has assigned the documents. For example, the following table shows how you can use this feature to find an invoice when you only have the invoice number assigned by the vendor.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
|---------------------------------|---------------------------------------|  
|**Business Contact Type**|Select one of the options: <Blank>, **Vendor**, or **Customer**. <Blank> is the default value. Select **Vendor** or **Customer** when you want to search for vendor or customer documents.|  
|**Business Contact No.**|Select the number of the vendor or customer who assigned a number to the invoice that you are searching for.|  
|**Document No.**|Enter the document number assigned by the vendor.<br /><br /> ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> will show all ledger entries that contain this document number.|  
  
### Find by Item Reference  
 On the **Item Reference** FastTab, you can enter the lot number or serial number, or you can filter on the lot number or serial number that you want to search for. This option is useful if you want to see where a specific item tracking number was used, what vendor it came from, or what customer it was sold to.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
|---------------------------------|---------------------------------------|  
|**Serial No.**|Enter the serial numbers on which you require additional information. You can insert a filter if you want to search for a certain set of serial numbers.|  
|**Lot No.**|Enter the lot numbers on which you require additional information. You can insert a filter if you want to search for a certain set of lot numbers.|  
  
## See Also  
 [Enter Criteria in Filters](../FullExperience/enter-criteria-in-filters.md)   
 SEARCH Search   
 Navigate   
 Document Entries   
 [Working with Product Name](../FullExperience/working-with-$-p_1-product-name-$-.md)