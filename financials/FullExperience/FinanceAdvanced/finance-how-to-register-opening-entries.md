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
# How to: Register Opening Entries
If you are using the fixed assets in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] for the first time, you must set up the general ledger application area before you set up fixed assets. How you do this depends on whether fixed assets is integrated with general ledger.  
  
 The following procedure is used if fixed asset transactions are to be posted to the general ledger.  
  
### To register opening entries  
  
1.  Make sure that you have completed the basic setup procedures for fixed assets.  
  
2.  Create a fixed asset card for each existing asset.  
  
3.  Set up fixed asset depreciation books.  
  
4.  Enable general ledger integration. In the **Search** box, enter **Depreciation Books**, and then choose the related link.  
  
5.  Select the relevant depreciation book. On the **Home** tab, in the **Manage** group, choose **Edit** to open the **Depreciation Book Card** window.  
  
6.  On the **Integration** FastTab, make sure all fields are blank by clearing all check marks. If you have more than one depreciation book, turn on general ledger integration for each one  
  
7.  In the FA journal, enter the following lines for each asset:  
  
    -   A line with the acquisition cost.  
  
    -   A line with the accumulated depreciation to the end of the previous fiscal year.  
  
    -   A line with the accumulated depreciation from the start of the current fiscal year to the date that [!INCLUDE[d365fin](../../includes/d365fin_md.md)] is set to start calculating the depreciation.  
  
     If you have other opening balances you can also enter them now, such as write-down and appreciation.  
  
8.  After you have entered and posted the journal lines for each asset, turn on general ledger integration.  
  
 If the fixed assets are not integrated with the general ledger, skip steps 4 and 8.  
  
## See Also  
 [How to: Create Fixed Assets](../how-to-create-fixed-assets.md)   
 [How to: Set Up General Default Values for Fixed Assets](../how-to-set-up-general-default-values-for-fixed-assets.md)   
 [How to: Set Up Fixed Asset Depreciation Books Manually](../how-to-set-up-fixed-asset-depreciation-books-manually.md)   
 [How to: Set Up Fixed Asset Depreciation Books Automatically](../how-to-set-up-fixed-asset-depreciation-books-automatically.md)   
 [How to: Fill In and Post Fixed Asset General Ledger Journals](../how-to-fill-in-and-post-fixed-asset-general-ledger-journals.md)   
 [How to: Fill In and Post Fixed Asset Journals](../how-to-fill-in-and-post-fixed-asset-journals.md)