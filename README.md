# Excel Dashboard + Pivot Table Demonstration

![image](https://github.com/user-attachments/assets/6f2861c7-20eb-4ec5-8335-8aadedd07582)
 <BR>
**_The following dashboard can be accessed [HERE](https://1drv.ms/x/s!AuV0f7giR2NGhC6TURBWo16u7rl8?e=SQLigE) and in this repository._**

## Project Description
I found a simple dataset about ranking ramen types on Kaggle. It included things like the rating, type of ramen, brand, country, and the form or packaging of the ramen. This project will
showcase my ability to use foundational Excel functions, and make charts/pivot charts for data visualization.


## Starting Things Off
1: I started by using the **UNIQUE** function to reference the **Data** worksheet, removing any redundant fields from the **Company** column so that company names will only show once. 
```
=UNIQUE(Data!B2:B2581)
```
<br>
2: Next I used the **COUNTIF** function to count how many reviews there were **PER** company.

```
=COUNTIF(Data!B2:B2581,$A2)
```

![image](https://i.imgur.com/ak4Bw85.png)




Then, I used **COUNTIF** to count key numbers or items that helped give insights.
![image](https://github.com/user-attachments/assets/4ed890f1-4f2d-405d-923b-e18aa7dda205)

I added the following IF statements:
<br>
![image](https://github.com/user-attachments/assets/31bc877a-33e1-450d-acb8-2d78bb111e77)
<br>
```
=IF(I3<>company,J3,N/A())
=IF($I2=company,$J2,N/A())
```
This changed the color of rows that didn’t match the selected data for a better visual look.
![image](https://github.com/user-attachments/assets/df6bb6cf-63c4-4641-b596-b0874ee00a9d)




I used **XLOOKUP** to find the rating for that choice and display it on the graph. <br>
![image](https://github.com/user-attachments/assets/266e7dc4-3ac3-4124-9b5f-210b23cf3180)


```
=XLOOKUP(company,I2:I16,K2:K16)
```

![Xlookup gif](https://github.com/user-attachments/assets/18ac1325-0759-486b-b38f-ed8a6c7b896c) <br>
Lastly, I repeated this process two more times for the remaining graphs.
<br>
![Ramen Ratings Video](https://github.com/user-attachments/assets/5586ac24-790e-4567-9eb3-aae6bde09b27)
![image](https://github.com/user-attachments/assets/2885d27a-e4ad-49c2-837b-6ffdc61b9ac9)
**_A larger look at the Coding_**

