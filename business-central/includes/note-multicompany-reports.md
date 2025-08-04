---
ms.service: dynamics-365-business-central
---
> [!NOTE]
> You could get the data from various companies in a single report with OData web services. However, starting with [!INCLUDE [prod_short](prod_short.md)] 2021 release wave 2, only ODataV4 is supported. ODataV4 doesn't export data from multiple companies. The **$expand** function in Power BI that you might think would be an alternative way to create a multi-company report can't be used either. It creates a column with the company name but doesn't populate it with the company data after a refresh.