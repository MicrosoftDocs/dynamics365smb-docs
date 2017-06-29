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
# Norwegian Sales Documents
FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> supports two sets of sales documents. A document set consists of a sales invoice, sales credit memo, reminder, and finance charge memo.  
  
 Set 1 is based on international reports. You cannot print Norwegian giro or use paper sources\/trays in this set of reports.  
  
 Set 2 contains reports designed for use in Norway. These reports print Norwegian giro. When printing these reports, you can use paper sources\/trays specified in the **Printer Selections** table.  
  
## Document Set 1  
 The first document set consists of standard reports that do not contain any settings specific to Norway. For example, giro transactions are not printed and paper sources\/trays cannot be processed.  
  
 Document set 1 contains the following reports:  
  
-   **Sales \- Invoice**  
  
-   **Sales \- Credit Memo**  
  
-   **Reminder**  
  
-   **Finance Charge Memo**  
  
## Document Set 2  
 The second document set prints Norwegian giro on every page. The giro on the last page contains information about the amount.  
  
 Document set 2 contains the following reports:  
  
-   **\($ R\_10604 Sales \- Invoice 2 $\)**  
  
-   **\($ R\_10605 Sales \- Credit Memo 2 $\)**  
  
-   **\($ R\_10615 Reminder 2 $\)**  
  
-   **\($ R\_10607 Finance Charge Memo 2 $\)**  
  
## See Also  
 [Norwegian Giro and OCR\-B Font](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/norwegian-giro-and-ocr-b-font.md)   
 [Paper Sources and Tray Numbers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Norway/paper-sources-and-tray-numbers.md)