---
    title: How to Print Periodic VAT Reports
    description: The VAT reporting feature enables you to print VAT transaction details. You must send three VAT reports to the Belgian tax authorities.

    services: project-madeira 
    documentationcenter: ''
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
# Print Periodic VAT Reports
The VAT reporting feature enables you to print VAT transaction details. You must send the following VAT reports to the Belgian tax authorities:  

- Monthly/Quarterly declaration  
- VAT annual listing (on paper/disk)  
- VAT-VIES listing (on paper/disk)  

## To print the monthly/quarterly declaration  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Form/Intervat Declaration**, and then choose the related link.  
2.  On the **VAT – Form** page, fill in the fields.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**Wrong Enterprise No.**|Specifies if you want to print the report that has erroneous enterprise numbers.|  
    |**VAT Annual Listing**|Specifies if you want to print the **VAT Annual Listing** report.|  
    |**Year**|Enter the year of the period for which you want to print the report. You should enter the year as a four-digit code. For example, to print a declaration for 2013, you should enter "2013" (instead of "13").|  
    |**Minimum Amount**|Enter the customer's minimum year balance to be included in the report. If the yearly balance of the customer is less than the minimum amount, the customer will not be included in the declaration.|  
    |**Include Customers From**|Select to include customers from all countries/regions or from a specific country/region in the report.|  
    |**Country/Region**|Select the country/region to include in the report.|  

3.  Choose the **Print** button to print the report, or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  

## To print the VAT annual listing on disk  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Annual Listing – Disk**, and then enter the related link.  
2.  On the **VAT Annual Listing – Disk** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Year**|Enter the year of the VAT declaration. You should enter the year as a four-digit code. For example, to print a declaration for 2013, you should enter "2013" (instead of "13").|  
    |**Minimum**|Enter the customer's minimum year balance to be included in the report.<br /><br /> If the yearly balance of the customer is less than the minimum amount, the customer will not be included in the declaration.|  
    |**Test Declaration**|Specifies if you want to create a test declaration.<br /><br /> If selected, an attribute test is written to the file that uses value 1, which indicates that this is a test file. If you want to test the XML file before sending it, you can upload this file to the Intervat site. The file is then validated without being stored on the server, and you receive a notification if the file is valid. Also, the unique sequence number in the XML file is not increased when a test declaration is created, which means that you can create as many internal test declarations as you want.|  
    |**Add Representative**|Specifies if you want to include the VAT declaration representative.<br /><br /> A representative is a person or an agency that has license to make a VAT declaration for your company.|  
    |**ID**|Enter the ID of the representative who is responsible for making the VAT declaration.|  
    |**File Name**|Enter the path and name of the file to which you want to create the declaration.|  

3.  Choose the **Print** button to print the report, or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  

## To print the VAT-VIES declaration report to disk  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter the **VAT – Vies Declaration Disk**, and then choose the related link.  
2.  Enter the required information, and choose the **OK** button to start the batch job, which will create a .xml file. For more information, see VAT- VIES Declaration Disk.  
3.  If you have to make a correction, Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT – VIES Correction**, and then choose the related link.  
4.  Choose the **Edit List** action, and then enter the information that has to be adjusted. Choose the **OK** button.  

## See Also  
 [Belgian VAT](belgian-vat.md)   
 [Set Up Non-Deductible VAT](how-to-set-up-non-deductible-vat.md)
