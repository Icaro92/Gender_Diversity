# Gender & Inclusion Dashboard for Human Resources
<p align = "center">
  <img src="https://github.com/Icaro92/Gender_Diversity/assets/58118599/236fcede-0bc6-4714-97d7-530337fdee56)">

## Objectives
This dashboard aims to provide a better understanding of gender diversity and inclusion for the HR Department in a Telecom company. The company has been working hard to improve gender balance at the executive management level.  
The challenge for this particular analysis was determining proper KPIs to answer the most important questions and defining KPIs in Hiring, Promotion, Performance, and Turnover.

# The Dashboard
You can **access the dashboard** in the link below (pages 1 and 2):
* [Gender Dashboard for Human Resources](https://app.powerbi.com/view?r=eyJrIjoiOGIyMDY4NzAtNDY2Ny00NGJiLThkODktODM4ZTMzNzgzZjFjIiwidCI6IjAyODQyZDljLWVhNTAtNGVkNy1iMWY1LWI2MDIwOGIwM2YzNyJ9)

## Data Source

This project was based on the [PwC in Switzerland](https://www.theforage.com/simulations/pwc-ch/power-bi-cqxg) job simulation from The Forage. The simulation provided data and directions into what was expected for the analysis.

# Measures created include (DAX formulas):
*  **Number of men** = CALCULATE(DISTINCTCOUNT('HR Manager'[Employee ID]), FILTER('HR Manager','HR Manager'[Gender] = "Male"))
  
* **Number of women**= # of women = CALCULATE(DISTINCTCOUNT('HR Manager'[Employee ID]), FILTER('HR Manager','HR Manager'[Gender] = "Female"))
  
*  **Number of leavers** = # of leavers = CALCULATE(countrows('HR Manager'), 'HR Manager'[FY20 leaver?] = "Yes")
  
*  **% employees promoted** (FY21) = divide(calculate(DISTINCTCOUNT('HR Manager'[Employee ID]), filter('HR Manager','HR Manager'[Promotion in FY21?] = "Yes")), calculate(DISTINCTCOUNT('HR Manager'[Employee ID]), filter('HR Manager','HR Manager'[In base group for Promotion FY21] = "Yes")))
  
*  **% of women promoted** = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female")),distinctcount('HR Manager'[Employee ID]))
  
*  **% of hires men** = DIVIDE([# of men], ([# of men] + [# of women]))
  
*  **% of hires women** = DIVIDE([# of women], ([# of men] + [# of women]))
  
*  **Average performance rating**: men = CALCULATE(AVERAGE('HR Manager'[FY20 Performance Rating]),'HR Manager'[Gender]="Male")
  
*  **Average Performance rating**: women = CALCULATE(AVERAGE('HR Manager'[FY20 Performance Rating]),'HR Manager'[Gender]="Female")
  
*  **% turnover** = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager',NOT('HR Manager'[Department @01.07.2020]=BLANK()))),2))
