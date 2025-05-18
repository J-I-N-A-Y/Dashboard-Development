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


    Pregnancies    Glucose    BloodPressure   SkinThickness   Insulin    BMI  \

             0            6      148             72             35        0  33.6   
             1            1       85             66             29        0  26.6   
             2            8      183             64              0        0  23.3   
             3            1       89             66             23       94  28.1   
             4            0      137             40             35      168  43.1   

    DiabetesPedigreeFunction  Age  Outcome 
   
       0                     0.627   50        1  
       1                     0.351   31        0  
       2                     0.672   32        1  
       3                     0.167   21        0  
       4                     2.288   33        1  

       Pregnancies     Glucose  BloodPressure  SkinThickness     Insulin  \
       
          count   768.000000  768.000000     768.000000     768.000000  768.000000   
          mean      3.845052  120.894531      69.105469      20.536458   79.799479   
          std       3.369578   31.972618      19.355807      15.952218  115.244002   
          min       0.000000    0.000000       0.000000       0.000000    0.000000   
          25%       1.000000   99.000000      62.000000       0.000000    0.000000   
          50%       3.000000  117.000000      72.000000      23.000000   30.500000   
          75%       6.000000  140.250000      80.000000      32.000000  127.250000   
          max      17.000000  199.000000     122.000000      99.000000  846.000000   

              BMI  DiabetesPedigreeFunction         Age     Outcome  
             count    768.000000                768.000000  768.000000  768.000000  
              25%      27.300000                  0.243750   24.000000    0.000000  
              50%      32.000000                  0.372500   29.000000    0.000000  
              75%      36.600000                  0.626250   41.000000    1.000000  
              max      67.100000                  2.420000   81.000000    1.000000  


![image](https://github.com/user-attachments/assets/3633076a-ea01-44f9-9c31-7b2390b4694a)

Selected features: ['Pregnancies', 'Glucose', 'BMI', 'DiabetesPedigreeFunction', 'Age']

Confusion Matrix:

 [[81 18]
 [17 38]]
 
Classification Report:

               precision    recall  f1-score   support

           0       0.83      0.82      0.82        99
           1       0.68      0.69      0.68        55

    accuracy                           0.77       154
    
   macro avg       0.75      0.75      0.75       154
weighted avg       0.77      0.77      0.77       154

Accuracy Score: 0.7727272727272727


