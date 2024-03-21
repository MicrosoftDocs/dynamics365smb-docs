---
title: Set up the IRS 1099 Form [US]
description: Learn how to set up the 1099 tax forms so that you can calculate and submit the required reports.
author: altotovi

ms.topic: conceptual
ms.search.keywords: local, 1099, IRS, Tax
ms.search.form: 26, 10030, 10031, 10033, 10034
ms.date: 03/21/2024
ms.author: altotovi
ms.reviewer: 

ms.service: dynamics-365-business-central
---

# Set Up the IRS 1099 Forms in the US Version

## Enabling Feature  

To enabling this feature you nedd to follow next steps:  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Feature Management**, and then choose the related link.
2. Find the following feature: **Feature Update: Enable using 1099 forms to transmit the tax data to the IRS in the United States.**
3. In the **Enabled for** column, change the status to **All Users**.
4. Confirm the consent, clicking the **Yes** buitton.   
5. Become familiar with the feature and click the **Next** button after that.
6. Specify the **Reporting Year** you will use.   
7. Specify the setup data you will use for the IRS Forms. You can choose to create a new default setup data in an app marking the **Create new setup** field, or to use transferring existing data, upgrading it from existing 1099 base application marking the **Transfer Existing Data** field.  

  > [!NOTE]
  > If you’re setting up [!INCLUDE[prod_short](../../includes/prod_short.md)] for the first time, choose **Create New Setup** and [!INCLUDE[prod_short](../../includes/prod_short.md)] will create the forms and associated setup so you can fill out and print them. If you’re upgrading and already have data for your 1099 form, you can choose **Transfer Existing Data** to take your existing setup from the previous solution or to start with **Create New Setup**.
 
8. Specify how the IRS Forms will work with documents, as you can choose to mark the **Collect Details For Line** field or not. If you mark this field this will enable you to drill down to the **IRS 1099 Form Doc Line Details** page for each of **Calculated Amounts** in the **IRS 1099 Form Document**, but this option requires an extra space in the database. 
9. You can choose one more option during setup – **Protect TIN** (Taxpayer Identification Number). You can choose not to protect TIN numbers, but also to mask or protect TIN for vendors or for both vendors and your company. Using this protection option will enable you to print only the last four digits on you printing forms, truncating the first 5 digits of the 9-digit number and replacing these digits with Xs, following the IRS regulations (example: XXXXX1234) and providing more security when sending documents using the email option, protecting the recipient from identity theft.  
10. Finish the setup.    

## Manual Setup  

If you didn’t finish the setup during enabling this feature or want to change or add some configurations, follow next steps:  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Forms Setup**, and then choose the related link. 
2. On the **General** FastTab you can change the setup for the **Collect Details For Line** and **Protect TIN** fields, as we previously explained.  
3. You can also set up details for the email you want to send to your recipients:

   - To do so, you can change the subject you will use in the **Email Subject** FastTab.  
   - You can also change to email body in the **Email Body** FastTab. When you entering your email body, you can use rich text editor.  

4. Close the page.   

## Reporting Periods and Forms Setup  

To configure reporting periods and forms, follow the next steps:   

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
2. In the **IRS Reporting Periods** page, you can specify different reporting periods and **Starting** and **Ending Date** for their validity. To set up specific 1099 forms for this period, you need to run the **Forms** action to open the **IRS Reporting Periods** page.  
3. In the **IRS 1099 Forms** page, you can specify different 1099 form types (MISC, NEC…). As all of these form types have more than one source with different rules, you need to setup them. To do so, you need to run the **Form Boxes** action to open the **IRS 1099 Form Boxes** page.  
4. In the **IRS 1099 Form Boxes** page, you can set up different sources for your form type using **No.** and **Description** fields, and you must fill in the **Minimum Reportable Amount** based on the IRS instruction for this reporting year, and those minimum reportable amounts can be populated whether a certain form box needs to be reported or not. 
5. Close the **IRS 1099 Form Boxes** page.   
6. Close the **IRS 1099 Forms** page.    

> [!NOTE]
> Every year, users must create a new reporting period. Recommendation is to use the **Copy Setup From** action on the **IRS Reporting Periods** page and choose the reporting period they want to copy from. With this process, all forms, form boxes, vendor setup, adjustment and form statement, except the form documents will be copied to the selected period.  

## Vendors Setup  

From the **IRS Reporting Periods** page, you can run the **Vendor Setup** action to open the **IRS 1099 Vendor Form Box Setup** page where you can map the form boxes to each vendor in the certain period. When you create a document for a certain vendor, the system will use this setup to fill in the form boxes. To do this, you need to follow next steps:

1.	Enter the **Vendor No.** field to specify the vendor number.  
2.	Use the **Form No.** field to specify the vendor number.   
3.	Use the **Form Box No.** field to specify the number of the 1099 form box. 

You do not need to set up vendors manually, and you can use the **Suggest** action to run **IRS 1099 Suggest Vendors** automation. Running this action, you can choose different types of filters to apply these vendors to the list. Once you do this, you just need to add default **Form No.** and **Form Box No.** for the list of vendors.  

You can make the same setup from the Vendor list page, using the action IRS Setup in the Related action group.

> [!NOTE]
> Keep in mind that this vendor setup is related to the specific period you configured in the **IRS Reporting Periods** page.  

Users will maybe need to make some additional setup on the **Vendor** card. To do this, follow next steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
2. All details related to the 1099 reporting can be found in the **Payments** FastTab. First, the user can see default values for the following fields, based on the **IRS 1099 Vendor Form Box Setup** configuration:

   - IRS Reporting Period
   - IRS 1099 Form No.
   - IRS 1099 Form Box No.

3. To configure additional required information, you can do the following:  

   - Mark the **Receiving 1099 E-Form Consent** field to acknowledge that your vendor has provided signed consent to receive their 1099 form electronically using email. You cannot mark this field if a minimum email address is not added for this vendor. 
   - If you want to use different emails for delivering IRS related emails, you can enter this information in the **E-Mail For IRS** field. Otherwise, the system will use the **Email** field.  
   - Users can mark the **FATCA Requirement** field to specify if the vendor is set up to require FATCA filing.   

## Printing Report Configuration

To print the form substitute documents there are a few setups you must use. For every single printing form there is a **Form Statement**. These statements are already configured, but user can change or update through configuration. To do this, follow next steps:  

1. To be able to configure or customize printing form, choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter the **IRS 1099 Forms**, and then choose the related link. 
2. When you open the **IRS 1099 Forms** page, for specific form **No.** run the **Edit Statement** action.  
3. The **IRS 1099 Form Statement** page will be opened, and, on this page, you can set up the filters and rules which will be applied to the form document lines for printing. You can use the following fields to set up the 1099 form statement:  

   - **Row No.** – Specifies a number that identifies the line, and it is used as a form box number on the printed report.  
   - **Description** – Specifies a description of the 1099 form box on the printed report.  
   - **Print Value Type** – Specifies the print value type of the statement. If the **Amount** is selected, then the amount calculated by the filter expression is printed. If the **Yes/No** option is selected, then either **Yes** or **No** is printed based on the **Yes/No** condition. 
   - **Filter Expressions** - Specifies the filter expression of the statement.   
   - **Row Totaling** – Specifies a row-number interval or a series of row numbers.  
   - **Print with** – Specifies whether amounts on the 1099 form box will be printed with their original sign using the option **Sign** or with the sign reversed using the option **Opposite Sign**. 

4. Close the page.   
5. Also, for every single form you can set up the recipient instructions. These instructions will be printed on the second page of the report layout, and this is required for the form printing by IRS as they explain meaning of each form box. To do so, from the **IRS 1099 Forms** page and for specific form **No.** run the **Edit Instructions** action to open the **IRS 1099 Form Instructions** page, where you can populate the **Header** (it will be printed as a bold text) and **Description** fields (it will be printed as a regular text).  
6. Close the page.  

## See also 

[United States Local Functionality](united-states-local-functionality.md)  
[How to use the IRS 1099 forms](how-to-1099-use.md)
[How to submit and report the IRS 1099](how-to-1099-report.md)
[Register New Vendors](../../purchasing-how-register-new-vendors.md)  
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
