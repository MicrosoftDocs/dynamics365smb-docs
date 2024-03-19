---
title: Financial KPIs in Business Central
description: Learn about common finance KPIs and how to implement them in Business Central.
author: kennieNP
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: bi, power BI, analysis, KPI
ms.date: 03/19/2024
ms.author: kepontop
ms.service: dynamics-365-business-central
---

# Financial KPIs in Business Central

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. Think of KPIs as your company’s scorecard, a way of measuring whether or not you’re delivering on your objectives. 

In finance, the following KPIs are commonly used for monitoring your organizations financial health:

- Gross Profit Margin
- Net Profit Margin
- Working Capital 
- Current/Quick Ratio
- Financial leverage, also known as the Equity Multiplier
- Debt-to-Equity Ratio
- Total Asset Turnover
- Return on Equity
- Return on Assets

For more information on how to use KPIs in your organization, see [Using key performance indicators (KPIs) to meet your business goals](analytics-about-kpis.md).

> [!NOTE]
> Borrow list and definitions from D365 Finance???
>
> https://learn.microsoft.com/en-us/dynamics365/fin-ops-core/dev-itpro/analytics/financial-insights#account-categories-used-by-page-and-visual

## Gross Profit Margin 

Gross Profit Margin is a financial metric that calculates the percentage of revenue remaining after deducting the cost of goods sold (COGS). COGS represents the direct expenses related to production and excludes operating costs, interest, and taxes. Essentially, gross profit margin assesses the profitability of a specific product, product line, or service without factoring in overhead expenses.

**Formula** 

Gross Profit Margin (in %) = Gross Profit / Revenue * 100% = (Revenue - Cost of Sales) / Revenue * 100%

**Implementing Gross Profit Margin**

You can very easily implement the Gross Profit Margin KPI using Financial reports. Do as follows

1. Navigate to the Financial Reporting page
1. Take a copy of the Income Statement report
1. Modify the row definition for the copied report. It already includes row calculations of Gross Profit and Revenue (might be called Income in the row definition), so you might just need to add a row that calculates the ratio. Note that you need to check if the accounts used in the row calculations of Gross Profit and Revenue match how you have setup your posting accounts.

See also Kerry Peters screenshot (when we get this IP)
https://www.kerrypeters.com/account-schedule-examples#exercise-f



## Next

> [!NOTE]
> The KPI list below was copied from https://online.hbs.edu/blog/post/financial-performance-measures
> We need to change that before we go live

2. Net Profit Margin
Net profit margin is a profitability ratio that measures what percentage of revenue and other income is left after subtracting all costs for the business, including costs of goods sold, operating expenses, interest, and taxes. Net profit margin differs from gross profit margin as a measure of profitability for the business in general, taking into account not only the cost of goods sold, but all other related expenses.

Net Profit Margin = Net Profit / Revenue * 100

3. Working Capital
Working capital is a measure of the business’s available operating liquidity, which can be used to fund day-to-day operations.

Working Capital = Current Assets - Current Liabilities

4. Current Ratio
Current ratio is a liquidity ratio that helps you understand whether the business can pay its short-term obligations—that is, obligations due within one year— with its current assets and liabilities.

Current Ratio = Current Assets / Current Liabilities 

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



## text below is copied from Oracle / NetSuite

**!! All of the text below is copied from Oracle / NetSuite. Just added here as an example**


### What Is a Financial KPI?
Financial KPIs are high-level measures of profits, revenue, expenses or other financial outcomes that specifically focus on relationships derived from accounting data — and they’re almost always tied to a specific financial value or ratio. Most KPIs fall into five broad categories based on the type of information they measure:

- Profitability KPIs, such as gross profit margin and net profit margin.
- Liquidity KPIs, such as current ratio and quick ratio.
- Efficiency KPIs, such as inventory turnover and accounts receivable turnover.
- Valuation KPIs, such as earnings per share and price to earnings ratio.
- Leverage KPIs, such as debt to equity and return on equity.

### Why Are Financial Metrics and KPIs Important to Your Business?
Like the indicators and warning lights displayed on a vehicle’s dashboard, financial KPIs enable business leaders to focus on the big picture, helping them steer the company and identify any pressing issues without getting mired in the details of what goes on under the hood. These snippets of information can show when operations are running smoothly and when there are significant changes or warning signs. KPIs can also be used to help manage the company to achieve specific goals.


### 30 Financial Metrics and KPIs to Measure Success in 2023
Measuring and constantly monitoring KPIs are best practices for running a successful business. The list below describes 30 of the most commonly used financial metrics and KPIs, and you can find formulas and more information on each below.

#### Gross Profit Margin:
This is an intermediate — but critical — measure of the profitability and efficiency of the company’s core business. It’s calculated as gross profit divided by net sales, and is usually expressed as a percentage. Gross profit is net sales minus cost of goods sold (COGS), which is the direct cost of producing the items sold. Calculating profit as a percentage of revenue makes it easier to analyze profitability trends over time and to compare profitability with other companies. The formula for calculating gross profit margin is:

Gross profit margin = (Net sales – COGS) / Net sales x 100%

Return on Sales (ROS)/Operating Margin:
This metric looks at how much operating profit the company generates from each dollar of sales revenue. It is calculated as operating income, or earnings before interest and taxes (EBIT), divided by net sales revenue. Operating income is the profit a company makes on sales revenue after deducting COGS and operating expenses. ROS is commonly used as a measure of how efficiently the company turns revenue into profit. The formula for return on sales is:

Return on sales = (Earnings before interest and taxes / Net sales) x 100%

#### Net Profit Margin:
This is a comprehensive measure of how much profit a company makes after accounting for all expenses. It’s calculated as net income divided by revenue. Net income is often regarded as the ultimate metric of profitability — the “bottom line” — because it’s the profit remaining after deducting all operating and non-operating costs, including taxes. Net profit margin is usually expressed as a percentage. The formula for net profit margin is:

Net profit margin = (Net income / Revenue) x 100%

#### Operating Cash Flow Ratio (OCF):
This liquidity KPI ratio measures a company’s ability to pay for short-term liabilities with cash generated from its core operations. It’s calculated by dividing operating cash flow by current liabilities. OCF is the cash generated by a company’s operating activities, while current liabilities include accounts payable and other debts that are due within a year. OCF uses information from a company’s statement of cash flows, rather than the income statement or balance sheet, which removes the impact of non-cash operating expenses. The formula for operating cash flow is:

Operating cash flow ratio = Operating cash flow / Current liabilities

#### Current Ratio:
This shows a company’s short-term liquidity. It’s the ratio of the company’s current assets to its current liabilities. Current assets are those that can be converted into cash within a year, including cash, accounts receivable and inventory. Current liabilities include all liabilities due within a year, including accounts payable. Generally, a current ratio below one may be a warning sign that the company doesn’t have enough convertible assets to meet its short-term liabilities. The current ratio formula is:

Current ratio = Current assets / Current liabilities

#### Working Capital:
This liquidity measure is often used in conjunction with other liquidity metrics, such as the current ratio. Like the current ratio, it compares the company’s current assets with its current liabilities. However, it expresses the result in dollars instead of as a ratio. Low working capital may indicate that the company will have difficulty meeting its financial obligations. Conversely, a very high amount may be a sign that it’s not using its assets optimally. The formula for working capital is:

Working capital = Current assets – Current liabilities

#### Quick Ratio/Acid Test:
The quick ratio is a liquidity risk KPI that measures the ability of a company to meet its short-term obligations by converting quick assets into cash. Quick assets are those current assets that can be converted into cash without discounting or writing down the value. In other words, quick assets are current assets – inventory. The quick ratio is also known as the acid test ratio because it’s used to measure the financial strength of a business. It reflects the organization’s ability to generate cash quickly to cover its debts if it experiences cash flow problems. Companies often aim for a quick ratio that’s greater than one. The quick ratio formula is:

Quick ratio = Quick assets / Current liabilities

#### Gross Burn Rate:
Generally used as a KPI by loss-generating startups, burn rate measures the rate at which the company uses up its available cash to cover operating expenses. The higher the burn rate, the faster the company will run out of cash unless it can attract more funding or receives additional financing. Investors often examine a company’s gross burn rate when considering whether to provide funding. The gross burn rate formula is:

Gross burn rate = Company cash / Monthly operating expenses

#### Current Accounts Receivable (AR) Ratio:
This metric reflects the extent to which the company’s customers pay invoices on time. It’s calculated as the total value of sales that are unpaid but still within the company’s billing terms in relation to the total balance of all AR. A higher ratio is generally better because it reflects fewer past-due invoices. A low ratio shows the company is having difficulty collecting money from customers and can be an indicator of potential future cash flow problems. The current AR formula is:

Current accounts receivable =
(Total accounts receivable – Past due accounts receivable) / Total accounts receivable

#### Current Accounts Payable (AP) Ratio:
This is a measure of whether the company pays its bills on time. It’s the total value of supplier payments that are not yet due divided by the total balance of all AP. A higher ratio indicates that the company is paying more of its bills on time. Spreading out payments to suppliers may ease a company’s cash flow problems, but it can also mean that suppliers are less likely to extend favorable credit terms in the future. The formula for current AP is:

Current accounts payable =
(Total accounts payable – Past due accounts receivable) / Total accounts receivable

#### Accounts Payable (AP) Turnover:
This is a liquidity measure that shows how fast a company pays its suppliers. It looks at how many times a company pays off its average AP balance in a period, typically a year. It’s a key indicator of how a company manages its cash flow. A higher ratio indicates that a company pays its bills faster. The formula for AP turnover is:

Accounts payable turnover =
Net Credit Purchases / Average accounts payable balance for period

#### Average Invoice Processing Cost:
Average invoice processing cost is an efficiency metric that estimates the average cost of paying each bill owed to suppliers. Processing costs often include labor, bank charges, systems, overhead and mailing costs. Factors such as outsourcing and the level of AP automation can influence the overall processing cost. A lower cost indicates a more efficient AP process. The formula for AP process cost is:

Average invoice processing cost =
Total accounts payable processing costs / Number of invoices processed for period

#### Days Payable Outstanding (DPO):
This is another way to calculate the speed at which a company pays for purchases obtained on vendor credit terms. This KPI converts AP turnover into a number of days. A lower value means the company is paying faster. The formula for calculating days payable outstanding is:

Days payable outstanding = (Accounts payable x 365 days) / COGS

#### Accounts Receivable (AR) Turnover: 
This measures how effectively the company collects money from customers on time. It reflects the number of times the average AR balance is converted to cash during a period, typically a year. It’s a ratio calculated by dividing net sales by the average AR balance during the period. A higher AR turnover is generally desirable. The formula for AR turnover is:

Accounts receivable turnover =
Sales on account / Average accounts receivable balance for period

#### Days Sales Outstanding (DSO):
This is another metric that companies use to measure how quickly its customers pay their bills. It is the average number of days required to collect accounts receivable payments. DSO converts the accounts receivable turnover metric into an average time in days. A lower value means your customers are paying faster. The formula for days sales outstanding is:

Days sales outstanding = 365 days / Accounts receivable turnover

#### Inventory Turnover:
This operational efficiency metric shows the number of times the average balance of inventory was sold during a period, typically a year. In general, a low inventory turnover ratio can indicate that the company is buying too much inventory or that sales are weak; a higher ratio indicates less inventory or stronger sales. An extremely high ratio could indicate that the company doesn’t have enough inventory to meet demand, limiting sales. The formula for inventory turnover is:

Inventory turnover = COGS / Average inventory balance for period

#### Days Inventory Outstanding (DIO):
This inventory management KPI provides another way to determine how quickly the company sells its inventory. It measures the average number of days required to sell an item in inventory. DIO converts the inventory turnover metric into a number of days. The formula for DIO is:

Days inventory outstanding = 365 days / Inventory turnover

#### Cash Conversion Cycle:
This calculates how long it takes a company to convert a dollar invested in inventory into cash received from customers. It takes into account both the time it takes to sell inventory and the time it takes to collect payment from customers. It’s expressed as a number of days. The formula for operating cycle is:

Operating cycle = Days inventory outstanding + Days sales outstanding

#### Budget Variance:
This compares the company’s actual performance to budgets or forecasts. Budget variance can analyze any financial metric, such as revenue, profitability or expenses. The variance can be stated in dollars or, more often, as a percentage of the budgeted amount. Budget variances can be favorable or unfavorable, with unfavorable budget variances typically shown in parentheses. A positive budget variance value is considered favorable for revenue and income accounts, but it can be unfavorable for expenses. The formula for calculating budget variance is:

Budget variance = (Actual result – Budgeted amount) / Budgeted amount x 100

#### Payroll Headcount Ratio:
This KPI is a measure of the productivity and efficiency of the HR team. It shows how many full-time employees are supported by each payroll or HR specialist. The calculation is usually based on full-time equivalent (FTE) headcounts. The formula for payroll headcount ratio is:

Payroll headcount ratio = HR headcount / Total company headcount

#### Sales Growth Rate:
One of the most critical revenue KPIs for many companies, sales growth shows the change in net sales from one period to another, expressed as a percentage. Companies often compare sales to the corresponding period during the previous year, or quarter-to-quarter changes in sales during the current year. A positive value indicates sales growth; negative values mean sales are contracting. The formula for sales growth rate is:

Sales growth rate = (Current net sales – Prior period net sales) / Prior period net sales x 100

#### Fixed Asset Turnover Ratio:
This shows a company’s ability to generate sales from its investment in fixed assets. This KPI is especially relevant to companies that make significant investments in property, plant and equipment (PPE) in order to increase output and sales. A higher ratio indicates that the company is using those fixed assets more effectively. The average fixed asset balance is calculated by dividing total sales by net of accumulated depreciation. The formula for fixed asset turnover is:

Fixed asset turnover = Total sales / Average fixed assets

#### Return on Assets (ROA):
This efficiency metric shows how well an operations management team uses its assets to generate profit. It takes into account all assets, including current assets such as accounts receivable and inventory, as well as fixed assets, such as equipment and real estate. ROA excludes interest expense, as financing decisions are typically not within operating managers’ control. The formula for return on assets is:

Return on assets = Net income / Total assets for period

#### Selling, General and Administrative (SG&A) Ratio:
This efficiency metric indicates what percentage of sales revenue is used to cover SG&A expenses. These expenses can include a broad range of operational costs, including rent, advertising and marketing, office supplies and salaries of administrative staff. Generally, the lower the SG&A ratio, the better. The formula for SG&A ratio is:

SGA = (Selling + General + Administrative expense) / Net sales revenue

#### Interest Coverage:
A long-term solvency KPI, interest coverage quantifies a company’s ability to meet contractual interest payments on debt such as loans or bonds. It measures the ratio of operating profit to interest expense; a higher ratio suggests that the company will be able to service debt more easily. The formula for interest coverage is:

Interest coverage = EBIT / Interest expense

#### Earnings Per Share (EPS):
This profitability metric estimates how much net income a public company generates per share of its stock. It’s typically measured by the quarter and by the year. Analysts, investors and potential acquirers often use EPS as a key measure of a company’s profitability and also as a way to calculate its total value. EPS can be calculated several ways, but here’s a widely used basic formula:

Earnings per share = Net income / Weighted average number of shares outstanding

Weighted average is basically the average number of shares outstanding — or available — during a given reporting period. The total number of shares can change due to stock splits, stock repurchase, etc. If EPS were based on the total share outstanding at the end of the reporting period, companies could manipulate results by repurchasing stock at the end of a quarter.

#### Debt-to-Equity Ratio:
This ratio looks at a company’s borrowing and the level of leverage. It compares the company’s debt with the total value of shareholder’s equity. The calculation includes both short-term and long-term debt. A high ratio indicates that the company is highly leveraged. This may not be a problem if the company can use the money it borrowed to generate a healthy profit and cash flow. The formula for debt-equity ratio is:

Debt-to-equity ratio = Total liabilities / Total shareholders’ equity

#### Budget Creation Cycle Time:
This efficiency metric measures how long it takes to complete the organization’s annual or periodic budgeting process. It’s usually measured from the time of establishing budget objectives to creating an approved, ready-to-use budget. This metric is usually calculated as the total number of days.

Budget creation cycle time = Date budget finalized – Date budgeting activities started

#### Line Items in Budget:
The number of line items in a budget or forecast is an indicator of the level of detail in the budget. A company can prepare its current budget by adjusting each line item in a previous budget to reflect current expectations. Budgets are often prepared at the account level or by project. They may include line items that correspond to lines in the company’s financial statements.

#### Number of Budget Iterations:
This is a measure of the accuracy and efficiency of the company’s budgeting process. It is the number of times a budget is reworked during the budget creation cycle. A highly manual process can be more error-prone, leading to a greater number of iterations before the company arrives at an accurate budget. Other reasons for an increased number of iterations include extensive internal negotiations, changes in business strategy or changes in the macro-economic climate. A high number of budget iterations can lead to delays and an increased budget cycle time, which can hinder the company’s ability to start executing toward the goals defined in the budget.

Number of budget iterations = Total amount of budget versions created

**END: copy from Netsuite**



## See also

[Financial Analytics in Business Central](bi.md)  
[Using key performance indicators (KPIs) to meet your business goals](analytics-about-kpis.md)
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
