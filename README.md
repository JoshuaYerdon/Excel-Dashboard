# Excel Dashboard + Pivot Table Demonstration

![image](https://github.com/user-attachments/assets/6f2861c7-20eb-4ec5-8335-8aadedd07582)
 <BR>
**_The following dashboard can be accessed [HERE](https://1drv.ms/x/s!AuV0f7giR2NGhC6TURBWo16u7rl8?e=SQLigE) and in this repository._**

## Project Description
I found a simple dataset about ranking ramen types on Kaggle. It included things like the rating, type of ramen, brand, country, and the form or packaging of the ramen. This project will
showcase my ability to use foundational Excel functions, and make charts/pivot charts for data visualization.


## Organizing the Data

1: I started by using the **UNIQUE** function to reference the **Data** worksheet, removing any redundant fields from the **Company** column so that company names will only show once. 
```
=UNIQUE(Data!B2:B2581)
```

2: Next I used the **COUNTIF** function to count how many reviews there were **PER** company.
```
=COUNTIF(Data!B2:B2581,$A2)
```

3: Following this I used the **AVERAGEIF** function to take the **Average Review** to give the average review of each company.
```
=ROUND(AVERAGEIF(Data!B2:B2581,$A2,Data!F2:F2581), 2)
```

![image](https://github.com/user-attachments/assets/28b9b783-23a6-4ca0-8043-a8b748bc2453)

4: The **UNIQUE** function was used for the **Country** column to remove any redundant county names.
```
=UNIQUE(Data!E2:E2581)
```

5: **Amount of Reviews** was created to count the amount of reviews in total **PER** country.
```
=COUNTIF(Data!E2:E2581,D2#)
```

6 & 7: Lastly, I used the **UNIQUE** and **COUNTIF** functions to list all unqiue styles of ramen in the **Style** column, and to count how many times each style occured, sorted in the **Amount of Style** column.
```
=UNIQUE(Data!D2:D2153)
```
![image](https://github.com/user-attachments/assets/2dd750e5-291f-41f5-98d5-3b0cf0552104)

## Making the Charts

1 & 2: The first and 3rd columns here are used as the data for the chart. *(Column 2 is essentially useless here, I just like to organize the data like this)*. In order to choose what company we want to see the average review of, I created a button for the graph using **Data Validation** to select the array of data, that being the **Company Sorted** Column. 
```
='Company + Country + Style'!$I$2:$I$16
```

![Image](https://i.imgur.com/EJvNyvA.png)

3: The last column has the **XLOOKUP** function, this will return a value from the range when selected in the graph. In the case of the GIF below, the company **MAMA** when selected updates to an average review of 3.7.
```
=XLOOKUP(company,I2:I16,K2:K16)
```

![Xlookup gif](https://github.com/user-attachments/assets/18ac1325-0759-486b-b38f-ed8a6c7b896c) <br>
Lastly, I repeated this process two more times for the remaining graphs.

The chart itself is composed of the 
![image](https://github.com/user-attachments/assets/ae8988f9-d888-4229-ad07-bd4fe095acd2)
















<br>
![Ramen Ratings Video](https://github.com/user-attachments/assets/5586ac24-790e-4567-9eb3-aae6bde09b27)
