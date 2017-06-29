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
# How to: Export and Post Domiciliations
You can submit domiciliations to your bank by exporting the data to a file. When you export to a file, you can choose to automatically post the lines to the general ledger.  
  
 Depending on setup of the **SEPA Direct Debit Exp. Format** field in the **Bank Account Card** window, the **File Domiciliations** action opens either of these request pages:  
  
-   **Create Gen. Jnl. Lines** window – for the SEPA Direct Debit format.  
  
-   **File Domiciliations** window – for domestic formats.  
  
### To export and post domiciliations in SEPA format  
  
1.  In the **Search** box, enter **Domiciliation Journals**, and then choose the related link.  
  
2.  In the **Batch Name** field, select the required journal batch, and on the **Home** tab, in the **Progress** group, choose **File Domiciliations**.  
  
3.  In the **Create Gen. Jnl. Lines** window, select the **Options** FastTab, and then fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_2000021\_F\_1\_11 Journal Template Name $\)**|Select the general journal template that the domiciliations will be posted from.|  
    |**\($ R\_2000021\_F\_1\_7 Journal Batch $\)**|Select the general journal batch that the journal lines will be transferred from.|  
    |**\($ R\_2000021\_F\_1\_3 Post General Journal Lines $\)**|Select to post to the general ledger.|  
  
4.  Choose the **OK** button to export the file.  
  
5.  Choose an appropriate location from where you upload the file to your bank, and then choose **Save**.  
  
6.  Choose the **Yes** button to automatically post the domiciliation journal lines.  
  
     If you did not select the **\($ R\_2000021\_F\_1\_3 Post General Journal Lines $\)** check box, you will have to post the domiciliations manually in the general journal.  
  
    > [!NOTE]  
    >  After you have posted domiciliations in the general journal, delete the posted domiciliations in the **Domiciliation Journal** window. To do this, select all lines with status **Posted**, choose **Actions**, and then choose the **Delete** button.  
  
### To export and post domiciliations in Isabel format  
  
1.  In the **Search** box, enter **Domiciliation Journals**, and then choose the related link.  
  
2.  In the **Batch Name** field, select the required journal batch, and on the **Home** tab, in the **Progress** group, choose **File Domiciliations**.  
  
3.  In the **File Domiciliations** window, select the **Options** FastTab, and then fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_2000021\_F\_1\_11 Journal Template Name $\)**|Select the general journal template that the domiciliations will be posted from.|  
    |**\($ R\_2000021\_F\_1\_7 Journal Batch $\)**|Select the general journal batch that the journal lines will be transferred from.|  
    |**\($ R\_2000021\_F\_1\_3 Post General Journal Lines $\)**|Select to post to the general ledger.|  
    |**\($ R\_2000021\_F\_1\_5 Pivot Date $\)**|Enter a pivot date if you want a date that differs from the posting date on the domiciliation lines. The date entered will overwrite the posting date on the selected journal lines.|  
    |**\($ R\_2000021\_F\_1\_9 Inscription No. $\)**|Enter the inscription number that is on the intra-community declaration disk. The number is included in the file and on the accompanying note.|  
    |**\($ R\_2000021\_F\_1\_1 File Name $\)**|Enter the name of the export file that you are creating.|  
  
4.  Choose the **Print** button to export the domiciliations and print the accompanying note, or choose the **Preview** button to view it on the screen. If you do not want to export the file now, choose the **Cancel** button.  
  
5.  Choose the **OK** button to send the report to the printer.  
  
6.  Choose the **Yes** button to automatically post the domiciliation journal lines.  
  
     If you did not select the **\($ R\_2000021\_F\_1\_3 Post General Journal Lines $\)** check box, you will have to post the domiciliations manually in the general journal.  
  
    > [!NOTE]  
    >  After you have posted domiciliations in the general journal, delete the posted domiciliations in the **Domiciliation Journal** window. To do this, select all lines with status **Posted**, choose **Actions**, and then choose the **Delete** button.  
  
## See Also  
 SEPA Direct Debit Exp. Format   
 [Direct Debit Using Domiciliation](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/direct-debit-using-domiciliation.md)   
 [How to: Set Up Domiciliations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-domiciliations.md)   
 [How to: Generate Domiciliation Suggestions](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-generate-domiciliation-suggestions.md)   
 [How to: Test Domiciliations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-test-domiciliations.md)   
 [How to: Edit and Delete Domiciliation Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-edit-and-delete-domiciliation-lines.md)