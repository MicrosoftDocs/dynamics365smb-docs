---
    title: Troubleshooting - RapidStart Services | Microsoft Docs
    description: This topic describes some common problems that you may see when you use RapidStart Services.
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
# Troubleshooting: RapidStart Services
This topic describes some common problems that you may see when you use RapidStart Services.  

## Binary type not supported  
 If you add a table to the Configuration Worksheet that contains a field of the Binary data type, you may receive the following error message:  

 **The type Binary is not supported.**  

 You may be unable to use navigation pane links or a ribbon action to reopen the worksheet. Other links, including those to tables listed in the worksheet, also become inoperable.  

 To resolve this error, consider the following change to your implementation. Before adding a table to the **Configuration Worksheet** window, check to see whether it contains fields of the Binary type, and modify the table before you continue with the addition.  

 For more information, see [Changes in C-AL Behavior and Support from Earlier Versions of Microsoft Dynamics NAV].  

## See Also  
