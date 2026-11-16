# Experiment 4 : Yearly Revenue Growth Visualization Using Matplotlib

## Aim

To visualize the yearly trend of company revenue and expenses from 2017 to 2023 using Matplotlib by plotting multi-line charts with customized markers, labels, legends, gridlines, and point annotations.

## Algorithm

1. **Start** the program.
2. **Import Libraries**: Import `matplotlib.pyplot` as `plt` for plotting and `numpy` as `np` for numeric array generation and index lookup.
3. **Initialize Dataset**:
   * Generate an array `years` spanning `2017` to `2023` using `np.arange(2017, 2024)`.
   * Define lists `revenue` and `expenses` representing annual amounts in Lakhs.
4. **Configure Figure & Plot Lines**:
   * Initialize a figure canvas of size $8 \times 5$ inches using `plt.figure(figsize=(8, 5))`.
   * Plot `revenue` against `years` as a solid green line with circular markers (`marker='o'`).
   * Plot `expenses` against `years` as a dashed red line (`linestyle='--'`) with square markers (`marker='s'`).
5. **Format Chart Aesthetics**:
   * Add a bold chart title (`plt.title()`) and axis labels (`plt.xlabel()`, `plt.ylabel()`).
   * Enable dashed semi-transparent gridlines (`plt.grid()`) and place the legend in the upper-left corner (`plt.legend(loc='upper left')`).
6. **Annotate Peak Values**:
   * Find the indices of maximum revenue and maximum expenses using `np.argmax()`.
   * Highlight both peak data points on the chart with directional arrows and text callouts using `plt.annotate()`.
7. **Adjust Layout & Display**:
   * Prevent label clipping via `plt.tight_layout()` and render the final plot with `plt.show()`.
8. **Stop** the program.

## Functions and Methods Used

| Category | Function / Method | Purpose / Description |
| :--- | :--- | :--- |
| **Numerical Operations** | `np.arange()` | Generates evenly spaced integer years (`2017` through `2023`) |
| | `np.argmax()` | Returns the array index of the maximum revenue and expense values |
| **Line Plotting** | `plt.figure()` | Initializes a new figure window with custom dimensions |
| | `plt.plot()` | Draws line plots with customized markers, colors, line styles, and widths |
| **Chart Formatting** | `plt.title()`, `plt.xlabel()`, `plt.ylabel()` | Adds descriptive title and axis labels with custom font sizes |
| | `plt.grid()`, `plt.legend()` | Adds background gridlines and displays series labels in the upper left |
| **Annotations & Display** | `plt.annotate()` | Places text labels with arrows pointing to peak revenue and expense points |
| | `plt.tight_layout()`, `plt.show()` | Optimizes spacing to avoid overlapping elements and renders the figure |

## Program / Code

#Company Revenue and Expense Visualization using Matplotlib
import matplotlib.pyplot as plt
import numpy as np

#Step 1: Create dataset
import matplotlib.pyplot as plt
import numpy as np

years = np.arange(2017, 2024)

revenue = [50, 60, 75, 90, 110, 130, 150]
expenses = [30, 40, 45, 55, 65, 80, 95]

#Step 2: Plot Revenue and Expenses
plt.figure(figsize=(8, 5))

plt.plot(years, revenue, color='green',
         marker='o', label='Revenue', linewidth=2)

plt.plot(years, expenses, color='red',
         linestyle='--', marker='s',
         label='Expenses', linewidth=2)
         
#Step 3: Add titles, labels, and grid
plt.title("Company Revenue and Expenses (2017-2023)",
          fontsize=14, fontweight='bold')

plt.xlabel("Year")
plt.ylabel("Amount (Lakhs)")

plt.grid(True, linestyle='--', alpha=0.5)

#Step 4: Add legend
plt.legend(loc='upper left')

#Step 5: Annotate highest revenue and expense
max_rev = np.argmax(revenue)
max_exp = np.argmax(expenses)

plt.annotate('Highest Revenue',
             xy=(years[max_rev], revenue[max_rev]),
             xytext=(2019, 145),
             arrowprops=dict(arrowstyle='->'))

plt.annotate('Highest Expense',
             xy=(years[max_exp], expenses[max_exp]),
             xytext=(2020, 110),
             arrowprops=dict(arrowstyle='->'))
             
#Step 6: Adjust layout and show plot
plt.tight_layout()
plt.show()

## Output
<img width="912" height="537" alt="image" src="https://github.com/user-attachments/assets/2c96aa34-d11c-438e-a4b4-5239beed3ee1" />


## Result

The program successfully creates datasets for yearly company revenue and expenses and renders an annotated multi-line comparison chart using Matplotlib.
