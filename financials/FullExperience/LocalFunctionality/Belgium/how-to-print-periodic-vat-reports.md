---
title: "How to: Print Periodic VAT Reports"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, periodic reports"
ms.assetid: a54343b6-99eb-4e0f-af7d-4c6bbba47217
caps.latest.revision: 6
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Print Periodic VAT Reports
The VAT reporting feature enables you to print VAT transaction details. You must send the following VAT reports to the Belgian tax authorities:  
  
-   Monthly\/Quarterly declaration  
  
-   VAT annual listing \(on paper\/disk\)  
  
-   VAT\-VIES listing \(on paper\/disk\)  
  
### To print the monthly\/quarterly declaration  
  
1.  In the **Search** box, enter **Form\/Intervat Declaration**, and then choose the related link.  
  
2.  In the **\($ R\_11307 VAT – Form $\)** window, fill in the fields.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_11307\_F\_1\_2 Declaration Type $\)**|Specify the type of declaration that you want to print. Options include **Month** and **Quarter**.|  
    |**\($ R\_11307\_F\_1\_5 Month or quarter $\)**|Enter the month or quarter of the VAT declaration.<br /><br /> -   If you select **Month**, you must enter a value between 1 and 12 \(1 \= January, 2 \= February, and so on\).<br />-   If you select **Quarter**, you must enter a value between 1 and 4 \(1 \= first quarter, 2 \= second quarter, and so on\).|  
    |**\($ R\_11307\_F\_1\_7 Year \(YYYY\) $\)**|Enter the year of the VAT declaration. You should enter the year as a four digit code. For example, to print a declaration for 2013, you should enter "2013" \(instead of "13"\).|  
    |**\($ R\_11307\_F\_1\_9 Include VAT Entries $\)**|Specify the VAT entries to be included in the report. You can choose between **Open**, **Closed** and **Open and Closed**.|  
    |**Prepayment**|Specify how prepayments should be handled in the VAT declaration \(case 91\). Options include **Print Prepmt. Amount**, **Print Zero \(No Prepayment\)**, and **Leave Empty \(User November Amount\)**. Note that case 91 must not be filled for quarterly VAT declarations or for declarations in months other than December.|  
    |**\($ R\_11307\_F\_1\_14 Claim for Reimbursement $\)**|Specify if you want to claim the reimbursement of the amount due by the tax authorities after you have submitted the declaration.|  
    |**\($ R\_11307\_F\_1\_16 Order Payment Forms $\)**|Specify if you want to order new payment forms.|  
    |**\($ R\_11307\_F\_1\_1010002 No Annual Listing $\)**|Specify if you do not want an annual listing for the declaration.<br /><br /> You can only select this option for the last declaration of the calendar year.|  
    |**\($ R\_11307\_F\_1\_1010019 Add Representative $\)**|Specify if you want to add a VAT declaration representative. A representative is a person or an agency that has license to make a VAT declaration.|  
    |**ID**|Enter the ID of the representative who is responsible for making the VAT declaration.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  
  
     When you run the report, you must specify the path and file name to store your VAT declaration on disk. Later, you can send this file to the VAT administration via the Internet using Intervat. It is important that you create an XML file, because the VAT administration requires the XML file format for the data exchange.  
  
### To print the VAT annual listing on paper  
  
1.  In the **Search** box, enter **Annual Listing**, and then choose the related link.  
  
2.  In the **VAT Annual Listing** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_11308\_F\_1\_3 Wrong Enterprise No. $\)**|Specifies if you want to print the report that has erroneous enterprise numbers.|  
    |**\($ R\_11308\_F\_1\_5 VAT Annual Listing $\)**|Specifies if you want to print the **VAT Annual Listing** report.|  
    |**\($ R\_11308\_F\_1\_6 Year $\)**|Enter the year of the period for which you want to print the report. You should enter the year as a 4 digit code. For example, to print a declaration for 2013, you should enter "2013" \(instead of "13"\).|  
    |**\($ R\_11308\_F\_1\_8 Minimum Amount $\)**|Enter the customer's minimum year balance to be included in the report. If the yearly balance of the customer is less than the minimum amount, the customer will not be included in the declaration.|  
    |**\($ R\_11308\_F\_1\_10 Include Customers From $\)**|Select to include customers from all countries\/regions or from a specific country\/region in the report.|  
    |**\($ R\_11308\_F\_1\_13 Country\/Region $\)**|Select the country\/region to include in the report.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  
  
### To print the VAT annual listing on disk  
  
1.  In the Search box, enter **Annual Listing – Disk**, and then enter the related link.  
  
2.  In the **\($ R\_11309 VAT Annual Listing – Disk $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Year**|Enter the year of the VAT declaration. You should enter the year as a four digit code. For example, to print a declaration for 2013, you should enter "2013" \(instead of "13"\).|  
    |**Minimum**|Enter the customer's minimum year balance to be included in the report.<br /><br /> If the yearly balance of the customer is less than the minimum amount, the customer will not be included in the declaration.|  
    |**Test Declaration**|Specifies if you want to create a test declaration.<br /><br /> If selected, an attribute test is written to the file that uses value 1, which indicates that this is a test file. If you want to test the XML file before sending it, you can upload this file to the Intervat site. The file is then validated without being stored on the server and you receive a notification if the file is valid. Also the unique sequence number in the XML file is not increased when a test declaration is created, which means that you can create as many internal test declarations as you want.|  
    |**Add Representative**|Specifies if you want to include the VAT declaration representative.<br /><br /> A representative is a person or an agency that has license to make a VAT declaration for your company.|  
    |**ID**|Enter the ID of the representative who is responsible for making the VAT declaration.|  
    |**File Name**|Enter the path and name of the file to which you want to create the declaration.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  
  
### To print the VAT\-VIES declaration report to disk  
  
1.  In the **Search** box, enter the **VAT – Vies Declaration Disk**, and then choose the related link.  
  
2.  Enter the required information, and choose the **OK** button to start the batch job, which will create an xml file. For more information, see VAT\- VIES Declaration Disk.  
  
3.  If you have to make a correction, in the **Search** box, enter **VAT – VIES Correction**, and then choose the related link.  
  
4.  On the **Home** tab, in the **Manage** group, choose **Edit List**, and then enter the information that has to be adjusted. Choose the **OK** button.  
  
     For more information, see the VAT VIES Correction table.  
  
## See Also  
 [Belgian VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgian-vat.md)   
 [How to: Set Up Non\-Deductible VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-non-deductible-vat.md)