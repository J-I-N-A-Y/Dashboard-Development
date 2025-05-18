# Dashboard-Development

*COMPANY*: CODTECH IT SOLUTIONS

*NAME*:JINAY SHAH

*INTERN ID*:CT04DL198

*DOMAIN*:DATA ANALYTICS

*DURATION*:4 WEEKS

*MENTOR*:NEELA SANTHOSH

## DESCRIPTION

This Python script builds an interactive financial dashboard using the Dash framework. Dash, developed by Plotly, allows developers to create rich web applications for data visualization entirely in Python, without needing knowledge of JavaScript or HTML. The script demonstrates a complete pipeline: simulating financial transaction data, creating a user interface (UI), and enabling interactivity via callbacks. It serves as a strong example of how dashboards can help users explore large datasets and extract insights in real time.

---

### **1. Data Simulation**

At the outset, the script simulates a dataset of 100,000 financial transactions using `pandas` and `numpy`. Five transaction categories (`Groceries`, `Electronics`, `Clothing`, `Entertainment`, and `Health`) and five customers (`Alice`, `Bob`, `Charlie`, `Diana`, and `Eve`) are defined. Each transaction has a unique ID, a randomly assigned category and customer, and a transaction amount randomly sampled between \$5 and \$500. This creates a synthetic but realistic dataset suitable for financial analysis.

---

### **2. Dash App Initialization**

The Dash app is initialized with `app = dash.Dash(__name__)`, and a title is set for the web page. Dash applications are structured with a layout and a set of callbacks that define the interactivity.

---

### **3. App Layout**

The layout defines how the dashboard will appear to users. It includes:

* A **title** displayed as a header.
* A **dropdown menu** (`dcc.Dropdown`) that allows the user to select one of the customers.
* A **row of two bar charts** side by side:

  * One for total transaction amounts by category.
  * Another for the average transaction value for the selected customer.
* A **histogram** that shows the overall distribution of transaction amounts.

The two bar charts are wrapped in a `html.Div` styled with CSS to appear side-by-side using `display: flex`, providing a clean and responsive UI.

---

### **4. Interactivity with Callbacks**

The core functionality of Dash lies in its callback system, which updates components of the layout in response to user input.

In this case, a single callback takes the selected customer from the dropdown and returns three updated figures:

1. **Total Transactions by Category (`fig1`)**: This figure uses `groupby` to sum transaction amounts per category across all customers. It's a static chart not affected by dropdown selection.
2. **Average Transaction Value by Category for the Selected Customer (`fig2`)**: This chart filters the dataset by the selected customer, then computes and displays the mean transaction amount per category.
3. **Transaction Amount Distribution (`fig3`)**: A histogram showing the frequency of transaction amounts. This is also static and not affected by customer selection.

All visualizations are built using Plotly Express, a high-level interface for creating interactive graphics.

---

### **5. Running the App**

Finally, the script runs the Dash server using `app.run(debug=True)`. When executed, it launches the app in a local web browser. The `debug=True` flag enables hot-reloading and helpful error messages during development.

## OUTPUT

![Image](https://github.com/user-attachments/assets/e4cb573c-5f3a-484b-80dd-a9e469d8e299)
