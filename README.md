## Excel Dashboard Demonstration 

![image](https://github.com/user-attachments/assets/6f2861c7-20eb-4ec5-8335-8aadedd07582)
 <BR>
**_The following dashboard can be accessed [HERE](https://1drv.ms/x/s!AuV0f7giR2NGhC6TURBWo16u7rl8?e=SQLigE) and in this repository._**

## Dashboard Decription
I found a simple dataset about ranking ramen types on Kaggle. It included things like the rating, type of ramen, brand, country, and the form or packaging of the ramen. 
Here's a quick 60-second summary:

## Quick Rundown

I started by using functions like **UNIQUE** and **SORT** to organize the data into groups. 
<br>
![image](https://github.com/user-attachments/assets/14753c0f-cc5c-49a2-9521-3d51c2714d02)

```
=ROUND(AVERAGEIF(Data!B3:B2582,$A3,Data!F3:F2582), 2)
=SORT(A2:C354,2,-1)
```

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


