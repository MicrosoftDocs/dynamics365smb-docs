---
    title: Tips and Tricks - RapidStart Services | Microsoft Docs
    description: When you configure companies using RapidStart Services, there are some tips and tricks that you can take advantage of to help your implementation go smoothly.
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
# Tips and Tricks: RapidStart Services
When you configure companies using RapidStart Services, there are some tips and tricks that you can take advantage of to help your implementation go smoothly.  

## Take advantage of configuration templates  
Configuration templates can help you streamline your implementation process. By using them, you can include similar customers in segments and then develop an implementation protocol that treats all customers in a segment in a similar manner. In that way, you can apply a level of preconfiguration to each segment and continue with a rapid implementation.  

## Configuration questionnaires  
To aid the process of filling out a configuration questionnaire, consider defining default answers to indicate best practices.  

## Batch creation of journal lines  
We recommend that you use the data migration tools provided to migrate journal entries. Otherwise, if you use a batch job to create journal lines, that has a limited scope and only generates pre-default fields into a journal. The rest of the journal then has to be completed manually.  

## Migrating transactions  
We recommend that you migrate opening balances in the following order. <!--Be aware that you cannot insert ledger entries directly. Instead you must use journals to post the journal lines--> 

1.  Migrate general ledger opening balances without using the general ledger account subledgers. Use specific opening balance offsetting accounts, one set up for each subledger. Set up the offsetting accounts to enable direct postings.  
2.  Migrate open customer ledger entries.  <!--work on these-->
3.  Migrate open item ledger entries.  
4.  Migrate open fixed asset entries.  

## See Also  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
