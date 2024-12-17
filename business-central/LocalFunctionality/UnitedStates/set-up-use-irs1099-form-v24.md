---
title: Set up the IRS 1099 form for version 24 [US]
description: Learn how to set up the 1099 tax forms so that you can calculate and submit the required reports.
author: altotovi
ms.topic: conceptual
ms.search.keywords: local, 1099, IRS, Tax
ms.search.form: 26, 10030, 10031, 10033, 10034
ms.date: 04/03/2024
ms.author: altotovi
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
---

# Set up the IRS 1099 forms

The Internal Revenue Service (IRS) requires one or more versions of the 1099 tax form for payments to vendors. Copies of these forms must be sent to vendors annually on or before the last day of January. On your purchase documents, you can specify that the document is 1099 liable, and you can specify the 1099 code for the vendor.


## To enable this feature to transmit the tax data using 1099 form 

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Feature Management**, and then choose the related link.
1. Find the following feature: **Feature Update: Enable using 1099 forms to transmit the tax data to the IRS in the United States.** that you want to enable.
1. In the **Feature** column, choose the three vertical dots, and then choose the **Select More** action.
1. Select the check box for all the features that you want to edit, and then choose **Edit List**.
1. In the **Enabled for** column, change the status to **All Users**.
1. Choose the **Yes** button.   
1. Become familiar with the feature and, then choose the **Next** button.
1. Specify the **Reporting Year** you'll use.   
1. Define the setup data you'll use for the IRS Forms.
1. By selecting the **Create new setup** field, you can choose to create a new default setup data in an app.
1. To transfer the existing data from the 1099 base application, select the **Transfer Existing Data** field.  

> [!NOTE]
> If you’re establishing [!INCLUDE[prod_short](../../includes/prod_short.md)] for the first time, choose **Create New Setup** to create the forms and associated setups, and then you can fill in the appropriate fields in the forms and print them. If you’re upgrading and already have data for your 1099 form, you can choose **Transfer Existing Data** from the previous solution.

12. Specify how the IRS forms work with documents, as you can decide to choose the **Collect Details For Line** field. By selecting this field, the details will be collected from the **IRS 1099 Form Doc Line Details** page for each of **Calculated Amounts** in the **IRS 1099 Form Document**, but this option requires an extra space in the database.

> [!NOTE]
> If you don't select this field, the total amount will be calculated without the details.

13. You can choose one more option during setup.
**Protect TIN** (Taxpayer Identification Number) to mask or protect TIN for vendors or for both vendors and your company.  
You can also choose not to protect TIN numbers if you want.

> [!NOTE]
> Using this protection option, enables you to print only the last four digits on your printing forms, truncating the first 5 digits of the 9-digit number and replacing these digits with Xs, following the IRS regulations (example: XXXXX1234), and providing more security when sending documents using the email option, protecting the recipient from identity theft.  

 14. Finish the setup.    

## Manual setup  

If you aren't able to finish the setup while enabling this feature or want to modify or add some configurations, follow these steps:  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Forms Setup**, and then choose the related link. 
2. On the **General** FastTab, you can change the setup for the **Collect Details For Line** and **Protect TIN** fields, as mentioned previously.  
3. You can also set up details for the email you want to send to your recipients:

   - To do so, you can change the subject you'll use in the **Email Subject** FastTab.  
   - You can also change the email body in the **Email Body** FastTab. To edit your email body, you can use rich text editor.  

4. Close the page.   

## Reporting periods and forms set up  

To configure reporting periods and forms, follow the steps:   

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
2. On the **IRS Reporting Periods** page, you can specify the time period that the report applies.
**Starting** and **Ending Date** for their validity. To set up specific 1099 forms for this period, you need to run the **Forms** action to open the **IRS Reporting Periods** page.
3. Run the **Forms** action to open the **IRS 1099 Forms** page.  
4. On the **IRS 1099 Forms** page, you can specify different 1099 form types, such as MISC, NEC, etc. As all of these form types have more than one source with different rules, you need to set them up. To do so, you need to run the **Form Boxes** action to open the **IRS 1099 Form Boxes** page.   
5. On the **IRS 1099 Form Boxes** page, you can set up different sources for your form type using **No.** and **Description** fields, and you must fill in the **Minimum Reportable Amount** based on the IRS instruction for this reporting year, and those minimum reportable amounts can be populated whether a certain form box needs to be reported or not. 
6. Close the **IRS 1099 Form Boxes** page.   
7. Close the **IRS 1099 Forms** page.    

> [!NOTE]
> Every year, users must create a new reporting period. Recommendation is to use the **Copy Setup From** action on the **IRS Reporting Periods** page and choose the reporting period they want to copy from. With this process, all forms, form boxes, vendor setup, adjustment and form statement, except the form documents will be copied to the selected period.  

## Vendors setup  

From the **IRS Reporting Periods** page, you can run the **Vendor Setup** action to open the **IRS 1099 Vendor Form Box Setup** page where you can map the form boxes to each vendor in the certain period. When you create a document for a certain vendor, the system uses this setup to fill in the form boxes. To do this, you need to follow the steps:

1.	Enter the **Vendor No.** field to specify the vendor number.  
2.	Use the **Form No.** field to specify the vendor number.   
3.	Use the **Form Box No.** field to specify the number of the 1099 form box. 

You don't need to set up vendors manually, and you can use the **Suggest** action to run **IRS 1099 Suggest Vendors** automation. Running this action, you can choose different types of filters to apply these vendors to the list. Once you do this, you just need to add default **Form No.** and **Form Box No.** for the list of vendors.  

By choosing the **IRS Setup** action in the **Related** menu, you can do the same setup from the **Vendor list** page.

> [!NOTE]
> Note that this vendor setup is related to the specific period you configured on the **IRS Reporting Periods** page.  

Users might need to make some additional setup on the **Vendor card** page. To do this, follow the steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
2. All details related to the 1099 reporting can be found in the **Payments** FastTab. First, the user can see default values for the following fields, based on the **IRS 1099 Vendor Form Box Setup** configuration:

   - **IRS Reporting Period**
   - **IRS 1099 Form No.**
   - **IRS 1099 Form Box No.**

3. To configure additional required information, you can do the following:  

   - Mark the **Receiving 1099 E-Form Consent** field to acknowledge that your vendor has provided signed consent to receive their 1099 form electronically using email. You can't mark this field if a minimum email address isn't added for this vendor. 
   - If you want to use different emails for delivering IRS related emails, you can enter this information in the **E-Mail For IRS** field. Otherwise, the system uses the **Email** field.  
   - Users can mark the **FATCA Requirement** field to specify if the vendor is set up to require FATCA filing.   

## To print report configuration

To print the form substitute documents, there are a few setups you must use. For every single printing form, there's a **Form Statement**. These statements are already configured, but users can change or update through configuration. To do this, follow the steps:  

1. To configure or customize the printing form, choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter the **IRS Reporting Periods**, and then choose the related link.
2. Run the **Forms** action to open the **IRS 1099 Forms** page.
3. When you open the **IRS 1099 Forms** page for a specific form **No.**, choose the **Edit Statement** action.  
4. The **IRS 1099 Form Statement** page opens, and, on this page, you can set up the filters and rules, which will be applied to the form document lines for printing. You can use the following fields to set up the 1099 form statement:  

   - **Row No.** – Specifies a number that identifies the line, and it's used as a form box number on the printed report.  
   - **Description** – Specifies a description of the 1099 form box on the printed report.  
   - **Print Value Type** – Specifies the print value type of the statement. If the **Amount** is selected, then the amount calculated by the filter expression is printed. If the **Yes/No** option is selected, then either **Yes** or **No** is printed based on the **Yes/No** condition. 
   - **Filter Expressions** - Specifies the filter expression of the statement.   
   - **Row Totaling** – Specifies a row-number interval or a series of row numbers.  
   - **Print with** – Specifies whether amounts on the 1099 form box will be printed with their original sign using the option **Sign** or with the sign reversed using the option **Opposite Sign**. 

5. Close the page.

> [!NOTE]  
> Also, for every single form you can set up the recipient instructions. These instructions will be printed on the second page of the report layout, and this is required for the form printing by IRS as they explain meaning of each form box. 
To do so, on the **IRS 1099 Forms** page and for specific form **No.**, choose the **Edit Instructions** action to open the **IRS 1099 Form Instructions** page, where you can populate the **Header** (it will be printed as a bold text) and **Description** fields (it will be printed as a regular text).  


## See also

[United States Local Functionality](united-states-local-functionality.md)  
[How to submit and report the IRS 1099](set-up-use-irs1099-form-v24.md#to-print-report-configuration)  
[Register New Vendors](../../purchasing-how-register-new-vendors.md)  
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
