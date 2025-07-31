# Financial Performance Dashboard - Power BI Analysis

## Project Overview
This Power BI dashboard analyzes financial performance using the "Financial Sample.xlsx" dataset, which includes sales, profit, units sold, discounts, and other metrics across customer segments, products, countries, and time periods (2013-2014). The dashboard is designed to provide actionable insights for business stakeholders to optimize sales strategies, improve profitability, and identify growth opportunities.

The project consists of five key pages:
1. **Overview Page**: High-level snapshot of sales, profit, and units sold by segment, product, and country.
2. **Trends Page**: Time-based analysis of sales, profit, and units sold to identify seasonal patterns and growth trends.
3. **Discount Impact Page**: Evaluation of how discounts affect sales volume and profitability.
4. **Product Analysis Page**: Comparison of product performance (Carretera, Montana, Paseo, Velo, VTT, Amarilla) to inform product strategy.
5. **Regional Analysis Page**: Geographic analysis of performance across countries (Canada, Germany, France, Mexico, United States).

## Dataset
The "Financial Sample.xlsx" dataset contains the following key fields:
- **Segment**: Customer segments (Government, Midmarket, Channel Partners, Enterprise, Small Business).
- **Country**: Sales regions (Canada, Germany, France, Mexico, United States).
- **Product**: Products sold (Carretera, Montana, Paseo, Velo, VTT, Amarilla).
- **Discount Band**: Discount levels (None, Low, Medium, High).
- **Units Sold, Sales, Profit, Discounts, COGS**: Key financial metrics.
- **Date, Month, Year**: Time dimensions for trend analysis.

Estimated total sales are ~$10M, with data spanning 2013-2014.

## Key Features
- **Interactive Visuals**: Includes bar charts, line charts, maps, treemaps, pie charts, and tables with slicers for Segment, Country, Product, Discount Band, and Year.
- **DAX Measures**: Custom measures for Total Sales, Total Profit, Average Profit Margin, Sales Contribution %, and more.
- **Cross-Filtering and Drill-Down**: Enables dynamic exploration of data across dimensions.
- **Conditional Formatting**: Highlights key metrics (e.g., negative profits in red, high margins in green).
- **Time Intelligence**: Analyzes year-over-year growth and seasonal trends using a custom Date Table.

## Key Insights
- **Revenue Drivers**: Government and Small Business segments, along with Paseo and Carretera products, drive the majority of sales, particularly in the United States and Canada (e.g., USA: $922,680 for Paseo; Canada: $978,236 for Carretera).
- **Profitability Challenges**: High discounts in Mexico (e.g., $149,677.5 for Paseo) and Small Business segments, and negative profits in Enterprise (e.g., -$11,115 in France), highlight areas for optimization.
- **Seasonal Trends**: Sales peak in June and December 2014, with Paseo and Amarilla showing strong seasonal performance.
- **Product Strategy**: Paseo and Carretera are top performers, while Velo and VTT underperform, suggesting reevaluation.
- **Regional Opportunities**: United States and Canada dominate sales (~50-60% combined contribution), while Mexico’s high discounts and France/Germany’s low profitability need targeted strategies.

## Recommendations
- **Optimize Discounts**: Reduce high discounts in Mexico and Small Business segments to improve profit margins without sacrificing volume.
- **Focus on High Performers**: Prioritize marketing and inventory for Paseo and Carretera, especially in the United States and Canada.
- **Address Underperformers**: Evaluate Velo and VTT for repositioning or discontinuation due to low sales and profitability.
- **Regional Strategies**: Target France and Germany with lower discounts and focus on high-margin segments like Government.
- **Seasonal Planning**: Capitalize on June and December peaks with targeted campaigns for Paseo and Amarilla.

## Project Structure
- **Financial Sample.xlsx**: Source dataset used for analysis.
- **Power BI File (Financial_Dashboard.pbix)**: Contains the dashboard with all pages, visuals, and DAX measures.
- **DAX Measures**:
  - `Total Sales = SUM(Sheet1[Sales])`
  - `Total Profit = SUM(Sheet1[Profit])`
  - `Avg Profit Margin = DIVIDE(SUM(Sheet1[Profit]), SUM(Sheet1[Sales]), 0)`
  - `Sales Contribution % = DIVIDE(SUM(Sheet1[Sales]), CALCULATE(SUM(Sheet1[Sales]), ALL(Sheet1[Country])), 0)`
  - Additional measures for units sold, discounts, and pricing metrics.

## Setup Instructions
1. **Prerequisites**:
   - Power BI Desktop (latest version).
   - "Financial Sample.xlsx" dataset (included in the repository).

2. **Installation**:
   - Clone or download this repository.
   - Open `Financial_Dashboard.pbix` in Power BI Desktop.
   - Ensure the dataset is linked to the `Sheet1` table in the Power BI model.

3. **Data Preparation**:
   - Verify data types: `Sales`, `Profit`, `Discounts`, `COGS` as Currency; `Units Sold` as Decimal; `Date` as Date.
   - Create a Date Table:
     ```DAX
     DateTable = CALENDAR(DATE(2013, 1, 1), DATE(2014, 12, 31))
     ```
   - Relate `Sheet1[Date]` to `DateTable[Date]` for time-based analysis.

4. **Usage**:
   - Navigate through the five dashboard pages (Overview, Trends, Discount Impact, Product Analysis, Regional Analysis).
   - Use slicers to filter by Segment, Country, Product, Discount Band, or Year.
   - Explore drill-downs and cross-filtering for detailed insights.

## Screenshots
*(To be added: Include screenshots of each dashboard page for visual reference.)*

## Future Enhancements
- Add predictive analytics to forecast sales trends for 2015.
- Incorporate Key Influencers visual to analyze drivers of profitability.
- Expand regional analysis with external economic data for deeper context.
- Automate data refreshes for real-time updates (if connected to a live source).

## Contributing
Contributions are welcome! Please submit a pull request or open an issue for suggestions, bug fixes, or additional features.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact
For questions or feedback, connect with me on [LinkedIn](https://www.linkedin.com/in/your-profile) or open an issue on GitHub.

---

*Created on July 31, 2025, for data-driven decision-making.*