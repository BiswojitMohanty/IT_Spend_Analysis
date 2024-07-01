

Project Overview: IT Spends Data Analytics Dashboard in Power BI:

Our project aims to develop a comprehensive IT spends data analytics dashboard using Power BI. The objective is to provide organizations with a powerful tool to analyze and visualize their IT spending patterns, identify cost-saving opportunities, and optimize IT budget allocation.

The IT spends data analytics dashboard will integrate data from various sources, including financial systems, procurement records, and vendor contracts. By leveraging Power BI's robust analytics capabilities, the dashboard will offer interactive visualizations and insightful reports for effective IT spend analysis.

The dashboard will provide a detailed breakdown of IT spending across different categories, such as hardware, software, cloud services, and IT personnel. Users can analyze spending trends over time, identify cost drivers, and compare actual spending against budgeted amounts.

Additionally, the dashboard will enable users to drill down into specific cost centers or departments, allowing for granular analysis of IT spending. This will help organizations understand spending patterns within different business units and identify areas for cost optimization.

Moreover, the dashboard will incorporate vendor analysis, providing insights into spending distribution among different vendors. Users can evaluate vendor performance, negotiate better contracts, and identify opportunities for consolidation or cost reduction.

Furthermore, the dashboard will support IT cost transparency, enabling business stakeholders to understand the value and impact of IT investments. It will provide cost allocation reports, show the breakdown of IT spends by business functions, and facilitate cost benchmarking against industry standards.

Additionally, the dashboard will provide forecasting and predictive analytics capabilities, allowing organizations to project future IT spending based on historical data and trends. This will help organizations plan their IT budgets, anticipate future expenses, and align IT investments with business objectives.

The IT spends data analytics dashboard in Power BI will serve as a valuable tool for organizations to gain visibility into their IT spending, identify areas for cost optimization, and make informed decisions to maximize the value of their IT investments. By leveraging interactive visualizations and advanced analytics, the dashboard will empower organizations to optimize IT budget allocation, improve cost efficiency, and drive business growth.


Note: the date format in the source data csv files is dd/mm/yyyy. If your date format is mm/dd/yyyy please watch this tutorial on how to convert the date to your locale: https://youtu.be/QKgS3hrrmvw



Actual running total- 

Actual RT = CALCULATE(SUM(Actuals[Actual]), FILTER(ALLSELECTED(Calender[Date]),ISONORAFTER(Calender[Date], MAX(Actuals[Date]), DESC)))


OR - 

RunningTotal = 
CALCULATE(
    SUM(ITSpend[Amount]),
    FILTER(
        ALLSELECTED(DateTable),
        DateTable[Date] <= MAX(DateTable[Date])
    )
)


PS- Create date table for this if not available.

DateTable = 
CALENDAR(
    MIN(ITSpend[Date]),
    MAX(ITSpend[Date]))

