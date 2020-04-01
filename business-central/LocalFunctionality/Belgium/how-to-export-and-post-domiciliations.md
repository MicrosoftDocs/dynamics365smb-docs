---
    title: How to Export and Post Domiciliations
    description: You can submit domiciliations to your bank by exporting the data to a file. When you export to a file, you can choose to automatically post the lines to the general ledger.

    services: project-madeira 
    documentationcenter: ''
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
# Export and Post Domiciliations
You can submit domiciliations to your bank by exporting the data to a file. When you export to a file, you can choose to automatically post the lines to the general ledger.  

Depending on setup of the **SEPA Direct Debit Exp. Format** field on the **Bank Account Card** page, the **File Domiciliations** action opens either of these request pages:  

- **Create Gen. Jnl. Lines** page – for the SEPA Direct Debit format.  
- **File Domiciliations** page – for domestic formats.  

## To export and post domiciliations in SEPA format  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Domiciliation Journals**, and then choose the related link.  
2.  In the **Batch Name** field, select the required journal batch, and then choose the **File Domiciliations** action.  
3.  On the **Create Gen. Jnl. Lines** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Journal Template Name**|Select the general journal template that the domiciliations will be posted from.|  
    |**Journal Batch**|Select the general journal batch that the journal lines will be transferred from.|  
    |**Post General Journal Lines**|Select to post to the general ledger.|  

4.  Choose the **OK** button to export the file.  
5.  Choose an appropriate location from where you upload the file to your bank, and then choose **Save**.  
6.  Choose the **Yes** button to automatically post the domiciliation journal lines.  

    If you did not select the **Post General Journal Lines** check box, you will have to post the domiciliations manually in the general journal.  

    > [!NOTE]  
    >  After you have posted domiciliations in the general journal, delete the posted domiciliations on the **Domiciliation Journal** page. To do this, select all lines with status **Posted**, and then choose the **Delete** button.  

## To export and post domiciliations in Isabel format  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Domiciliation Journals**, and then choose the related link.  
2.  In the **Batch Name** field, select the required journal batch, and then choose the **File Domiciliations** action.  
3.  On the **File Domiciliations** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Journal Template Name**|Select the general journal template that the domiciliations will be posted from.|  
    |**Journal Batch**|Select the general journal batch that the journal lines will be transferred from.|  
    |**Post General Journal Lines**|Select to post to the general ledger.|  
    |**Pivot Date**|Enter a pivot date if you want a date that differs from the posting date on the domiciliation lines. The date entered will overwrite the posting date on the selected journal lines.|  
    |**Inscription No.**|Enter the inscription number that is on the intra-community declaration disk. The number is included in the file and on the accompanying note.|  
    |**File Name**|Enter the name of the export file that you are creating.|  

4.  Choose the **Print** button to export the domiciliations and print the accompanying note, or choose the **Preview** button to view it on the screen. If you do not want to export the file now, choose the **Cancel** button.  
5.  Choose the **OK** button to send the report to the printer.  
6.  Choose the **Yes** button to automatically post the domiciliation journal lines.  

    If you did not select the **Post General Journal Lines** check box, you will have to post the domiciliations manually in the general journal.  

    > [!NOTE]  
    >  After you have posted domiciliations in the general journal, delete the posted domiciliations on the **Domiciliation Journal** page. To do this, select all lines with status **Posted**, and then choose the **Delete** button.  

## See Also  
 [Direct Debit Using Domiciliation](direct-debit-using-domiciliation.md)   
 [Set Up Domiciliations](how-to-set-up-domiciliations.md)   
 [Generate Domiciliation Suggestions](how-to-generate-domiciliation-suggestions.md)   
 [Test Domiciliations](how-to-test-domiciliations.md)   
 [Edit and Delete Domiciliation Lines](how-to-edit-and-delete-domiciliation-lines.md)
