# My-PALAMORIA-Documentation

## Project Topic:Palmora Group HR Analysis
This marks the beginning of my portfolio-building journey, which I've undertaken alongside my Data Analysis class at the Incubator Hub.  
I am working The Palmoria Group, a manufacturing company based in Nigeria, is embroiled in issues bordering on gender inequality in its 3 regions. Unfortunately, the media recently published the news with the headline “Palmoria, the Manufacturing Patriarchy”. This doesn’t look good for the owners of the business, based on their ambition to scale the business to other regions and even overseas. Cases like this can only spiral downwards,revealing other issues like the gender pay gap, amongst other possible issues.The CEO of Palmoria, Mr Ayodeji Chukwuma, is keen to address these issues before they get out of hand. The CHRO, Mr Yunus Shofoluwe, has been assigned the task to identify key areas within the business that could give rise to issues and address them immediately.Mr Shofoluwe decided to recruit me as an HR Analytics expert to analyse the company’s HR data and come up with recommendations for management’s attention. “Now, the future of gender equality in Palmoria lies in your hands” – the exact words of Mr Shofoluwe before he handed the data to me.

### TOOLS USED
-   Microsoft excel 
  -    Data cleaning
  -    Data manipulation
-   Power BI (Forcasting a report)[dowload Here](https://www.microsoft.com/en-gb/power-platform/products/power-bi/).



###   The EDA involves exploring of the Data to answer some questions like:

####   Analysis Tasks
-    What is the gender distribution in the organization? Distil to regions and departments
-    Show insights on ratings based gender
-    Analyse the company’s salary structure. Identify if there is a gender pay gap. If there is, identify the department and regions that should be the focus of management A recent regulation was adopted which requires manufacturing companies to pay employees a minimum of $90,000
-    Does Palmoria meet this requirement?
-    Show the pay distribution of employees grouped by a band of $10,000. For example:
-    How many employees fall into a band of $10,000 – $20,000, $20,000 – $30,000,etc.?
-    Also visualize this by regions.


### Analysis of Data

-  Import the employee data into Power BI.
-  Do a proper cleaning E.g
 Remove employees without salaries and departments indicated as "NULL".
-  Assign a generic gender status to employees who refused to disclose their gender.

-  Gender Distribution Analysis-
-  Create a bar chart:
-  Axis: Region/Department
-  Value: Count of Employees by Gender
-  set a slicer to filter by region/department.
-  Visualize the overall gender distribution using a pie chart.

### Visualization: 
-  Bar chart: "Gender Distribution by Region"
-  Pie chart: "Overall Gender Distribution"

- Measures
-     Gender Count = COUNT('Employee'[Gender])`
-     Gender Percentage = DIVIDE(CALCULATE(COUNT('Employee'[Gender])), CALCULATE(COUNT('Employee'[Gender]), ALL('Employee'[Gender])))`

- 2: Ratings Insights Based on Gender
1. Create a histogram/box plot:
    - Axis: Rating
    - Value: Count of Employees by Gender
2. Use a slicer to filter by gender.
3. Calculate the average rating by gender using a measure.

Visualization:
- Histogram: "Ratings Distribution by Gender"
- Box plot: "Ratings Comparison by Gender"

Measures
- `Average Rating by Gender = AVERAGE('Employee'[Rating])`
- `Rating Count by Gender = COUNT('Employee'[Rating])`

- 3: Salary Structure and Gender Pay Gap Analysis
1. Create a scatter plot:
    - X-axis: Salary
    - Y-axis: Gender
2. Calculate the average salary by gender using a measure.
3. Identify departments and regions with significant pay gaps.

Visualization:
- Scatter plot: "Salary vs. Gender"
- Bar chart: "Average Salary by Department and Region"

Measures 
- `Average Salary by Gender = AVERAGE('Employee'[Salary])`
- `Salary Count by Department and Region = COUNT('Employee'[Salary])`

 ### Minimum Salary Requirement Analysis
 - Create a histogram:
 - Axis: Salary Band ($10,000 increments)
 - Value: Count of Employees
 - Use a slicer to filter by region.
-  Calculate the number of employees below the minimum salary threshold.

### Visualization:
 - Histogram: "Salary Distribution by $10,000 Band"
 - Bar chart: "Employees Below Minimum Salary Threshold by Region"

### Measures
     - `Employees Below Minimum Salary = COUNTX(FILTER('Employee', 'Employee'[Salary] < 90000), 'Employee'[Salary])`

 ### Bonus Payment Calculation
-  Create a measure to calculate the bonus amount based on performance ratings.
-  Calculate the total amount to be paid to individual employees (salary + bonus).
-  reate a bar chart to visualize the total amount to be paid out per region.

### Visualization:
-   Bonus Payments
-   Bar chart: "Total Bonus Payout by Region"
- Table: "Individual Employee Bonus Payments"

### Measures
     - `Bonus Amount = IF('Employee'[Rating] > 3, 'Employee'[Salary] * 0.1, 0)`
     - `Total Amount to be Paid = 'Employee'[Salary] + 'Bonus Amount'`
