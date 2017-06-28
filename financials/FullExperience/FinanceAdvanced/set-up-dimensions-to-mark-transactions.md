---
title: "Set Up Dimensions to Mark Transactions"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "dimensions, setting up to mark transactions"
  - "dimensions, setting up"
ms.assetid: 5448edbc-f0a0-4393-9e01-f1335c361669
caps.latest.revision: 3
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Set Up Dimensions to Mark Transactions
Dimensions are data that you add to entries to categorize them for analysis. For example, you can have dimensions that indicate which project or department an entry originates from. Than you can use dimensions instead of setting up separate general ledger accounts for each department and project. This allows you to have rich analysis information in your data without having to use a complicated chart of accounts. You can define an unlimited number of dimensions with an unlimited number of dimension values.  
  
 You set up all of the different dimensions that you want to track in the Dimensions window. The Dimensions window contains one line for each dimension, such as Project, Department, Area, and Salesperson.  
  
 For each dimension, you need to set up the dimension values, for example, all of the departments in your company. Dimension values can be set up in a hierarchical structure similar to the chart of accounts, so that data can be broken down into various levels of granularity, and subsets of dimension values can be totaled.  
  
 You can specify two global dimensions that will automatically be available everywhere, for example on reports and batch jobs. You can also specify six additional shortcut dimensions that will be available as a field on journal and document lines. The remaining dimensions can be used by accessing a separate window that displays dimensions for the line.  
  
 You can make a dimension mandatory, and you can specify default dimensions for:  
  
-   An individual account  
  
-   A particular group of accounts within an account type  
  
-   An entire account type, for example all customers  
  
 If you use default dimensions, there can be conflicts if two accounts on a line have different values for the same dimension. You can define which source has the highest priority. You can also block combinations of dimensions or dimension values.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Learn about dimensions and what you can use them for.|[\($ T\_348 Dimension $\)](assetId:///09a43eac-15fc-4036-9913-fe2b74a18bf3)|  
|Set up a dimension and its values.|[How to: Set Up Dimensions and Dimension Values](../Finance/how-to-set-up-dimensions-and-dimension-values.md)|  
|Select two dimensions that will be available globally and can be used as filters for general ledger entries, as well as on all reports, account schedules and batch jobs.|[How to: Set Up Global Dimensions](../Finance/how-to-set-up-global-dimensions.md)|  
|Select up to six dimensions, in addition to the global dimensions, that you will be able to access directly from journal or document lines.|[How to: Set Up Shortcut Dimensions](../Finance/how-to-set-up-shortcut-dimensions.md)|  
|Set up default dimension values for a single account, such as a customer.|[How to: Set Up Default Dimensions for One Account](../Finance/how-to-set-up-default-dimensions-for-one-account.md)|  
|Set up default dimension values for a group of accounts that you define.|[\($ N\_542 Default Dimension \- Multiple $\)](assetId:///9dbb8368-e787-472c-86b4-e8157799bfe1)|  
|Set up default dimension values, or make a dimension mandatory for an account type, such as customer or salesperson accounts.|[How to: Set Up Default or Required Dimensions for Account Types](../Finance/how-to-set-up-default-or-required-dimensions-for-account-types.md)|  
|Specify how to handle conflicts between default dimension values, for example from different sources on a journal or document line.|[How to: Set Up Default Dimension Priorities](../Finance/how-to-set-up-default-dimension-priorities.md)|  
|Block or limit specific combinations of two dimensions.|[How to: Set Up Dimension Combinations](../Finance/how-to-set-up-dimension-combinations.md)|  
|Display the global dimensions in a ledger entries window, filter ledger entries by dimension, or view all the dimensions on an individual entry.|[How to: View Global Dimensions in Ledger Entry Windows](../Finance/how-to-view-global-dimensions-in-ledger-entry-windows.md)|