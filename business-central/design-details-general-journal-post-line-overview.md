---
    title: General Journal Post Line Overview | Microsoft Docs
    description: This topic introduces changes to Codeunit 12, **Gen. Jnl.-Post Line**, which is the major application object for general ledger posting and is the only place to insert general ledger, VAT, and customer and vendor ledger entries.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, general ledger, post
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# General Journal Post Line Overview
Codeunit 12, **Gen. Jnl.-Post Line**, is the major application object for general ledger posting and is the only place to insert general ledger, VAT, and customer and vendor ledger entries. This codeunit is also used for all Apply, Unapply and Reverse operations.  
  
While the codeunit has been improved in each release over the last ten years, its architecture remained essentially unchanged. The codeunit became very large, with approximately 7,600 code lines. With this release of [!INCLUDE[d365fin](includes/d365fin_md.md)], the architecture is changed and the codeunit has been made simpler and more maintainable. This documentation introduces the changes and provides information that you will need for upgrade.  
  
## Old Architecture  
The old architecture had the following features:  
  
* There was extensive use of global variables, which increased the possibility of hidden errors due to use of variables with the wrong scope.  
* There were many long procedures (with more than 100 code lines) that also had high cyclomatic complexity (that is, a lot of CASE, REPEAT, IF nested statements), which made the code very difficult to read and maintain.  
* Several procedures that were only used locally and were only meant to be used locally were not marked as local.  
* Most procedures had no parameters and used global variables. Some used parameters and overrode global variables with locals.  
* Code patterns for searching the general ledger accounts and creating general ledger and VAT entries was not standardized and varied from place to place. In addition, there was a lot of code duplication and broken symmetry between customer and vendor code.  
* A large part of the code in codeunit 12, approximately 30 percent, related to payment discount and tolerance calculations, although these features are not needed in many countries or regions.  
* Posting, Apply, Unapply, Reverse, Payment Discount and Tolerance, and Exchange Rate Adjustment were married together in codeunit 12 using a long list of global variables.  
  
### New Architecture  
In [!INCLUDE[d365fin](includes/d365fin_md.md)], codeunit 12 has had the following improvements:  
  
* Codeunit 12 has been refactored into smaller procedures (all less than 100 code lines).  
* Standardized patterns for the search of general ledger accounts have been implemented by using helper functions from Posting Group tables.  
* A Posting Engine Framework has been implemented to manage the start and finish of transactions and to isolate the creation to general ledger and VAT entries, the collection of VAT adjustment, and the calculation of additional currency amounts.  
* Code duplication has been eliminated.  
* Many helper functions have been transferred to corresponding customer and vendor ledger entry tables.  
* The use of global variables has been minimized, so that each procedure uses parameters and encapsulates its own application logic.  
  
## See Also  
[Design Details: Posting Interface Structure](design-details-posting-interface-structure.md)   
[Design Details: Posting Engine Structure](design-details-posting-engine-structure.md)
