# 🛒 Online Retail Data Cleaning & Exploratory Data Analysis (EDA)

Cleaning and exploring 541,909 retail transactions to find where revenue comes from, when it peaks, and which products and customers drive it.

**Program:** AnalystLab Africa Data Analytics Internship (Week 1)
**Author:** Danjuma Zainab
**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

---

## The Business Problem

Raw transaction logs contain missing values, duplicates, returns and pricing errors that distort revenue figures. Before a retailer can decide which markets, products and customers to prioritise, the data must be cleaned and validated. This project turns raw transactions into an analysis-ready dataset and answers four questions:

1. Which countries generate the most revenue?
2. When does revenue peak?
3. Which products drive demand?
4. How concentrated is customer spending?

## Dataset

- **Source:** Online Retail transactions dataset
- **Size:** 541,909 rows, 8 columns
- **Columns:** InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country
- **Period:** 1 December 2010 to 9 December 2011, 38 countries

### Cleaned dataset and Raw Dataset 

The raw and cleaned file (`OnlineRetail_Cleaned.csv`, 524,878 rows) is too large for GitHub.
Download it here: 
- Dataset:**https://drive.google.com/file/d/1AbG2DAKokA0TcPlouOEnHUeY831n3bl6/view?usp=sharing**
- Cleaned Datset:**https://drive.google.com/file/d/1NwQxGdlM5iaLWJHW5r9IplJe1u_luxmz/view?usp=drive_link**

## Data Cleaning

| Issue | Count | Action |
|---|---|---|
| Missing Description | 1,454 (0.27%) | Rows removed |
| Missing CustomerID | 135,080 (24.93%) | Kept as valid sales; excluded from customer-level analysis only |
| Duplicate records | 5,268 | Removed |
| Column names | 8 | Lowercased and underscored |
| InvoiceDate as text | 1 | Converted to datetime |
| Cancelled invoices (prefix "C") | 9,251 | Removed |
| Negative quantities | 9,725 | Removed |
| Zero or negative unit price | 1,058 | Removed |

**Result:** 17,031 rows removed (3.14%), leaving **524,878** completed sales transactions. A `revenue` column (`quantity x unitprice`) was added for analysis.

## Key Insights

1. **UK dependence:** The UK generated about £9.00M, over 30 times the next market (Netherlands, £285K), because sales are overwhelmingly domestic.
2. **Strong seasonality:** Revenue peaked at £1.50M in November 2011, nearly three times February's £523K, as holiday gifting demand built from September.
3. **Gifting and décor lead demand:** Paper Craft, Little Birdie sold the most units (80,995) and White Hanging Heart T-Light Holder appeared in the most orders (2,311), reflecting a gift-led product mix.
4. **Concentrated customer spend:** Customer 14646 spent the most (£280K) and the top 10 identified customers contributed about £1.54M, so spending is concentrated in a few high-value accounts.
5. **Cleaning protected accuracy:** Removing only 3.14% of rows eliminated returns, duplicates and zero-price lines that would have distorted every metric above.

## Recommendations

- **Prepare for Q4 early:** build stock and launch campaigns from September.
- **Reduce UK reliance:** test targeted marketing in the Netherlands, Ireland, Germany and France.
- **Protect top customers:** introduce loyalty rewards and account management.
- **Prioritise proven gift and décor lines:** keep best-sellers stocked and bundle them for gifting.
- **Capture customer IDs:** about 25% of transactions have none, which limits customer analysis.

## Limitations

- Cancelled invoices were removed without being matched to their original orders, so a large order that was later reversed may still count as a sale.
- December 2011 is a partial month (1 to 9 December).
- Customer-level results cover only transactions with a recorded CustomerID.

## Repository Structure

```
├── Online_Retail_Data_Cleaning_EDA.ipynb
├── Online_Retail_EDA_Report.pdf
├── assets/
│   ├── monthly.png
│   ├── countries.png
│   ├── products.png
│   └── customers.png
└── README.md
```

## How to Run

```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook Online_Retail_Data_Cleaning_EDA.ipynb
```

Update the file path in the "Load Dataset" cell to point to your copy of `OnlineRetail.csv`.

## Next Steps

- Customer segmentation (RFM analysis)
- Product-level revenue analysis
- Interactive Power BI dashboard

## Key Takeaway

Clean data changes the story. Removing just 3.14% of the rows gave a reliable base that showed a UK-dependent business, a strong Q4 peak, a gift-led product mix and concentrated customer spending.

## Author

**Danjuma Zainab**
Data Analytics Intern, AnalystLab Africa

- LinkedIn: https://www.linkedin.com/danjuma-zainab
- GitHub: https://www.github.com/Xee-xainab

## Acknowledgements

Thanks to AnalystLab Africa for the opportunity and guidance during the internship.

If you found this project useful, please give it a ⭐ and feel free to share feedback.













