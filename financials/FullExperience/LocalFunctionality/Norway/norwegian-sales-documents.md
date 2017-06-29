---
title: "Norwegian Sales Documents"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "sales documents, Norwegian"
ms.assetid: 0a5d479d-2294-41c1-9bc3-29aa9cf38117
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "nb-no"
---
# Norwegian Sales Documents
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] supports two sets of sales documents. A document set consists of a sales invoice, sales credit memo, reminder, and finance charge memo.  
  
 Set 1 is based on international reports. You cannot print Norwegian giro or use paper sources\/trays in this set of reports.  
  
 Set 2 contains reports designed for use in Norway. These reports print Norwegian giro. When printing these reports, you can use paper sources\/trays specified in the **\($ T\_78 Printer Selections $\)** table.  
  
## Document Set 1  
 The first document set consists of standard reports that do not contain any settings specific to Norway. For example, giro transactions are not printed and paper sources\/trays cannot be processed.  
  
 Document set 1 contains the following reports:  
  
-   **\($ R\_206 Sales \- Invoice $\)**  
  
-   **\($ R\_207 Sales \- Credit Memo $\)**  
  
-   **\($ R\_117 Reminder $\)**  
  
-   **\($ R\_118 Finance Charge Memo $\)**  
  
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