---
title: Set up project resource costs, prices, and capacity
description: To use resources and facilitate project management, you specify costs and prices for individual resources or resource groups, and set the resource capacity.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: project management, capacity, staff
ms.search.form: 72, 76, 77, 203, 204
ms.date: 03/17/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Set up resources for projects

To correctly manage resource activities, you must set up your resources and the related costs and prices. The project-related prices, discounts, and cost factor rules are set up on the project card. You can specify the costs and prices for individual resources, resource groups, or all available resources of the company.

You specify the default amount per hour when you set up a resource. The price and cost amounts apply when you use or sell resources in a project. For example, if you use a specific machine for five hours, the calculation is based on the amount per hour.

> [!NOTE]
> You can't purchase external resources for a specific project. We recommend that you use items of the type Service instead.

## To set up a resource

Create a card for each resource that you want to use in projects.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To set up a resource group

You can combine several resources in one resource group. All capacities and budgets of resource groups are accumulated from the individual resources. You can also enter capacities for resource groups either independently of the accumulated values or in addition to them.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resource groups**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary.

## To set capacity for a resource

To calculate how much time a resource can spend on projects, you must set their capacity. Capacity represents a resource's available time for a period on the work calendar. This setup is used when you fill in project planning lines that contain the resource. For more information, see [Create Projects](projects-how-create-jobs.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources**, and then choose the related link.
2. Open the relevant resource card, and then choose the **Resource Capacity** action.
3. On the **Resource Capacity** page, in the **View By** field, specify the length of the period, such as **Day**, that is shown on columns on the **Resource Capacity Matrix** FastTab.
4. For each resource on a line, specify for each period on the columns the number of hours that the resource is available.
5. Alternatively, to detail the resource's capacity for a specific period, choose the **Set Capacity** action.

   > [!TIP]
   > If you're setting capacity for a group of people who typically work the same hours, you can save a little time and ensure consistency by choosing a work hour template. For example, you might have one work hour template for full time technicians, and another for technicians that work part time. To learn more about work hour templates, go to [To set up work hour templates](service-how-setup-work-service-hours.md#to-set-up-work-hour-templates).

6. On the **Resource Capacity Settings** page, fill in the fields as necessary.
7. Choose the **Update Capacity** action. The **Resource Capacity** page is updated with the entered capacity.
8. Close the page.

## To set up alternate resource costs

In addition to the cost specified on the resource card, you can set up alternate costs for each resource. For example, if you pay an employee a higher hourly rate for overtime, you can set up a resource cost for the overtime rate. The alternate cost that you set up for the resource overrides the cost on the resource card when you use the resource in the resource journal.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources**, and then choose the related link.  
2. Select the resource for that you want to set up one or more alternate costs for, and then choose the **Costs** action.  
3. On the **Resource Costs** page, fill in the fields on a line as necessary.  
4. Repeat step 3 for each alternate resource cost that you want to set up.

> [!NOTE]
> To set up resource costs that apply to all resources and resource groups, open the **Resource Costs** page and fill in the fields.

## To set up alternate resource prices

In addition to price specified on the resource card, you can set up alternate prices for each resource. These alternate prices can be conditional. They can depend on whether the resource is used with a specific project or work type.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources**, and then choose the related link.
2. Select the resource for that you want to set up one or more alternate prices for, and then choose the **Prices** action.
3. On the **Resource Prices** page, fill in the fields on a line as necessary.
4. Repeat step 3 for each alternate resource price that you want to set up.

## To adjust resource prices

If you want to change costs or prices for a large number of resources, you can use a batch job.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Adjust Resource Costs/Prices**, and then choose the related link.
2. Fill in the fields on a line as necessary, and then choose the **OK** button.

> [!NOTE]  
> This batch job doesn't create or adjust alternate costs or prices for resources. It only changes the contents of the field on the resource card for the **Adjust Field** field that you selected in the batch job. The adjustment takes effect immediately for resources, so check your adjustment factors before you run the batch job.

## To get resource price change suggestions based on existing alternate prices

If you already set up alternate resource prices for some resources, you can use a batch job to set up multiple alternate resource prices.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resource Price Changes**, and then choose the related link.
2. Choose the **Suggest Res. Price Chg. (Price)** action, and then fill in the fields as necessary.
3. Choose the **OK** button.  
4. When the batch job is finished, the **Resource Price Changes** page shows the results of the batch job.

## To get resource price change suggestions based on standard prices

If you want to set up multiple alternate resource prices based on the standard prices on the resource cards, you can use a batch job.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resource Price Changes**, and then choose the related link.
2. Choose the **Suggest Res. Price Chg. (Res.)** action, and then fill in the fields as necessary.  
3. Choose the **OK** button.  
4. When the batch job is finished, open the **Resource Price Changes** page to see the results of the batch job.

### Allow multiple people to post resource transactions at the same time

To allow people to post transactions for resources at the same time, enable the **Enable multiple users to post resource ledger entries at the same time** feature update on the **Feature Management** page. By default, the feature isn’t enabled.

> [!NOTE]
> Similar features are available for project, inventory, and warehouse entries. To learn more, go to:
>
> * [Allow multiple people to post project transactions at the same time](projects-how-setup-jobs.md#allow-multiple-people-to-post-project-transactions-at-the-same-time)
> * [Allow workers to post inventory transactions at the same time](inventory-how-setup-general.md#allow-workers-to-post-transactions-at-the-same-time)
> * [Design details: Creating warehouse entries](design-details-warehouse-entries.md)

If you enable the feature, [!INCLUDE [prod_short](includes/prod_short.md)] assigns entry numbers for each table from `SequenceNumbers` in the database, which allows people to post transactions at the same time. The result can be that sometimes entries from two or more transactions are interleaved.

There's a similar feature for inventory transactions. An item register might contain any or all of the entry tables, as shown in the following image.

:::image type="content" source="media/interleaved inventory tables.png" alt-text="Screenshot that shows the item register with several entry tables." lightbox="media/interleaved inventory tables.png":::

If you don’t enable the feature, when someone posts a transaction the tables are locked and other users can’t post. [!INCLUDE [prod_short](includes/prod_short.md)] finds the last entry in each table and assigns a number that’s one higher. This numbering ensures that entries that belong to the same register are consecutive, but prevents other people from posting at the same time.

> [!NOTE]
> You might not want to enable the feature if you have a feature or extension that:
>
> * Relies on consecutive entry numbers.
> * Requires that tables are locked throughout the posting process.

## Related information

[Setting Up Project Management](projects-setup-projects.md)  
[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
