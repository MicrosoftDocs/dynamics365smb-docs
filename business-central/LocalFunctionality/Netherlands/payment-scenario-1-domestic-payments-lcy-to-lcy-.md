---
    title: Payment Scenario 1 - Domestic Payments (LCY to LCY)
    description: You can use telebanking for trade with domestic and foreign customers and vendors.
    documentationcenter: ''
    author: SorenGP
    services: project-madeira
    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Payment Scenario 1 - Domestic Payments (LCY to LCY)
You can use telebanking for trade with domestic and foreign customers and vendors. This topic describes a scenario where the trade is with domestic customers and vendors.  

The following list describes the main steps:  

1.  Create Vendor/Customer.  
2.  Create Vendor/Customer Bank Account.  
3.  Create and Post Purchase Invoice for Vendor or Sales Invoice for Customer.  
4.  Create Proposal.  
5.  Create Payment History.  
6.  Export Payment History.  
7.  Import Bank Statement.  

> [!NOTE]  
>  In the examples below some standard CRONUS data is being used. Likewise instead of creating a vendor/customer and a vendor/customer bank account you could use existing data.  

## Create Vendor/Customer  
Create vendor/customer and enter all necessary information. Special attention should be paid to the following fields:  

- **Currency Code**: Leave empty - i.e. it is set to the local currency (LCY).  
- **Transaction Mode**: Select an appropriate, default transaction mode - i.e. one that can deal with local currency payments for your bank.  
- **Preferred Bank Account**: Select an appropriate, default vendor/customer bank account having the same Currency Code as the vendor/customer itself.  

> [!NOTE]  
>  In order to be able to enter a bank account in the **Bank Account** vendor/customer bank accounts must be available. See below.  

### Example  
Olek Johansson (code **OLEK**) is one of our local vendors. Purchase invoices will be paid through our national bank account (code **ABN**) to his bank account (code **OJBA**). Both bank account ABN and OJBA are denominated in local currency (LCY). Therefore, on Olek Johansson's vendor card we leave the **Currency Code** field empty, fill the **Transaction Mode** field with **ABN** that is linked to our bank account, ABN, and set the **Bank Account** field to **OJBA**.  

## Create Vendor/Customer Bank Account  
Create vendor/customer bank account and enter all necessary information. Special attention should be paid to the following fields:  

- **Preferred Bank Account**: Enter a valid bank account number.  
- **Currency Code**: Leave empty - i.e. it is set to the local currency (LCY).  
- **Owner Information**: Be sure all owner information has been entered.  

### Example  
Olek Johansson's bank account (code **OJBA**) is denominated in local currency (LCY). Therefore, on Olek Johansson's vendor bank account card we enter a valid number in the **Bank Account No.** field, leave the **Currency Code** field empty and fill the fields on the **Owner Information** FastTab with appropriate values.  

## Create and Post Purchase Invoice for Vendor or Sales Invoice for Customer  
Create a purchase/sales invoice and enter all necessary information. Special attention should be paid to the following fields:  

- **Currency Code**: Leave empty - i.e. it is set to the local currency (LCY).  
- **Transaction Mode**: Select an appropriate, default transaction mode - i.e. one that can deal with local currency payments for your bank.  
- **Preferred Bank Account**: Select an appropriate, default vendor/customer bank account having the same Currency Code is the vendor/customer itself.  

By default these three fields will be populated with values taken from the vendor/customer card.  

When the invoice is finished it can be posted.  

### Example  
When creating a purchase invoice for Olek Johansson we enter **OLEK** in the **Buy-from Vendor No.** field. By default the **Currency Code**, **Transaction Mode** and **Bank Account** fields will be populated with values taken from the Olek Johansson's vendor card. Therefore, the **Currency Code**, **Transaction Mode** and **Bank Account** fields will be **<empty>**, **ABN** and **OJBA** respectively. Nevertheless, these values can be changed.  

## Create Proposal  
Open the **Telebank - Bank Overview** page and browse to the bank through which we want to perform our payment. Open the **Proposal** page and generate payment proposals using the **Get Proposal Entries** batch job.  

### Example  
Through the **Telebank - Bank Overview** page, we open the **Proposal** page for our bank, ABN. Using the batch job, one proposal line will be created for the purchase invoice we just created and posted for vendor OLEK.  

## Create Payment History  
From the **Proposal** page, we process our proposal into a payment history. The proposal will disappear and can be found on the **Payment History Overview** page for the same bank.  

### Example  
We process our proposal concerning the payment to vendor OLEK and open the **Payment History Overview** page for our bank, ABN. The last payment history is the one we just created.  

## Export Payment History  
Open the **Payment History Overview** page, browse to the relevant payment history and choose the **Export** action. The export batch job will appear for the export protocol that is linked to this payment. For this export the system already has entered appropriate filters. Check, if wanted, any of the fields on the **Options** FastTab, and then choose the **OK** action to export the payment. The system will generate a text file using a filename as defined in the **Default File Names Field** field of the export protocol, which now is ready to be sent to our bank.  

## Import Bank Statement  
After receiving electronic bank statements from our bank we can import them by running the appropriate import protocol from the **Import Protocol List** page.  

### Example  
The bank statement containing our payment to Olek Johansson will be sent to us by our bank, ABN. Therefore, we should chose **OFFICE NET EXTRA** as the appropriate import protocol.  

## See Also  
 [Create Proposals](how-to-create-proposals.md)   
 [Create and Export Payment History](how-to-create-and-export-payment-history.md)
