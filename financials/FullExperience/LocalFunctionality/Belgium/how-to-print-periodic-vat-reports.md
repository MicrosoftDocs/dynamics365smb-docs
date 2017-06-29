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
# How to: Print Periodic VAT Reports
The VAT reporting feature enables you to print VAT transaction details. You must send the following VAT reports to the Belgian tax authorities:  
  
-   Monthly\/Quarterly declaration  
  
-   VAT annual listing \(on paper\/disk\)  
  
-   VAT-VIES listing \(on paper\/disk\)  
  
### To print the monthly\/quarterly declaration  
  
1.  In the **Search** box, enter **Form\/Intervat Declaration**, and then choose the related link.  
  
2.  In the **\($ R\_11307 VAT – Form $\)** window, fill in the fields.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---
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

    ---------------------------------|---------------------------------------|  
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
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Year**|Enter the year of the VAT declaration. You should enter the year as a four digit code. For example, to print a declaration for 2013, you should enter "2013" \(instead of "13"\).|  
    |**Minimum**|Enter the customer's minimum year balance to be included in the report.<br /><br /> If the yearly balance of the customer is less than the minimum amount, the customer will not be included in the declaration.|  
    |**Test Declaration**|Specifies if you want to create a test declaration.<br /><br /> If selected, an attribute test is written to the file that uses value 1, which indicates that this is a test file. If you want to test the XML file before sending it, you can upload this file to the Intervat site. The file is then validated without being stored on the server and you receive a notification if the file is valid. Also the unique sequence number in the XML file is not increased when a test declaration is created, which means that you can create as many internal test declarations as you want.|  
    |**Add Representative**|Specifies if you want to include the VAT declaration representative.<br /><br /> A representative is a person or an agency that has license to make a VAT declaration for your company.|  
    |**ID**|Enter the ID of the representative who is responsible for making the VAT declaration.|  
    |**File Name**|Enter the path and name of the file to which you want to create the declaration.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  
  
### To print the VAT-VIES declaration report to disk  
  
1.  In the **Search** box, enter the **VAT – Vies Declaration Disk**, and then choose the related link.  
  
2.  Enter the required information, and choose the **OK** button to start the batch job, which will create an xml file. For more information, see VAT- VIES Declaration Disk.  
  
3.  If you have to make a correction, in the **Search** box, enter **VAT – VIES Correction**, and then choose the related link.  
  
4.  On the **Home** tab, in the **Manage** group, choose **Edit List**, and then enter the information that has to be adjusted. Choose the **OK** button.  
  
     For more information, see the VAT VIES Correction table.  
  
## See Also  
 [Belgian VAT](../belgian-vat.md)   
 [How to: Set Up Non-Deductible VAT](../how-to-set-up-non-deductible-vat.md)