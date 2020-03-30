---
    title: Payment Scenario 2 - Foreign Payment (FCY to FCY)
    description: You can use telebanking for trade with domestic and foreign customers and vendors.
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
# Payment Scenario 2 - Foreign Payment (FCY to FCY)
You can use telebanking for trade with domestic and foreign customers and vendors. This topic describes a scenario where the trade is with foreign customers and vendor that use the same foreign currency as your bank account is set up to use.  

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

- **Currency Code**: Set it to the foreign currency (FCY).  
- **Transaction Mode**: Select an appropriate, default transaction mode - i.e. one that can deal with foreign currency payments for your foreign bank.  
- **Preferred Bank Account**: Select an appropriate, default vendor/customer bank account having the same Currency Code as the vendor/customer itself.  

> [!NOTE]  
>  In order to be able to enter a bank account in the **Bank Account** vendor/customer bank accounts must be available. See below.  

### Example  
Jannet Carter (code **JANNET**) is one of our US vendors. Purchase invoices will be paid through our foreign bank account (code **ABN-USD**) to her bank account (code **JCBA**). Both bank account ABN-USD and JCBA are denominated in the same foreign currency (FCY) - i.e. USD. Therefore, on Jannet Carter's vendor card, we set the **Currency Code** field to **USD**, fill the **Transaction Mode** field with **ABN-USD** that is linked to our bank account, ABN-USD and set the **Bank Account** field to **JCBA**.  

## Create Vendor/Customer Bank Account  
Create vendor/customer bank account and enter all necessary information. Special attention should be paid to the following fields:  

- **Preferred Bank Account**: Enter a valid bank account number.  
- **Currency Code**: Set it to the foreign currency (FCY).  
- **Owner Information**: Be sure all owner information has been entered.  

### Example  
Jannet Carter's bank account (code **JCBA**) is denominated in foreign currency (FCY) - i.e. USD. Therefore, on Jannet Carter's vendor bank account card, we enter a valid number in the **Bank Account No.** field, set the **Currency Code** field to **USD**, and fill the fields on the **Owner Information** tab with appropriate values.  

## Create and Post Purchase Invoice for Vendor or Sales Invoice for Customer  
Create a purchase/sales invoice and enter all necessary information. Special attention should be paid to the following fields:  

- **Currency Code**: Set it to the foreign currency (FCY).  
- **Transaction Mode**: Select an appropriate, default transaction mode - i.e. one that can deal with foreign currency payments for your foreign bank.  
- **Preferred Bank Account**: Select an appropriate, default vendor/customer bank account having the same Currency Code is the vendor/customer itself.  

By default, these three fields will be populated with values taken from the vendor/customer card.  

When the invoice is finished it can be posted.  

### Example  
When creating a purchase invoice for Jannet Carter we enter **JANNET** in the **Buy-from Vendor No.** field. By default, the **Currency Code**, **Transaction Mode**, and **Bank Account** fields will be populated with values taken from the Jannet Carter's vendor card. Therefore, the **Currency Code**, **Transaction Mode**, and **Bank Account** fields will be **USD**, **ABN-USD**, and **JCBA** respectively. Nevertheless, these values can be changed.  

## Create Proposal  
Open the **Telebank - Bank Overview** page and browse to the bank through which we want to perform our payment. Open the **Proposal** page and generate payment proposals using the **Get Proposal Entries** batch job.  

### Example  
Through the **Telebank - Bank Overview** page, we open the **Proposal** page for our bank, ABN-USD. Using the batch job, one proposal line will be created for the purchase invoice we just created and posted for the vendor JANNET.  

## Create Payment History  
From the **Proposal** page we process our proposal into a payment history. The proposal will disappear and can be found on the **Payment History Overview** page for the same bank.  

### Example  
We process our proposal concerning the payment to the vendor JANNET and open the **Payment History Overview** page for our bank, ABN-USD. The last payment history is the one we just created.  

## Export Payment History  
Open the **Payment History Overview** page, browse to the relevant payment history and choose the **Export** action. The export batch job will appear for the export protocol that is linked to this payment. For this export the system already has entered appropriate filters. Check, if wanted, any of the fields on the **Options** FastTab, and then choose the **OK** button to export the payment. The system will generate a text file using a filename as defined in the **Default File Names Field** field of the export protocol, which now is ready to be sent to our bank.  

### Example  
As the transaction mode associated with our payment is ABN-USD, the **BBV** or **PAYMUL** batch job will appear.  

## Import Bank Statement  
After receiving electronic bank statements from our bank we can import them by running the appropriate import protocol from the **Import Protocol List** page.  

### Example  
The bank statement containing our payment to Jannet Carter will be sent to us by our bank, ABN-USD. Therefore, we should chose **OFFICE NET EXTRA** as the appropriate import protocol.  

## See Also  
 [Create Proposals](how-to-create-proposals.md)   
 [Create and Export Payment History](how-to-create-and-export-payment-history.md)
