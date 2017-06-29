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
# How to: Change the Owner of Service Contracts
You may need to change the owner of a service contract. If a service item in a service contract is registered in noncanceled multiple contracts owned by the same customer, then the owner of all service contracts that include this service item and of all other service items included in these contracts is updated automatically.  
  
> [!NOTE]  
>  In this case, only noncanceled contracts are considered. The status of the contract quotes is not taken into account.  
  
> [!IMPORTANT]  
>  Many service items and contracts can be interrelated. These interrelationships can be affected when you change the ownership of a service contract.  
>   
>  For example, suppose service item No. 8 is included in contracts SC00003 and SC00015. Contract SC00015 also contains service item No. 15, which is also included in the contract SC00080. In this case, the owner for all three contracts and service items will be changed.  
  
### To change the owner of a service contract  
  
1.  In the **Search** box, enter **Service Contracts**, and then choose the related link. Open the relevant service contract whose owner you want to change.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Open Contract** to open the contract for editing.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Change Customer**. The **Change Customer in Contract** window opens.  
  
4.  In the **Contract No.** and **Service Item No**. fields you can see the numbers of the contract and service item owned by the selected customer. If the customer owns more than one contract with more than one service item included, then the value of these fields will be **Multiple**. To see the list of related contracts or service items, select these field values.  
  
5.  In the **New Customer No.** field, select the new customer, and then choose the **OK** button to copy it to the field.  
  
6.  In the **New Ship\-to Code** field, select the address, and then choose the **OK** button to copy it to the field.  
  
7.  Choose the **OK** button to change the customer and ship\-to code of the service contracts.  
  
8.  On the **Actions** tab, in the **Functions** group, choose **Lock Contract** to lock the contract and to make sure that the changes will be part of the contracts.  
  
 The new owner is assigned to all service contracts that include the same service items as this contract and to all other service items included in these contracts.