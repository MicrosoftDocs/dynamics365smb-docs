---
title: Financial Analytics in Business Central
description: Business Central contains many features to help you gather, analyze, and share valuable company data for business intelligence and decision-making.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 103, 108, 198, 490
ms.date: 09/22/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# Financial Analytics in Business Central

Businesses capture a tremendous amount of data during daily activities. This data, which reflects such things as the organization's sales figures, purchases, operational expenses, employee salaries, and budgets, represents valuable information, or business intelligence (BI), for decision makers. [!INCLUDE[prod_short](includes/prod_short.md)] contains many features to help you gather, analyze, and share your company data:

- Financial reporting (for financial statements and KPIs)
- Ad-hoc analysis on lists
- Ad-hoc analysis of data in Excel (using open in Excel)
- Built-in finance reports

Each of these features has its own advantages and disadvantages, depending on the type of data analysis and the role of the user. In this article, we introduce these analytical features and how they can be used differently in an organization to provide financial insights.

## Analytics needs in finance

When thinking of analytics needs in finance, it might help to use a mental model based on  personas described on a high-level and their different analytics needs.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration of different personas for analytics" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

The model is based on the observation that different roles in an organization have different needs when it comes to data: the higher the role is placed in the org chart, the more data needs to be aggregated for them to do their work. 

Each of the roles has some preferred/typical ways to consume/analyze data, ways that reflect the level of data aggregation needed in their role as shown in this illustration and table.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration of how different personas have different analytics needs." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Role              | Data aggregation  | Typical ways to consume data                          | 
|-------------------|-------------------| ----------------------------------------------------- |
|CFO / CEO          | Performance data  | KPIs <br> Dashboards <br> Financial reports           |
|Finance Management | Trends, summaries | Built-in managerial reports <br> Ad-hoc analysis      | 
|Bookkeeper         | Detailed data     | Built-in operational reports <br> On-screen task data |


## Finance KPIs

Text copied from
https://powerbi.microsoft.com/en-us/kpi-dashboards/

### What is a KPI?
A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. Think of KPIs as your company’s scorecard, a way of measuring whether or not you’re delivering on your objectives.

### Why KPIs matter
Identifying and tracking KPIs lets you know if your business is on the right path—or if you should change course to avoid losing valuable time and money. When used properly, KPIs are powerful tools that help you:

- Monitor company financial health.
- Measure progress against strategic goals.
- Spot problems early on.
- Make timely adjustments to tactics.
- Motivate team members.
- Make better decisions, faster.

So how do you begin to identify the KPIs that are important to your business? Start by clarifying your strategic objectives—collectively or by department.

These goals will help you identify which KPIs matter for your company. Picking KPIs that are relevant will depend entirely on these objectives and the ability you have to measure your performance against them.

Next, identify the KPI targets that you’re working toward, and how they’ll be measured. Keep in mind that these could be both short- and long-term targets.

Talk to your team and encourage open dialogue about the KPIs and their targets. Are they too aggressive? Too easy? Targets should be challenging, but if they’re too far-fetched or rely entirely on metrics that your team doesn’t control, it would be wise to revisit. You’ll also want to explore the activities and tactics your company will use to achieve those targets. Lastly, take time to evaluate where you are today—this will be your KPI starting point.


### Get to know the different types of KPIs
Identifying which KPIs you should track becomes easier when you have a better understanding of the types of KPIs that are most commonly used to measure progress.

- Quantitative KPIs are all about measurable facts that can be represented with a number. Think stats, percentages, and dollar signs.
- Qualitative KPIs involve human interpretations and can’t be quantified with numbers. Think opinions, feelings, and experiences.
- Lagging KPIs measure what’s already happened in the past to predict success or failure. Think of looking back at what you’ve already accomplished, or where you’ve struggled.
- Leading KPIs measure performance to predict future success and long-term trends. Think of looking forward to where you’re headed.
- Leading and lagging KPIs are commonly used together. Along with quantitative and qualitative KPIs, they’re a good place to start.

For each KPI that you choose to track, assign an owner and agree on tracking frequency. Whatever KPIs you decide to track, using a KPI platform or tool is key for collaborating with your team on KPI definitions. By collectively defining each KPI, then capturing contextual data and unifying it into a single view, you enable spot-on, real-time actions.

### KPI reporting
KPI reports take the information presented on the KPI dashboard to a new level. They go deeper into the data to pull out more detailed insights and analysis.

A KPI report helps stakeholders and team members identify trends or bottlenecks over a specific time period, so that they’re able to make better decisions. Reporting topics could include:

- Insights into the company’s day-to-day operations.
- Financial health of the company against targeted KPIs.
- Notable trends or patterns presented by the data.
- Deeper analysis of the data to assist with strategic decision-making.

To create your KPI report, first determine your audience and the objective for the report. For example, you might want to show company stakeholders Q3 progress toward your revenue target. Make sure that all the KPIs featured in your report point back to that central theme.

Additional considerations for creating your KPI reports include:

- Exploring KPI report templates that may be already included in your KPI tool or platform.
- Setting a cadence for reporting frequency.
- Deciding whether your report will be static or interactive, for more dynamic drilldowns into data.
- Presenting only the relevant KPIs so you don’t overload the report with KPIs that don’t map back to the reporting - goals.
- Making sure your reporting is clear, easy to understand, and actionable for the intended audience.

KPI best practices
To help you successfully harness the power of KPIs, we’ve compiled a few tips to get you started.

Identifying KPIs:
- Only pick KPIs that are aligned to your specific goals. If your objectives aren’t clear, matching KPIs against them will prove complicated.
- Use different KPIs for the same goals if they stretch across departments—for example, the marketing department will have different KPIs than the sales team.
- Make sure that for whatever KPIs you pick, there’s a core team responsible for defining them.

Monitoring KPIs:
- Explore the different dashboards, visualization charts, and templates available in your KPI tool or platform to select the right ones for your goals.
- Make sure to include starting data for comparison, so that your dashboard shows a true representation of company performance and progress over time.
- Determine a cadence for monitoring and acting on KPIs. Are KPI dashboards monitored daily or weekly? Do actions only come after reporting or are stakeholders and/or team members empowered to adjust tactics along the way?
- Be sure you have simple, end-to-end data protection for data dashboards, with controls for sharing outside the organization.

### Common KPI mistakes

Avoid these common KPI mistakes:
- Selecting KPIs that aren’t key to your strategic goals. While it’s smart to track your relevant business metrics, not all of your metrics are worthy of KPI status.
- Adopting poorly defined or vague KPIs. Collaborate with your team to define the KPIs with specific details on how they’ll be measured. If you don’t, you’ll struggle to meet your goals.
- Setting lofty or unrealistic KPI targets. It’s better to set more realistic targets based on historical data, resources, and current tactics. Consider focusing on a specific timeframe or set short- and long-term targets.
- Tracking KPIs without owners. Accountability matters, not just for the results but also for the process. Each KPI should have an owner responsible for monitoring, reporting, analysis, and action.
- Failing to take action on your KPIs. Whether you’re meeting your goals or falling behind, KPIs are tools to help you make better decisions. So don’t track just for tracking’s sake—take action.

### Commonly used financial KPIs

#### 13 FINANCIAL PERFORMANCE MEASURES TO MONITOR
https://online.hbs.edu/blog/post/financial-performance-measures

1. Gross Profit Margin
Gross profit margin is a profitability ratio that measures what percentage of revenue is left after subtracting the cost of goods sold. The cost of goods sold refers to the direct cost of production and does not include operating expenses, interest, or taxes. In other words, gross profit margin is a measure of profitability, specifically for a product or item line, without accounting for overheads.

Gross Profit Margin = (Revenue - Cost of Sales) / Revenue * 100

2. Net Profit Margin
Net profit margin is a profitability ratio that measures what percentage of revenue and other income is left after subtracting all costs for the business, including costs of goods sold, operating expenses, interest, and taxes. Net profit margin differs from gross profit margin as a measure of profitability for the business in general, taking into account not only the cost of goods sold, but all other related expenses.

Net Profit Margin = Net Profit / Revenue * 100

3. Working Capital
Working capital is a measure of the business’s available operating liquidity, which can be used to fund day-to-day operations.

Working Capital = Current Assets - Current Liabilities

4. Current Ratio
Current ratio is a liquidity ratio that helps you understand whether the business can pay its short-term obligations—that is, obligations due within one year— with its current assets and liabilities.

Current Ratio = Current Assets / Current Liabilities5. Quick Ratio
The quick ratio, also known as an acid test ratio, is another type of liquidity ratio that measures a business’s ability to handle short-term obligations. The quick ratio uses only highly liquid current assets, such as cash, marketable securities, and accounts receivables, in its numerator. The assumption is that certain current assets, like inventory, are not necessarily easy to turn into cash.

5. Quick Ratio
The quick ratio, also known as an acid test ratio, is another type of liquidity ratio that measures a business’s ability to handle short-term obligations. The quick ratio uses only highly liquid current assets, such as cash, marketable securities, and accounts receivables, in its numerator. The assumption is that certain current assets, like inventory, are not necessarily easy to turn into cash.

Quick Ratio = (Current Assets - Inventory) / Current Liabilities

6. Leverage
Financial leverage, also known as the equity multiplier, refers to the use of debt to buy assets. If all the assets are financed by equity, the multiplier is one. As debt increases, the multiplier increases from one, demonstrating the leverage impact of the debt and, ultimately, increasing the risk of the business.

Leverage = Total Assets / Total Equity

7. Debt-to-Equity Ratio
The debt-to-equity ratio is a solvency ratio that measures how much a company finances itself using equity versus debt. This ratio provides insight into the solvency of the business by reflecting the ability of shareholder equity to cover all debt in the event of a business downturn.

Debt to Equity Ratio = Total Debt / Total Equity


8. Inventory Turnover
Inventory turnover is an efficiency ratio that measures how many times per accounting period the company sold its entire inventory. It gives insight into whether a company has excessive inventory relative to its sales levels.

Inventory Turnover = Cost of Sales / (Beginning Inventory + Ending Inventory / 2)

9. Total Asset Turnover
Total asset turnover is an efficiency ratio that measures how efficiently a company uses its assets to generate revenue. The higher the turnover ratio, the better the performance of the company.

Total Asset Turnover = Revenue / (Beginning Total Assets + Ending Total Assets / 2)

10. Return on Equity
Return on equity, more commonly displayed as ROE, is a profitability ratio measured by dividing net profit over shareholders’ equity. It indicates how well the business can utilize equity investments to earn profit for investors.

ROE = Net Profit / (Beginning Equity + Ending Equity) / 2

11. Return on Assets
Return on assets, or ROA, is another profitability ratio, similar to ROE, which is measured by dividing net profit by the company’s average assets. It’s an indicator of how well the company is managing its available resources and assets to net higher profits.

ROA = Net Profit / (Beginning Total Assets + Ending Total Assets) / 2

12. Operating Cash Flow
Operating cash flow is a measure of how much cash the business has as a result of its operations. This measure could be positive, meaning cash is available to grow operations, or negative, meaning additional financing would be required to maintain current operations. The operating cash flow is usually found on the cash flow statement and can be calculated using one of two methods: direct or indirect.

13. Seasonality
Seasonality is a measure of how the period of the year is affecting your company’s financial numbers and outcomes. If you’re in an industry that’s affected by high and low seasons, this measure will help you sort out confounding variables and see the numbers for what they truly are.


#### Borrow list and definitions from D365 Finance???
https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/analytics/financial-insights#account-categories-used-by-page-and-visual



#### text below is copied from Oracle / NetSuite

**!! All of the text below is copied from Oracle / NetSuite. Just added here as an example**

Financial key performance indicators (KPIs) are select metrics that help managers and financial specialists analyze the business and measure progress toward strategic goals. A wide variety of financial KPIs are used by different businesses to help monitor their success and drive growth. For each company, it’s essential to identify KPIs that are the most meaningful to its business.

The following overview of 30 KPIs is designed to help leaders choose the KPIs that make the most sense for their organizations in the year ahead.

##### What Are KPIs?
KPIs are metrics that provide insights into the underlying financial and operational strength of a business. They can be based on any kind of data that is important to a company, such as sales per square foot of retail space, click-through rate for web ads or accounts closed per salesperson. Many KPIs are ratios that highlight important relationships in data, such as the ratio of profit to revenue or the ratio of current assets to current liabilities. A single KPI measurement can provide a useful snapshot of the business’s health at a specific point in time.

KPIs are even more powerful when they are used to analyze trends over time, to measure progress against targets or to compare the business with other, similar companies. Their value expands further when businesses consider them alongside other meaningful KPIs to create a more complete view of the business.

##### What Is a Financial KPI?
Financial KPIs are high-level measures of profits, revenue, expenses or other financial outcomes that specifically focus on relationships derived from accounting data — and they’re almost always tied to a specific financial value or ratio. Most KPIs fall into five broad categories based on the type of information they measure:

- Profitability KPIs, such as gross profit margin and net profit margin.
- Liquidity KPIs, such as current ratio and quick ratio.
- Efficiency KPIs, such as inventory turnover and accounts receivable turnover.
- Valuation KPIs, such as earnings per share and price to earnings ratio.
- Leverage KPIs, such as debt to equity and return on equity.

##### Why Are Financial Metrics and KPIs Important to Your Business?
Like the indicators and warning lights displayed on a vehicle’s dashboard, financial KPIs enable business leaders to focus on the big picture, helping them steer the company and identify any pressing issues without getting mired in the details of what goes on under the hood. These snippets of information can show when operations are running smoothly and when there are significant changes or warning signs. KPIs can also be used to help manage the company to achieve specific goals.

##### Which KPIs Are Best?
For any business, the best KPIs help companies determine what they're doing well and where they need to improve. While the actual metrics will vary from company to company, automated KPIs are the best way to track performance. After selecting a set of KPIs that matches your business priorities, you can generally automate their calculation and have them updated in real time by integrating the company’s accounting and ERP systems. This ensures the KPIs reflect the current state of the business and are always calculated the same way.

Automating KPIs is important for companies of all sizes. It means small businesses can direct more of their resources to analyzing KPIs instead of expending effort — and money — to create them. Larger enterprises can also better manage voluminous data this way than by using error-prone spreadsheets, and they can achieve better consistency across business units.

##### Defining the Right KPIs for Your Business
Determining the most useful and meaningful KPIs for your business can be challenging. The KPIs you choose will depend on your company’s goals, business model and specific operating processes. Some KPIs are almost universally applicable, such as accounts receivable turnover and the quick ratio. Other KPIs differ by industry. For example, manufacturers must monitor the status of their inventory, while services businesses might focus on measuring revenue per employee when evaluating efficiency.

##### 30 Financial Metrics and KPIs to Measure Success in 2023
Measuring and constantly monitoring KPIs are best practices for running a successful business. The list below describes 30 of the most commonly used financial metrics and KPIs, and you can find formulas and more information on each below.

###### Gross Profit Margin:
This is an intermediate — but critical — measure of the profitability and efficiency of the company’s core business. It’s calculated as gross profit divided by net sales, and is usually expressed as a percentage. Gross profit is net sales minus cost of goods sold (COGS), which is the direct cost of producing the items sold. Calculating profit as a percentage of revenue makes it easier to analyze profitability trends over time and to compare profitability with other companies. The formula for calculating gross profit margin is:

Gross profit margin = (Net sales – COGS) / Net sales x 100%

Return on Sales (ROS)/Operating Margin:
This metric looks at how much operating profit the company generates from each dollar of sales revenue. It is calculated as operating income, or earnings before interest and taxes (EBIT), divided by net sales revenue. Operating income is the profit a company makes on sales revenue after deducting COGS and operating expenses. ROS is commonly used as a measure of how efficiently the company turns revenue into profit. The formula for return on sales is:

Return on sales = (Earnings before interest and taxes / Net sales) x 100%

###### Net Profit Margin:
This is a comprehensive measure of how much profit a company makes after accounting for all expenses. It’s calculated as net income divided by revenue. Net income is often regarded as the ultimate metric of profitability — the “bottom line” — because it’s the profit remaining after deducting all operating and non-operating costs, including taxes. Net profit margin is usually expressed as a percentage. The formula for net profit margin is:

Net profit margin = (Net income / Revenue) x 100%

###### Operating Cash Flow Ratio (OCF):
This liquidity KPI ratio measures a company’s ability to pay for short-term liabilities with cash generated from its core operations. It’s calculated by dividing operating cash flow by current liabilities. OCF is the cash generated by a company’s operating activities, while current liabilities include accounts payable and other debts that are due within a year. OCF uses information from a company’s statement of cash flows, rather than the income statement or balance sheet, which removes the impact of non-cash operating expenses. The formula for operating cash flow is:

Operating cash flow ratio = Operating cash flow / Current liabilities

###### Current Ratio:
This shows a company’s short-term liquidity. It’s the ratio of the company’s current assets to its current liabilities. Current assets are those that can be converted into cash within a year, including cash, accounts receivable and inventory. Current liabilities include all liabilities due within a year, including accounts payable. Generally, a current ratio below one may be a warning sign that the company doesn’t have enough convertible assets to meet its short-term liabilities. The current ratio formula is:

Current ratio = Current assets / Current liabilities

###### Working Capital:
This liquidity measure is often used in conjunction with other liquidity metrics, such as the current ratio. Like the current ratio, it compares the company’s current assets with its current liabilities. However, it expresses the result in dollars instead of as a ratio. Low working capital may indicate that the company will have difficulty meeting its financial obligations. Conversely, a very high amount may be a sign that it’s not using its assets optimally. The formula for working capital is:

Working capital = Current assets – Current liabilities

###### Quick Ratio/Acid Test:
The quick ratio is a liquidity risk KPI that measures the ability of a company to meet its short-term obligations by converting quick assets into cash. Quick assets are those current assets that can be converted into cash without discounting or writing down the value. In other words, quick assets are current assets – inventory. The quick ratio is also known as the acid test ratio because it’s used to measure the financial strength of a business. It reflects the organization’s ability to generate cash quickly to cover its debts if it experiences cash flow problems. Companies often aim for a quick ratio that’s greater than one. The quick ratio formula is:

Quick ratio = Quick assets / Current liabilities

###### Gross Burn Rate:
Generally used as a KPI by loss-generating startups, burn rate measures the rate at which the company uses up its available cash to cover operating expenses. The higher the burn rate, the faster the company will run out of cash unless it can attract more funding or receives additional financing. Investors often examine a company’s gross burn rate when considering whether to provide funding. The gross burn rate formula is:

Gross burn rate = Company cash / Monthly operating expenses

###### Current Accounts Receivable (AR) Ratio:
This metric reflects the extent to which the company’s customers pay invoices on time. It’s calculated as the total value of sales that are unpaid but still within the company’s billing terms in relation to the total balance of all AR. A higher ratio is generally better because it reflects fewer past-due invoices. A low ratio shows the company is having difficulty collecting money from customers and can be an indicator of potential future cash flow problems. The current AR formula is:

Current accounts receivable =
(Total accounts receivable – Past due accounts receivable) / Total accounts receivable

###### Current Accounts Payable (AP) Ratio:
This is a measure of whether the company pays its bills on time. It’s the total value of supplier payments that are not yet due divided by the total balance of all AP. A higher ratio indicates that the company is paying more of its bills on time. Spreading out payments to suppliers may ease a company’s cash flow problems, but it can also mean that suppliers are less likely to extend favorable credit terms in the future. The formula for current AP is:

Current accounts payable =
(Total accounts payable – Past due accounts receivable) / Total accounts receivable

###### Accounts Payable (AP) Turnover:
This is a liquidity measure that shows how fast a company pays its suppliers. It looks at how many times a company pays off its average AP balance in a period, typically a year. It’s a key indicator of how a company manages its cash flow. A higher ratio indicates that a company pays its bills faster. The formula for AP turnover is:

Accounts payable turnover =
Net Credit Purchases / Average accounts payable balance for period

###### Average Invoice Processing Cost:
Average invoice processing cost is an efficiency metric that estimates the average cost of paying each bill owed to suppliers. Processing costs often include labor, bank charges, systems, overhead and mailing costs. Factors such as outsourcing and the level of AP automation can influence the overall processing cost. A lower cost indicates a more efficient AP process. The formula for AP process cost is:

Average invoice processing cost =
Total accounts payable processing costs / Number of invoices processed for period

###### Days Payable Outstanding (DPO):
This is another way to calculate the speed at which a company pays for purchases obtained on vendor credit terms. This KPI converts AP turnover into a number of days. A lower value means the company is paying faster. The formula for calculating days payable outstanding is:

Days payable outstanding = (Accounts payable x 365 days) / COGS

###### Accounts Receivable (AR) Turnover: 
This measures how effectively the company collects money from customers on time. It reflects the number of times the average AR balance is converted to cash during a period, typically a year. It’s a ratio calculated by dividing net sales by the average AR balance during the period. A higher AR turnover is generally desirable. The formula for AR turnover is:

Accounts receivable turnover =
Sales on account / Average accounts receivable balance for period

###### Days Sales Outstanding (DSO):
This is another metric that companies use to measure how quickly its customers pay their bills. It is the average number of days required to collect accounts receivable payments. DSO converts the accounts receivable turnover metric into an average time in days. A lower value means your customers are paying faster. The formula for days sales outstanding is:

Days sales outstanding = 365 days / Accounts receivable turnover

###### Inventory Turnover:
This operational efficiency metric shows the number of times the average balance of inventory was sold during a period, typically a year. In general, a low inventory turnover ratio can indicate that the company is buying too much inventory or that sales are weak; a higher ratio indicates less inventory or stronger sales. An extremely high ratio could indicate that the company doesn’t have enough inventory to meet demand, limiting sales. The formula for inventory turnover is:

Inventory turnover = COGS / Average inventory balance for period

###### Days Inventory Outstanding (DIO):
This inventory management KPI provides another way to determine how quickly the company sells its inventory. It measures the average number of days required to sell an item in inventory. DIO converts the inventory turnover metric into a number of days. The formula for DIO is:

Days inventory outstanding = 365 days / Inventory turnover

###### Cash Conversion Cycle:
This calculates how long it takes a company to convert a dollar invested in inventory into cash received from customers. It takes into account both the time it takes to sell inventory and the time it takes to collect payment from customers. It’s expressed as a number of days. The formula for operating cycle is:

Operating cycle = Days inventory outstanding + Days sales outstanding

###### Budget Variance:
This compares the company’s actual performance to budgets or forecasts. Budget variance can analyze any financial metric, such as revenue, profitability or expenses. The variance can be stated in dollars or, more often, as a percentage of the budgeted amount. Budget variances can be favorable or unfavorable, with unfavorable budget variances typically shown in parentheses. A positive budget variance value is considered favorable for revenue and income accounts, but it can be unfavorable for expenses. The formula for calculating budget variance is:

Budget variance = (Actual result – Budgeted amount) / Budgeted amount x 100

###### Payroll Headcount Ratio:
This KPI is a measure of the productivity and efficiency of the HR team. It shows how many full-time employees are supported by each payroll or HR specialist. The calculation is usually based on full-time equivalent (FTE) headcounts. The formula for payroll headcount ratio is:

Payroll headcount ratio = HR headcount / Total company headcount

###### Sales Growth Rate:
One of the most critical revenue KPIs for many companies, sales growth shows the change in net sales from one period to another, expressed as a percentage. Companies often compare sales to the corresponding period during the previous year, or quarter-to-quarter changes in sales during the current year. A positive value indicates sales growth; negative values mean sales are contracting. The formula for sales growth rate is:

Sales growth rate = (Current net sales – Prior period net sales) / Prior period net sales x 100

###### Fixed Asset Turnover Ratio:
This shows a company’s ability to generate sales from its investment in fixed assets. This KPI is especially relevant to companies that make significant investments in property, plant and equipment (PPE) in order to increase output and sales. A higher ratio indicates that the company is using those fixed assets more effectively. The average fixed asset balance is calculated by dividing total sales by net of accumulated depreciation. The formula for fixed asset turnover is:

Fixed asset turnover = Total sales / Average fixed assets

###### Return on Assets (ROA):
This efficiency metric shows how well an operations management team uses its assets to generate profit. It takes into account all assets, including current assets such as accounts receivable and inventory, as well as fixed assets, such as equipment and real estate. ROA excludes interest expense, as financing decisions are typically not within operating managers’ control. The formula for return on assets is:

Return on assets = Net income / Total assets for period

###### Selling, General and Administrative (SG&A) Ratio:
This efficiency metric indicates what percentage of sales revenue is used to cover SG&A expenses. These expenses can include a broad range of operational costs, including rent, advertising and marketing, office supplies and salaries of administrative staff. Generally, the lower the SG&A ratio, the better. The formula for SG&A ratio is:

SGA = (Selling + General + Administrative expense) / Net sales revenue

###### Interest Coverage:
A long-term solvency KPI, interest coverage quantifies a company’s ability to meet contractual interest payments on debt such as loans or bonds. It measures the ratio of operating profit to interest expense; a higher ratio suggests that the company will be able to service debt more easily. The formula for interest coverage is:

Interest coverage = EBIT / Interest expense

###### Earnings Per Share (EPS):
This profitability metric estimates how much net income a public company generates per share of its stock. It’s typically measured by the quarter and by the year. Analysts, investors and potential acquirers often use EPS as a key measure of a company’s profitability and also as a way to calculate its total value. EPS can be calculated several ways, but here’s a widely used basic formula:

Earnings per share = Net income / Weighted average number of shares outstanding

Weighted average is basically the average number of shares outstanding — or available — during a given reporting period. The total number of shares can change due to stock splits, stock repurchase, etc. If EPS were based on the total share outstanding at the end of the reporting period, companies could manipulate results by repurchasing stock at the end of a quarter.

###### Debt-to-Equity Ratio:
This ratio looks at a company’s borrowing and the level of leverage. It compares the company’s debt with the total value of shareholder’s equity. The calculation includes both short-term and long-term debt. A high ratio indicates that the company is highly leveraged. This may not be a problem if the company can use the money it borrowed to generate a healthy profit and cash flow. The formula for debt-equity ratio is:

Debt-to-equity ratio = Total liabilities / Total shareholders’ equity

###### Budget Creation Cycle Time:
This efficiency metric measures how long it takes to complete the organization’s annual or periodic budgeting process. It’s usually measured from the time of establishing budget objectives to creating an approved, ready-to-use budget. This metric is usually calculated as the total number of days.

Budget creation cycle time = Date budget finalized – Date budgeting activities started

###### Line Items in Budget:
The number of line items in a budget or forecast is an indicator of the level of detail in the budget. A company can prepare its current budget by adjusting each line item in a previous budget to reflect current expectations. Budgets are often prepared at the account level or by project. They may include line items that correspond to lines in the company’s financial statements.

###### Number of Budget Iterations:
This is a measure of the accuracy and efficiency of the company’s budgeting process. It is the number of times a budget is reworked during the budget creation cycle. A highly manual process can be more error-prone, leading to a greater number of iterations before the company arrives at an accurate budget. Other reasons for an increased number of iterations include extensive internal negotiations, changes in business strategy or changes in the macro-economic climate. A high number of budget iterations can lead to delays and an increased budget cycle time, which can hinder the company’s ability to start executing toward the goals defined in the budget.

Number of budget iterations = Total amount of budget versions created

###### Measuring and Monitoring KPIs With Financial Management Software
Beyond the common financial metrics and KPIs listed above, businesses may want to track specialized KPIs that focus on their inner workings or functions, such as those related to analyzing inventory, sales, receivables, payables and human resources. Manually mapping and calculating financial KPI formulas from general ledger accounts can be a cumbersome, error-prone and time-consuming process. That’s why many businesses use software to automate these calculations and create dashboards with all these key numbers in one place.

NetSuite’s robust accounting and financial management software includes built-in real-time dashboards and KPIs tailored to different roles and functions within the organization as well as by industry. Users can easily add customized KPIs to support specific requirements or goals. All information is automatically updated as the platform processes transactions and other financial data.

Financial KPIs and metrics help business leaders, managers and staff quickly get the pulse of how their company is performing and track any important changes over time. They also help leaders develop key objectives and keep their employees focused on measurable goals. Financial software that provides automated, accurate, real-time KPIs keeps the company moving toward those goals, rather than getting lost in mounds of data and reports.

**END: copy from Netsuite***


## Finance Dashboards

TODO

## Using Financial reporting to produce financial statements and KPIs

The *Financial reporting* feature gives you insight into the financial data stored in your chart of accounts (COA). You can setup financial reports to analyze figures in general ledger (G/L) accounts, and compare general ledger entries with budget entries. The results display in charts and reports in your Role Center, such as the cash flow chart and income statement and balance sheet reports.

The **Dimensions** functionality plays an important role in business intelligence. A dimension is data that you can add to an entry as a parameter. As such, you can use it to group entries that have similar characteristics, such as customers, regions, products, and salesperson, and easily retrieve these groups for analysis. Among other purposes, you use dimensions when defining analysis views and creating financial reports. Learn more at [Work with Dimensions](finance-dimensions.md).

> [!TIP]
> As a quick way to analyze transactional data, you can filter totals in the chart of accounts and all entries in **Entries** pages by dimensions. Look for the **Set Dimension Filter** action.  

The following table describes a sequence of tasks, with links to the articles that describe them.  

| To | See |
| --- | --- |
|View actual amounts compared to budgeted amounts for all accounts and for several periods.|[Analyze Actual Amounts Versus Budgeted Amounts](bi-how-analyze-actual-versus-budget.md)|
|Create new financial reports to define financial statements for reporting or to display as charts.|[Prepare Financial Reports with Financial Data and Account Categories](bi-how-work-account-schedule.md)|
|Analyze your financial performance by setting up key performance indicators (KPIs) based on financial reports, which you then publish as web services. The published financial reports KPIs can be viewed on a web site or imported to Microsoft Excel using OData web services.|[Set Up and Publish KPI Web Services Based on Financial Reports](bi-how-to-set-up-and-publish-kpi-web-services-based-on-account-schedules.md)|
|Set up views to analyze data using dimensions.|[Analyze Data by Dimensions](bi-how-analyze-data-dimension.md)|
|Create new analysis reports for sales, purchases, and inventory, and set up analysis templates.|[Create Analysis Reports](bi-how-create-analysis-views-reports.md)|


## Finance reporting across business units or legal entities

Some organizations use [!INCLUDE [prod_short](includes/prod_short.md)] in multiple business units or legal entities. Others use [!INCLUDE [prod_short](includes/prod_short.md)] in subsidiaries that must report into parent organizations. [!INCLUDE [prod_short](includes/prod_short.md)] gives accountants tools that help them transfer general ledger entries from two or more companies (subsidiaries) into a consolidated company.  

For more information, see [Company consolidation](finance-consolidated-company-reporting.md)

## Ad-hoc analysis of finance data

Sometimes, you just need to check if the numbers add up correctly, quickly confirm or debunc a hypothosis about the business, or maybe look for anomalies in your financial data. For these ad-hoc analysis tasks, you might not have a built-in report that helps you with your questions, instead you can use these two features
- Data analysis on ledger list pages
- Open in Excel

With the *Data analysis* feature, you can open almost a list page such as General Ledger Entries, Fixed assets Ledger Entries, Check Ledger Entries, or Bank Account Ledger Entries, enter analysis mode, and then group, filter, and pivot data as you see fit, all directly in the [!INCLUDE [prod_short](includes/prod_short.md)] client. 

:::image type="content" source="media/data-analysis-gl-entries.png" alt-text="Example of how to do data analysis on the G/L entries page." lightbox="media/data-analysis-gl-entries.png":::


Similarly, using the *Open in Excel* feature, you can open a list page such as General Ledger Entries, Fixed assets Ledger Entries, Check Ledger Entries, or Bank Account Ledger Entries, optionally filter the list to a subset of the data, and then get the data in Excel. You can then do further analysis in Excel, using built-in Excel functionality such as Analyze Data, What-If Analysis, or Forecast Sheet.

:::image type="content" source="media/open-in-excel-gl-entries.png" alt-text="Example of how to do data analysis on the G/L entries data using Excel." lightbox="media/open-in-excel-gl-entries.png":::

> [!TIP]
> If your organization has configured OneDrive for system features, the Excel workbook is opened in your browser by using Excel for the web. 

For more information, see [Ad-hoc analysis on finance data](ad-hoc-analysis-finance.md).

## Built-in reports for finance

[!INCLUDE [prod_short](includes/prod_short.md)] includes several built-in reports, tracing functions, and tools to help auditors or controllers who are responsible for reporting to the finance department. 

To get an overview of available reports, you can click **All reports** on the top pane of your role centre. This takes you to the Role explorer limiting the features shown to the **Report & Analysis** option. For more information, see [Finding Reports with the Role Explorer](ui-role-explorer.md).

:::image type="content" source="media/report-explorer-finance.png" alt-text="Example of reports on the finance role centre." lightbox="media/report-explorer-finance.png":::

Built-in reports come in two flavors: one designed for print (pdf) and one designed for further consumption and analysis in Excel. For more information, see these overviews for reports that are relevant for finance
* [Built-in finance Excel reports](finance-analyze-excel.md)
* [Built-in key finance reports](finance-reports.md)
* [Built-in fixed assets reports](fa-reports.md)
* [Built-in accounts receivable reports](receivables-reports.md)
* [Built-in accounts payable reports](payables-reports.md)

<!-- TODO: add when we have that article
* [Built-in Cost Accounting reports](cost-accounting-reports.md) 
* [Built-in Cash Management reports](cost-accounting-reports.md) 
* [Built-in Tax and VAT reports](tax-and-vat-reports.md) 
-->


## On-screen finance task pages

[!INCLUDE [prod_short](includes/prod_short.md)] has a number of pages that you can use for getting finance overviews and tasks to perform within the finance area. 

### Show general ledger entries and balances from the Chart of Accounts page

The Chart of Accounts page shows all general ledger accounts with aggreated numbers on what has been posted to the. From this page, you can do things like:  

* View reports that show general ledger entries and balances.  
* See a list of posting groups for that account.
* View separate debit and credit balances for a single account.

:::image type="content" source="media/chart-of-accounts-page.png" alt-text="Example of how the Chart of Accounts page shows finance insights" lightbox="media/chart-of-accounts-page.png":::

For more information, see [Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts)

### Analyzing Cash Flow 

On the Accountant Role Center, under Finance Performance, the Cash Cycle, Cash Flow, and Income & Expense charts offer ways to analyze cash flow:
- See figures for a period by using the timeline slider.
- Filter the chart by choosing the source in the legend.
- Change the length of the period, or go to the previous or next period, by choosing options on the Finance Performance drop down.

:::image type="content" source="media/cashflow-accountant-rolecentre.png" alt-text="Example of how the cash flow visuals look on the accountant role centre" lightbox="media/cashflow-accountant-rolecentre.png":::


If you want to examine the forecast, in addition to forecast entries, you can also look at the cash flow worksheet. For example, you can see how the forecast:
- Handles confirmed sales and purchases.
- Subtracts payables and adds receivables.
- Skips duplicate sales orders and purchase orders.

For more information, see [Analyzing Cash Flow in Your Company](finance-analyze-cash-flow.md)


## See also
[Ad-hoc analysis on finance data](ad-hoc-analysis-finance.md)  
[Understand the Chart of Accounts](finance-general-ledger.md#the-chart-of-accounts)  
[Built-in finance Excel reports](finance-analyze-excel.md)  
[Built-in key finance reports](finance-reports.md)  
[Built-in fixed assets reports](fa-reports.md)  
[Built-in accounts receivable reports](receivables-reports.md)  
[Built-in accounts payable reports](payables-reports.md)  
[Finance overview](finance.md)  
[Business Intelligence and Reporting Overview](reports-bi-reporting.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
