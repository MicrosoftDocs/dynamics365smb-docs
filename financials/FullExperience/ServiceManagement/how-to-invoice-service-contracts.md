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
# How to: Invoice Service Contracts
You can invoice service contracts periodically. The invoice period for each contract defines how often you invoice it.  
  
### To invoice a service contract  
  
1.  In the **Search** box, enter **Create Contract Invoices**, and then choose the related link.  
  
2.  On the **Service Contract Header** FastTab, set the filters you want to apply.  
  
3.  On the **Options** FastTab, in the **Posting Date** field, enter the date you want to use as the posting date on the service invoices.  
  
4.  In the **Invoice to Date** field, enter the date up to which you want to invoice contracts. The batch job will include the contracts with the next invoice dates, up to this date.  
  
5.  In the **Action** field, select **Create Invoices**.  
  
6.  Choose the **OK** button to create the service invoices.  
  
 You can also invoice a service contract directly from the **Service Contract** window, if the next invoice date on the contract is earlier than the working date.  
  
### To invoice a service contract from the service contract window  
  
1.  In the **Search** box, enter **Service Contracts**, and then choose the related link.  
  
2.  Select and open the service contract that you want to invoice.  
  
3.  On the **Home** tab, in the **Process** group, choose **Create Service Invoice**. A dialog box opens asking whether you want to create an invoice for the contract. Choose the **Yes** button to confirm.  
  
> [!NOTE]  
>  It is not possible to create service invoices for the service contract when the **Change Status** field value is set to **Open**.  
  
## See Also  
 [Changing the Service Contract Status](../Service/changing-the-service-contract-status.md)   
 [How to: Create Service Contracts and Service Contract Quotes](../Service/how-to-create-service-contracts-and-service-contract-quotes.md)