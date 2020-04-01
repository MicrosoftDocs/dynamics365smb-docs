---
    title: How to Create Report 340
    description: Report 340 includes all sales invoices and purchase invoices posted by a company during a given period. The report also includes the operation codes with related taxes and payments in cash.

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
# Create Report 340
Report 340 includes all sales invoices and purchase invoices posted by a company during a given period. The report also includes the operation codes with related taxes and payments in cash.  

This report is generated in a format approved by the tax authorities. You should submit this report on a monthly or quarterly basis, depending on the size of your company.  

## To create Report 340  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Make 340 Declaration**, and then choose the related link.  
2.  On the **Make 340 Declaration** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Fiscal Year**|Enter the fiscal year for which you want to create the operation declaration.|  
    |**Month**|Select the month that you want to include in the operations declaration.|  
    |**Min. Payment Amount**|Enter the amount that you have received in cash for the selected **G/L Acc. for Payments in Cash**. **Important:**  The field is designed for reporting payments in cash. The amount that you have selected decides the sum of customer entries in the report. If the total invoiced amount for a customer per year is less than the amount specified in the field, then the sum of the customer entries is not included in the report. If the total invoiced amount for a customer per year is greater than the amount specified in the field, then the sum of customer entries is included in the report. When you export the data to a declaration .txt file, you will see that the **Amount Received in Cash** field in the declaration .txt file contains the accumulated amount of customer entries in one line per year.|  
    |**G/L Acc. for Payments in Cash**|Select one or more on general ledger accounts to include only the entries that are posted to the filtered general ledger accounts in the report. **Important:**  The field is designed for reporting payments in cash. When you export the data to a declaration .txt file, you will see that the **Amount Received in Cash** field in the declaration .txt file contains the accumulated value for the selected general ledger accounts. If you do not select any general ledger accounts, type 2 lines for payments in cash will not be created.|  
    |**Contact Name**|Enter the surname and name for the company that is creating the operations declaration.|  
    |**Telephone Number**|Enter the telephone number for the company that is creating the operations declaration.|  
    |**Non Deduct. Gen. Prod. Post. Groups**|Select the general product posting group. The selected posting groups are non-deductible VAT.|  
    |**Declaration Number**|Enter the number to identify the operations declaration.|  
    |**Electronic Code**|Specify the electronic code that is provided by the tax authorities.|  
    |**Declaration Media Type**|Select the media type for the declaration.|  
    |**Replacement Declaration**|Select if this is a replacement of a previously sent declaration.|  
    |**Previous Declaration Number**|If the **Replacement Declaration** option is selected, enter the previous declaration number.|  

3.  Select the appropriate filters, and then choose the **OK** button. The text file for report 340 is created in the specified path.  

## To create a Modelo 340 report under the CAC regimen  

1.  Perform the steps in the previous procedure.  
2.  As needed, adjust and modify the operation code information. In order for the report to pass validation when you submit it to the tax authority, any line that has an unrealized payment must be updated to include an operation code. You can change an operation code of Z or 3 to Z or 1 – 8 only for cash based payments.  
3.  Choose the **OK** button. The report is exported to the file location that you specified. The report will only contain lines for invoices, credit memos, whether applied or not, and payments that have unrealized VAT.  

    Invoices will be exported and will contain the Z operation code. Collection data is blank.  

    Payments against an invoice will be exported and will contain the collection data.  

If you print the posted document, for example, a posted sales invoice, it will include the following label: **Régimen especial del criterio de caja**.  

## See Also  
 [Report 340](report-340.md)   
 [Payments in Cash](payments-in-cash.md)   
 [Spanish Tax Agency](https://www.agenciatributaria.es/AEAT.internet/en_gb/Inicio.shtml)
