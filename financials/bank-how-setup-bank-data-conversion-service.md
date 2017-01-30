---
title: 'How to: Set Up the Bank Data Conversion Service| Microsoft Docs'
description: 'How to: Set Up the Bank Data Conversion Service'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/12/2016
ms.author: sgroespe

---
# How to: Set Up the Bank Data Conversion Service
You can export payment lines from the **Payment Journal** window to a data stream that you then upload to your bank for automatic processing so that do not have to make electronic payments individually. For more information, see [How to: Export Payments to a Bank File](payables-how-export-payments-bank-file.md).

A global provider of services to convert payment information to any data format that your bank requires is connected and ready to be enabled in Financials.

As an alternative to the Envestnet Bank Data Feeds service, you can also use the bank data conversion service to have a bank statement file that you receive from your bank converted to a data stream that you can import into Financials. For more information, see [How to: Apply Payments Automatically and Reconcile Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).

**Note**: The bank data conversion service may impose a limit on the number of lines that can be exported in one file. You will receive an error message if the limit is exceeded. It is recommended that bank statement files do not exceed 1000 lines as the processing time in the bank data conversion service may otherwise increase significantly.

## To sign your company up for the bank data conversion service
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Bank Data Conv. Service Setup**, and then choose the related link.  
2. The **Bank Data Conv. Service Setup** window opens with three fields prefilled with relevant URLs of the provider of bank data conversion service.
   
    **Note**: In the CRONUS International Ltd. demonstration database, the User Name and Password fields are prefilled with demonstration logon information, which you will replace with your company’s actual information as you sign up for the bank data conversion service.
3. In the **Sign-up URL** field, choose the browser button to open the service provider’s sign-up page.  
4. On the sign-up page of the bank data service provider, enter the user name and password for your company’s subscription to the service, and then complete the sign-up process as instructed by the service provider.
   
    Your company is now signed up for the bank data conversion service. Proceed to enter the user name and password that you specified for the service in the related setup fields in Financials.
5. In the **Bank Data Conv. Service Setup** window, in the User **Name** field, enter the same value that you entered as logon name on the service provider’s page in step 4.
6. In the **Password** field, enter the same value that you entered in the **Password** field on the service provider’s page in step 4.

## To encrypt your login information
It is recommended that you protect the logon information that you enter in the **Bank Data Conv. Service Setup** window. You can encrypt data on the Financials Server by generating new or importing existing encryption keys that you enable on the Financials Server instance that connects to the database.

1. In the **Bank Data Conv. Service Setup** window, choose the **Encryption Management** action.
2. In the **Data Encryption Management** window, enable encryption of your data.

## To view or update the list of currently supported bank data formats
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Bank Data Conv. Service Setup** , and then choose the related link.
2. In the **Bank Data Conv. Service Setup** window, choose the **Bank Name - Data Conversion List** action to open the list of bank names representing bank data formats that are supported by the conversion service.
3. In the **Bank Name - Data Conversion List** page, choose the **Update Bank Name List** action.

The list of bank data formats that are supported by the bank data conversion service is now updated. This is the list of bank names, filtered by the country/region, that you can select from in the **Bank Name - Data Conversion** field in the **Bank Account Card** window.

**Note**: The update of supported bank data formats also occurs when you select or enter a value in the **Bank Name - Data Conversion** field on the bank account.

You have now signed up for the bank data conversion service. Proceed to reflect the sign-up information on every bank account that will use the service.

## To set up bank accounts to use the bank data conversion service
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Bank Accounts**, and then choose the related link.
2. Open the card for a bank account that you will export or import bank files for by using the bank data conversion service.
3. On the **Transfer** FastTab, in the **Payment Export Format** field, choose **Bank Data Conversion Service - Credit Transfer** to set up for payment export.
4. In the **Bank Name - Data Conversion** field, enter or select the name of the bank’s data format that you signed-up for in step 4 in the “To sign up for the bank data conversion service” section.
5. Repeat steps 1 through 4 for other bank accounts that will use the bank data conversion service .

## See Also
[Setting Up Banking](bank-setup-banking.md)  
[Managing Bank Accounts](bank-manage-bank-accounts.md)  
[Working With Financials](ui-work-product.md)

