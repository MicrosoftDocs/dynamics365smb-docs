---
    title: How to Work with Service Contracts and Service Contract Quotes | Microsoft Docs
    description: You can create a service contract either manually or from a service contract quote. You can create a contract based on a service contract quote.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Work with Service Contracts and Service Contract Quotes
You can create a service contract either manually or from a service contract quote. You can use a service contract quote as a forerunner of a service contract, in which your company makes an offer to the customer and obtains customer approval before you can convert it to a service contract. The procedures for creating either a service contract or service contract quote are similar.  

## To create a service contract or service contract quote  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contracts** or **Service Contract Quotes**,and then choose the related link.  
2. Create a new service contract or service contract quote.  
3. Fill in the **No.** field. A dialog box opens, asking whether you want to fill it with the common data from a contract template. If you want to create such a service contract or service contract quote, choose the **Yes** button. The **Service Contract Template List** page opens.  
4. Select the appropriate template, and then choose **OK** to use it to create the service contract or service contract quote.  
5. In the **Customer No.** field, choose the customer.  
6. If you do not want an annual amount difference to be distributed automatically, choose the **Allow Unbalanced Amounts** check box. The values in the **Annual Amount** and **Calcd. Annual Amount** fields are not automatically equalized. If you want application to do automatically distribute any annual amount difference that might occur from a change in the service contract, leave the **Allow Unbalanced Amounts** check box clear.  
7. Add contract lines to the service contract or service contract quote.  
8. Fill in the rest of the fields as necessary.  

## To convert a service contract quote to service contract  
When a customer has accepted a service contract quote, you convert it to a service contract. At the same time, you can create a service invoice for the starting period of the contract if the starting date of the contract is before the beginning of the next invoice period.

After you complete the following steps, a service contract is created with the status **Signed**. If a service invoice is created for the starting period of the contract, the invoiced amount is calculated in the following way, depending on whether the contract is detailed or not.  

For detailed contracts, the invoiced amount is calculated as follows:  

* Invoiced amount = sum of the invoiced amount for each contract line.  
* Invoiced amount for each contract line = ((quote value ÷ 12) × number of months in the starting period) + ((quote value ÷ number of days in the year) × number of days left in the starting period).  
* If the contract line expires before the starting period ends, the expiration date becomes the ending date of the starting period for the line.  

For contracts that are not detailed, the invoiced amount is calculated as follows:  

* Invoiced amount = (annual amount ÷ number of days in the year) × number of days in the starting period.  
* If the contract expires before the starting period ends, the expiration date becomes the ending date of the starting period.    

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contract Quotes**, and then choose the related link.  
2. Open the service contract quote you want to convert to a service contract.  
3. Choose the **Make Contract** action.  
4. If the starting date of the contract is before the beginning of the next invoice period, you are asked if you want to create an invoice for the starting period of the contract. Choose **Yes**.  

 The service invoice is posted to the service account of the contract, even if the contract is prepaid.

## To create contract service credit memos
You can use a contract service credit memo when a customer cancels a prepaid service contract or removes a service item from a prepaid contract. You can also use it to correct an erroneous service invoice.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Credit Memos**, and then choose the related link.  
2. Create a new service credit memo.  
3. Fill in the **No.** field.  
4. In the **Customer No.** field, enter the number of the customer in the service contract.  

     The **Invoicing** FastTab shows information copied from the **Customer** card. If you want to post the credit memo to a different customer than the one specified on the **General** FastTab, enter the number of that customer in the **Bill-to Customer No.** field.  

    > [!NOTE]  
    >  You can compare the credit memo to the original posted document on the **Posted Service Invoices** page. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Service Invoices**, and then choose the related link.  

5. Fill in the **Posting Date** and **Document Date** fields.  
6. On the credit memo lines, enter information about the items that have been returned or removed, or the allowance that will be sent. You can also use the **Get Prepaid Contract Entries** batch job.  

 To automatically create a credit memo when contract lines are removed from a service contract, on the **Service Contract** page, on the **Invoice Details** FastTab, select the **Automatic Credit Memos** check box.  

 To manually create a credit memo when contract lines are removed from a service contract, on the **Service Contract** page, choose the **Credit Memo** action.  

## Updating and evaluating contracts
Sometimes you have to change the terms of a contract after it has been created. In most cases, you open the relevant contract on the **Service Contract** page, and change it as necessary.  

You can change the status of the contract, initially set to **Locked**, add and remove contract lines, and cancel a contract. If you want to see how your business is doing as measured by gain and loss, you can do quick business analysis using the contract trendscape feature.

## To add a contract line to a service contract or contract quote  
When a customer purchases a new item and wants to include it in the existing service contract or contract quote, you can register the item as a service item and then add it as a new contract line to the contract or contract quote.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contracts**, and then choose the related link.  
2. Open the relevant service contract or service contract quote that you want to add a new contract line for.  
3. Choose the **Open Contract** action to open the service contract or service contract quote for editing.  
4. On the **Invoice Details** FastTab, select the **Allow Unbalanced Amounts** field if you want to change the annual amount and distribute the annual amount difference manually on the contract lines. Otherwise, clear the check box in the **Allow Unbalanced Amounts** field. This will distribute the annual amount difference automatically on the contract lines after you change the annual amount.  
5. On the **Lines** FastTab, add a service item or item, or text description, on each contract line. Alternatively, you can add contract quote lines. Note that you can create multiple contracts per service item to have it included in different service contracts or contract quotes at the same time.  
6. Verify and correct the numbers in the **Line Discount %**, **Line Discount Amount**, **Response Time**, **Service Period**, and other fields as needed.

## To remove contract lines  
You may need to remove contract lines from the service contract as you remove corresponding service items from the service contract. Usually you remove a contract line that is expired or corresponds to the service item that has broken down.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contracts**, and then choose the related link.  
2. Open the service contract from which you want to remove contract lines.  
3. Choose the **Open Contract** action to open the service contract for editing.  
4. Choose the contract line you want to remove. Fill in the **Contract Expiration Date** field with the date as of which you want to remove the line. For example, you could enter the date when the service item broke down.  
5. Choose the **Remove Contract Lines** action. The **Remove Lines from Contract** page opens.  
6. Fill in the default filters: **Contract No.**, **Service Item No.**, and **Contract Type**. If needed, you can apply more filters or change the existing ones.  
7. Fill in the fields on the **Options** FastTab, and then choose the **Delete Lines** action.  

> [!NOTE]  
>  If the contract is not detailed, you must update the value in the **Annual Amount** field on the **Invoice Details** FastTab on the **Service Contract** page, reflecting the loss of the service item from the contract.  
>   
>  If the contract is detailed and prepaid, and you have posted invoices for the contract, you can create a credit memo for the contract. Choose the **Create Credit Memo** action. This is unnecessary if the check box in the **Automatic Credit Memos** field on the **Invoice Details** FastTab is selected. In that case, a credit memo is created automatically when you remove a contract line.

## Service Line Cost and Value
On a service contract lines, the amounts in the **Line Cost** and **Line Value** are calculated as described in the following tables.

| Line Cost Options | Description|
|----------------------------------|---------------------------------------|  
|**Service item** | The cost is automatically retrieved from the **Default Contract Cost** field in the **Service Item** table and copied into the **Line Cost** field. The following formula is used to calculate the line cost:<br /><br /> Sales Unit Cost × Contract Value % ÷ 100|  
|**Item** | The cost is automatically retrieved from the **Unit Cost** field in the **Item** table and the **Contract Value %** field value in the **Service Mgt. Setup** table. The following formula is used to calculate the line cost:<br /><br /> Unit Cost × Contract Value % ÷ 100|  
|**Text description** | The value in the **Line Cost** field is set to zero.|  

| Line Value Options | Description|
|----------------------------------|---------------------------------------|  
|**Service item** | The price is automatically retrieved from the **Default Contract Value** field in the **Service Item** table and copied into the **Line Value** field.|  
|**Item** | Depending on the value in the **Contract Value Calc. Method** field in the **Service Mgt. Setup** table, the amount is retrieved from either the **Unit Price** or the **Unit Cost** field in the **Item** table. After that, this value is multiplied by the contents of the **Contract Value %** field in the **Service Mgt. Setup** table and divided by 100. This amount is copied into the **Line Value** field.<br /><br /> **NOTE:** If the **Contract Value Calc. Method** field is set to **None**, the contents of the **Line Value** field are not calculated.|  
|**Text description** | The contents of the **Line Value** field are set to zero.|  

## To add a contract discount to service contract quotes  
You can add contract discounts on services for contract quotes and service contracts. The discounts can be on spare parts in particular service item groups, on resource hours for resources in particular resource groups, and on particular service costs.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contract Quotes**, and choose the related link.  
2. Choose the quote to add discounts for.  
3. Choose the **Service Discounts** action. The **Contract/Service Discounts** page opens.  
4. To create a new contract discount, choose the **New** action.  
5. Fill in the fields on the line as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].  

> [!Tip]  
>  To add contract discounts directly to a service contract, perform similar steps from the **Service Contract** page.  

## To change the owner of a service contract  
You may need to change the owner of a service contract. If a service item in a service contract is registered in noncanceled multiple contracts owned by the same customer, then the owner of all service contracts that include this service item and of all other service items included in these contracts is updated automatically.  

> [!NOTE]  
>  In this case, only noncanceled contracts are considered. The status of the contract quotes is not taken into account.  

> [!IMPORTANT]  
>  Service items and contracts can be related. Changing the owner of a service contract can affect these relationships.  
>   
>  For example, suppose service item No. 8 is included in contracts SC00003 and SC00015. Contract SC00015 also contains service item No. 15, which is also included in the contract SC00080. In this case, the owner for all three contracts and service items will be changed.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contracts**, and then choose the related link. Open the relevant service contract whose owner you want to change.  
2. Choose the **Open Contract** action to open the contract for editing.  
3. Choose the **Change Customer** action. The **Change Customer in Contract** page opens.  
4. In the **Contract No.** and **Service Item No**. fields you can see the numbers of the contract and service item owned by the selected customer. If the customer owns more than one contract with more than one service item included, then the value of these fields will be **Multiple**. To see the list of related contracts or service items, select these field values.  
5. In the **New Customer No.** field, choose the new customer.  
6. In the **New Ship-to Code** field, choose the address.  
7. Choose the **OK** button to change the customer and ship-to code of the service contracts.  
8. Choose the **Lock Contract** action to lock the contract and to make sure that the changes will be part of the contracts.  

## To update a service contract price  
You can update the prices on service contracts by specifying a price update percentage.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Update Service Contract Prices**, and then choose the related link.
2. Choose the service contract.  
3. In the **Update to Date** field, enter a date. The batch job will update prices for contracts with next price update dates on or before this date.  
4. In the **Price Update %** field, enter the percentage that you want to update the prices by.  
5. In the **Action** field, select **Update Contract Prices**.  

## To post prepaid contract entries  
If you work with prepaid service contracts, you must regularly post prepaid contract entries, thereby transferring the prepaid payments from the prepaid contract accounts to the regular contract accounts.  

Before you can post prepaid contract entries, you must specify a number series in the **Prepaid Posting Document Nos.** field on the **Service Mgt. Setup** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Post Prepaid Contract Entries**, and then choose the related link.  
2. In the **Post until Date** field, enter a date. The batch job posts prepaid service ledger entries with posting dates up to this date.  
4. In the **Posting Date** field, enter the date you want to use as the posting date on the general journal line.  
5. In the **Action** field, choose **Post Prepaid Transactions**.  
6. Choose **OK** to post the entries.

## Changing the Service Contract Status
After the service contract is signed, the **Change Status** field value is automatically set to **Locked**. If you want to modify information in the service contract or service contract quote, first you have to change the status of the contract or contract quote from **Locked** to **Open**. Note that you cannot create service invoices for the service contract with the **Open** change status. After the contract or contract quote is modified, you have to change the status back to **Locked** to make it possible to create service invoices and ledger entries for the service contract, which includes the changes that you made to it.  

> [!NOTE]  
>  The **Change Status** field is not related to the **Release Status** field on the service order header, which governs the warehouse handling of service items.  

## To cancel a service contract  
You may need to cancel a service contract when the contract has expired or has been canceled by you or the customer.  

> [!NOTE]  
>  You cannot reopen a contract after it is canceled.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contracts**, and then choose the related link.  
2. Open the relevant service contract to cancel.  
3. Choose the **Open Contract** action to open the service contract for editing.  
4. In the **Cancel Reason Code** field, choose the relevant reason code. To add more reason codes, choose the **Advanced** action.  

     If the check box in the **Use Contract Cancel Reason** field on the **Service Mgt. Setup** page is selected, you must specify a cancel reason code when canceling contracts.  

5. In the **Status** field, choose **Canceled**.  
6. If there are unposted invoices, credit memos, or opened prepaid entries for the contract, a confirmation message will appear. In the message box, choose **No** to return to the contract and post the documents, or **Yes** to continue the cancellation process.  

## Filing a service contract or contract quote  
You can file service contracts and contract quotes at any time to record and archive a copy of the contract or contract quote. [!INCLUDE[d365fin](includes/d365fin_md.md)] files service contracts automatically when you convert contract quotes to service contracts or cancel service contracts. You can file a contract or quote yourself by choosing the **File Contract** action in the **Service Contracts** or **Service Contract Quotes** pages. If you want to view your archived contracts of quotes by searching for **Filed Contracts**.

## See Also  
[Set Up Service Contracts](service-how-setup-service-contracts.md)  
[Service Management](service-service.md)  
[Convert Service Contracts that Include VAT Amounts](service-how-to-convert-service-contracts.md)  
