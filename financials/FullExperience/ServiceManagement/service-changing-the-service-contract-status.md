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
# Changing the Service Contract Status
After the service contract is signed, the **Change Status** field value is automatically set to **Locked**. If you want to modify information in the service contract or service contract quote, first you have to change the status of the contract or contract quote from **Locked** to **Open**. Note that you cannot create service invoices for the service contract with the **Open** change status. After the contract or contract quote is modified, you have to change the status back to **Locked** to make it possible to create service invoices and ledger entries for the service contract, which includes the changes that you made to it.  
  
> [!NOTE]  
>  The **Change Status** field is not related to the **Release Status** field on the service order header, which governs the warehouse handling of service items.  
  
## See Also  
 Service Order   
 Release Status   
 Change Status