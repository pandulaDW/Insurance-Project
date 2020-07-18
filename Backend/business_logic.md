## Business Logic

#### Input files
    - Client Input (all plans)
    - Input per plan  
    - Assumptions per plan 

#### Input per each policy
    - Valuation Date (Client data)
    - Age (Client data)
    - Commencement date (Client data)
    - Spouse Age (Client data), if missing 0 in assumptions


#### Logic per each row in policy projection
    -  Time
       Calculate the date column first and if date exists, increment by 1. 
      
    -  Date
       First row will start from valuation data. Then take age of each client
       and check if the client age is less than a "given value". If yes, add a 
       month to the previous month and get end of the month date. If not, terminate
       calculating the table
       
    -  Policy year
       Get the difference in years of commencement date and Date column. Round up
       the figure.  
       
    -  Age
       First cell will be taken from the input. Starting from the valuation date, 
       check if an year has passed, if yes, then increment by one.
       
     - Age (Spouse)
       Taken straightly from the assumptions
       
     - Year
       The number of years passed after valuation date
       
     - Month
       Number of months passed after the valuation date. Restart month count after
       each year increment 