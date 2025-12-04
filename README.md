# 📈 Interactive Sales Growth Rate Dashboard

## 🎯 What is This Project?

This is an **Interactive Sales Growth Rate Dashboard** built using **Python**, the **Pandas** library for data handling, and the **Dash** framework (Plotly) for web visualization.

The application analyzes simulated sales data, allowing the user to dynamically select any two dates within the dataset. It instantly calculates the **percentage growth rate** (or decline) between those periods, displaying the result as a clear Key Performance Indicator (KPI) and visualizing the trend on a responsive time-series chart.

---

## 💡 Why Was It Done? (Value Proposition)

The creation of this project serves both practical analytics needs and educational purposes:

* **KPI Insight:** Provides a quick, visual tool for business users to gauge performance and volatility in sales figures, which is crucial for **demand planning** and inventory decisions.
* **Demonstrate Python Capabilities:** Showcases the ability of Python to create **interactive, browser-based analytics applications** using Dash, a key skill in data science and business intelligence.
* **Illustrate Core Logic:** Explicitly demonstrates robust **date comparison logic** and the handling of the mathematical edge case of calculating growth from a zero base.

---

## ⚙️ How Was It Done? (Implementation Details)

The dashboard is structured using a modular three-part architecture:

### 1. Data & Core Logic

* **Simulation:** Sales data over a 12-month period is simulated using Pandas.
* **Growth Rate Function:** A dedicated Python function calculates the percentage change using the standard formula:
    $$\text{Growth Rate} = \left( \frac{\text{End Value} - \text{Start Value}}{\text{Start Value}} \right) \times 100$$
* **Validation:** Includes exception handling to prevent runtime errors (e.g., division by zero) and logical errors (e.g., ensuring the start date precedes the end date).

### 2. Frontend Layout (Dash)

* The layout uses Dash's HTML components, featuring custom CSS styling for a clean look.
* **User Controls:** Two `dcc.Dropdown` components allow the user to select the **Start Month** and **End Month**.
* **Visual Elements:** Dedicated panels display the primary KPI and the interactive `dcc.Graph` container for the sales trend line.

### 3. Backend Interactivity (Callbacks)

* The `@app.callback` decorator links the two dropdowns (as **Inputs**) to the KPI text and the chart figure (as **Outputs**).
* The callback function filters the data, executes the core growth rate calculation, and uses **Plotly** to generate a line chart with **color-coding** (green for growth, red for decline) and **annotations** marking the start and end points.

---

## 🚀 Getting Started

### Prerequisites

Ensure you have Python installed and the following libraries:

```bash
pip install pandas dash plotly
