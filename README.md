# Excel Dashboard + PivotTable Demonstration

![image](https://github.com/user-attachments/assets/6f2861c7-20eb-4ec5-8335-8aadedd07582)
 <BR>
**_The following dashboard can be accessed [HERE](https://1drv.ms/x/s!AuV0f7giR2NGhC6TURBWo16u7rl8?e=PsscOc) and in this repository._**

## Dashboard Description
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

## Making the Graphs

1 & 2: The first and 3rd columns here are used as the data for the chart. *(We will talk about column 2 soon)*. In order to choose what company we want to see the average review of, I created a button for the graph using **Data Validation** to select the array of data, that being the **Company Sorted** Column. 
```
='Company + Country + Style'!$I$2:$I$16
```

![image](https://github.com/user-attachments/assets/201fef78-ebbd-4cd1-bb0b-b5d9545a702f)

3: The last column has the **XLOOKUP** function, this will return a value from the range when selected in the graph. In the case of the GIF below, the company **MAMA** updates to an average review of 3.7 when selected .
```
=XLOOKUP(company,I2:I16,K2:K16)
```

![Xlookup gif](https://github.com/user-attachments/assets/18ac1325-0759-486b-b38f-ed8a6c7b896c) <br>
**Extra:** I found a way to make the graph's bars change, contrasting the focused data point. In the case of this video, the focused bar will become dark blue, while the other companies bars remain light blue.
- The top **IF** function looks for the value of the **I** column, if it doesn't equal **Company** *(The button name for the chart)*, return the value of the **J** column.
- The bottom **IF** function does the opposite, 
these two IFS create the contrasting bars.

```
=IF($I2<>company,$J2,N/A())
=IF($I2=company,$J2,N/A())
```

Lastly, I repeated this process two more times for the remaining graphs.
![Ramen Ratings Video](https://github.com/user-attachments/assets/5586ac24-790e-4567-9eb3-aae6bde09b27)

# PivotTable & PivotChart Section
![image](https://github.com/user-attachments/assets/d27b35a7-f64d-4010-87da-f11ef6c2c0c1)
<br>
**PivotTables** are ubiquitous when it comes to Excel and visualizing data. Below is a quick demonstration of the above data, <br>
converted into a PivotChart this time.

## Quick Rundown
1: I started by going to the **Data** worksheet, and selecting **Insert PivotTable**. Since I was trying to replicate the Dashboard above, I selected fields accordingly, 
the following fields were used:
<br>
![image](https://github.com/user-attachments/assets/f40b810c-0eda-4b09-8d61-8a0907617040)
![image](https://github.com/user-attachments/assets/5370414d-9fab-476a-a342-4ec33dfafff8)
![image](https://github.com/user-attachments/assets/83fee973-3ce7-4bc1-a13e-762ee1a95677)
- Inside of the **Values** field **Average Rating**, **Total Ratings** and **Style Total** were inserted.
- Inside of the **Rows** field I used **Style** and **Brand**. 
- Inside of the **Columns** field values were inserted.
<br>

2: Next, I selected the table and inserted a slicer. Slicers are used to filter data interactively. Again, since the goal is to create a PivotChart similar to the Dashboard, I added a slicer to filter by country.
![2](https://github.com/user-attachments/assets/fcb3199d-c5ef-4559-966c-000d589d5a65)


3: Now that we have a slicer, we can manipuilate the data by filtering for whatever country or countries we want to.

![GIF2](https://github.com/user-attachments/assets/bcaaf04c-136c-42f0-addb-c05d646bbac9)

## Conclusion
From these two examples of data visualizations, businesses, countries, or other stakeholders can draw **several insights:**
- Types of ramen to produce
- Countries to focus production efforts in
- Preferred styles of ramen.

I **intentionally omitted** certain data, like Top 10 and Variety because:
- I prioritized other fields which I considered more significant factors.
- Including too many data variants would make this presentation overly complex.

Thank you for taking the time to review this demonstration of my foundational Excel skills!





