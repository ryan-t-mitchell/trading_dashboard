
# 📈 Webull Trade Analyzer

Analyze and visualize your trading performance from raw Webull order data using Python.

This project reconstructs complete and partial trades using FIFO logic, calculates performance KPIs, and generates professional dashboards and charts inspired by platforms like TradeZella.

---

## 🚀 Features

- ✅ **Automatic trade grouping** using FIFO methodology  
- 📊 **Realized P&L breakdowns** for both fully and partially closed trades  
- 📅 **Daily net cumulative P&L chart** with red/green gradient fill  
- 🧠 **KPI Cards** for:
  - Net P&L
  - Trade win %
  - Profit factor
  - Day win %
  - Average win/loss
  - Total trades
- 📈 **Day win %** computed using actual realized closes  
- 🎯 Optional Plotly gauge visualizations  

---

## 📂 Input Format

Just export your order history from Webull and save as:

```bash
~/Downloads/Webull_Orders_Records_new.csv
```

The script expects columns like:

- `Symbol`
- `Side` (Buy/Sell)
- `Filled` (Quantity)
- `Avg Price`
- `Filled Time`

---

## 🧮 Key Metrics Calculated

| Metric             | Description                                                    |
|--------------------|----------------------------------------------------------------|
| **Net P&L**        | Total profit/loss from all matched closes (partial + full)     |
| **Trade win %**    | % of fully closed trades with positive P&L                     |
| **Profit Factor**  | Sum of wins / absolute sum of losses                           |
| **Day win %**      | % of trading days with net positive realized P&L               |
| **Avg Win/Loss**   | Average size of winning vs losing trades                       |
| **Cumulative P&L** | Running sum of daily realized P&L                              |

---

## 📊 Example Visuals

### ✅ Cumulative P&L Chart
- Simulates TradeZella-style fill  
- Red below $0, green above $0  
- Final P&L value annotated  

### 📇 KPI Cards
Displayed inline using styled HTML:

- 🟩 Net P&L
- 🟩 Trade Win %
- 🟨 Profit Factor
- 🟥 Day Win %

### 🎯 Plotly Gauges *(optional)*
> Visual indicators of win rates, customizable per metric.

---

## 🛠 Setup & Usage

### 1. Install dependencies

```bash
pip install pandas matplotlib plotly python-dateutil
```

### 2. Run the notebook or script

Ensure your file path is correct:

```python
orders_df = pd.read_csv(PATH TO CSV)
```

Run the analysis and visuals will be generated inline.

---

## 📌 Notes

- Uses FIFO logic to match Buy and Sell orders per symbol.
- Partial closes are treated accurately.
- Trade grouping follows round-trip logic: position starts at 0 and returns to 0.

---

## 🧠 Inspiration

Inspired by TradeZella, but fully transparent and customizable in Python.

---

## 📬 Feedback

Have an idea for new KPIs? Want to export to Google Sheets or PDF? Open an issue or PR!

---

**Made with ❤️ by traders, for traders.**