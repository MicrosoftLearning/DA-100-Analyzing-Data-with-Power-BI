

### Lab 02A

Preparing Data in Power BI Desktop

# Overview

**The estimated time to complete the lab is 45 minutes**

In this lab, you commence the development of a Power BI Desktop solution for the Adventure Works company. It involves connecting to source data, previewing the data, and using data preview techniques to understand the characteristics and quality of the source data.

In this lab, you learn how to:

* Open Power BI Desktop

* Set Power BI Desktop options

* Connect to source data

* Preview source data

* Use data preview techniques to better understand the data

# Exercise1: Prepare Data

In this exercise, you will create eight Power BI Desktop queries. Six queries will source data from SQL Server, and two from CSV files.

### Task 1: Save the Power BI Desktop file

In this task, you will first save the Power BI Desktop file.

1. In Power BI Desktop, click the **File** ribbon tab to open the backstage view.

2. Select **Save**.

	![Picture 13](Linked_image_Files/PowerBI_Lab02A_image1.png)

3. In the **Save As** window, navigate to the **D:\DA100\Lab02A\MySolution** folder.

4. In the **File Name** box, enter **Sales Analysis**.

	![Picture 14](Linked_image_Files/PowerBI_Lab02A_image2.png)

5. Click **Save**.

	![Picture 17](Linked_image_Files/PowerBI_Lab02A_image3.png)

	*Tip: You can also save the file by click the **Save** icon located at the top-right*.

	![Picture 18](Linked_image_Files/PowerBI_Lab02A_image4.png)

### Task 2: Set Power BI Desktop options

In this task, you will set Power BI Desktop options.

1. In Power BI Desktop, click the **File** ribbon tab to open the backstage view.

7. At the left, select **Options and Settings**, and then select **Options**.

	![Picture 1](Linked_image_Files/PowerBI_Lab02A_image5.png)

8. In the **Options** window, at the left, in the **Current File** group, select **Data Load**.

	![Picture 5](Linked_image_Files/PowerBI_Lab02A_image6.png)

	*The **Data Load** settings for the current file allow setting options that determine default behaviors when modeling*.

9. In the **Relationships** group, uncheck the two options that are checked.

	![Picture 7](Linked_image_Files/PowerBI_Lab02A_image7.png)

	*While these two options can be helpful when developing a data model, they have been disabled to support the lab experience. When you create relationships in **Lab 03A**, you will learn why you are adding each one*.

10. Click **OK**.

	![Picture 9](Linked_image_Files/PowerBI_Lab02A_image8.png)

11. Save the Power BI Desktop file.

### Task 3: Get data from SQL Server

In this task, you will create queries based on SQL Server tables.

1. On the **Home** ribbon tab, from inside the **Data** group, click **SQL Server**.

	![Picture 19](Linked_image_Files/PowerBI_Lab02A_image9.png)

13. In the **SQL Server Database** window, in the **Server** box, enter **localhost**.

	![Picture 21](Linked_image_Files/PowerBI_Lab02A_image10.png)

	*In the labs, you will connect to the SQL Server database by using **localhost**. This isn’t a recommended practice, however, when creating your own solutions. It’s because gateway data sources cannot resolve **localhost***.

14. Click **OK**.

	![Picture 22](Linked_image_Files/PowerBI_Lab02A_image11.png)

15. Notice that the default authentication is to **Use My Current Credentials**.

	![Picture 23](Linked_image_Files/PowerBI_Lab02A_image12.png)

16. Click **Connect**.

	![Picture 25](Linked_image_Files/PowerBI_Lab02A_image13.png)

17. When prompted about encryption support, click **OK**.

	![Picture 27](Linked_image_Files/PowerBI_Lab02A_image14.png)

18. In the **Navigator** window, at the left, expand the **AdventureWorksDW2020** database.

	*The **AdventureWorksDW2020** database is based on the **AdventureWorksDW2017** sample database. It has been modified to support the learning objectives of the course labs*.

	![Picture 28](Linked_image_Files/PowerBI_Lab02A_image15.png)

19. Select—but don’t check—the **DimEmployee** table.

	![Picture 29](Linked_image_Files/PowerBI_Lab02A_image16.png)

20. In the right pane, notice a preview of the table.

	*The preview allows you to determine the columns and a sample of rows*.

21. To create queries, check the following six tables:

	* DimEmployee

	* DimEmployeeSalesTerritory

	* DimProduct

	* DimReseller

	* DimSalesTerritory

	* FactResellerSales

22. To apply transformations to the data of the selected tables, click **Transform Data**.

	*You won’t be transforming the data in this lab. The objectives of this lab are to explore and profile the data in the **Power Query Editor** window*.

	![Picture 30](Linked_image_Files/PowerBI_Lab02A_image17.png)

### Task 4: Preview SQL Server queries

In this task, you will preview the data of the SQL Server queries. First, you will learn relevant information about the data. You will also use column quality, column distribution, and column profile tools to understand the data, and assess data quality.

1. In the **Power Query Editor** window, at the left, notice the **Queries** pane.

	![Picture 31](Linked_image_Files/PowerBI_Lab02A_image18.png)

	*The **Queries** pane contains one query for each selected table*.

24. Select the first query—**DimEmployee**.

	![Picture 33](Linked_image_Files/PowerBI_Lab02A_image19.png)

	*The **DimEmployee** table stores one row for each employee. A subset of the rows represent the salespeople, which will be relevant to the model you’ll develop*.

25. At the bottom left, in the status bar, notice the table statistics—the table has 33 columns, and 296 rows.

	![Picture 36](Linked_image_Files/PowerBI_Lab02A_image20.png)

26. In the data preview pane, scroll horizontally to review all columns.

27. Notice that the last five columns contain **Table** or **Value** links.

	*These five columns represent relationships to other tables in the database. They can be used to join tables together. You will join tables in **Lab 03A***.

28. To assess column quality, on the **View** ribbon tab, from inside the **Data Preview** group, check **Column Quality**.

	![Picture 35](Linked_image_Files/PowerBI_Lab02A_image21.png)

	*Column quality allows you to easily determine the percentage of valid, error, or empty values*.

29. For the **Position** column (sixth last column), notice that 94% of rows are empty (null).

	![Picture 38](Linked_image_Files/PowerBI_Lab02A_image22.png)

30. To assess column distribution, on the **View** ribbon tab, from inside the **Data Preview** group, check **Column Distribution**.

	![Picture 40](Linked_image_Files/PowerBI_Lab02A_image23.png)

31. Review the **Position** column again, and notice that there are four distinct values, and one unique value.

32. Review the column distribution for the **EmployeeKey** (first) column—there are 296 distinct values, and 296 unique values.

	![Picture 43](Linked_image_Files/PowerBI_Lab02A_image24.png)

	*When the distinct and unique counts are the same, it means the column contains unique values. When modeling, it’s important that some tables contain unique columns. They will be used to create one-to-many relationships, which you will do in **Lab 04A***.

33. In the **Queries** pane, select the **DimEmployeeSalesTerritory** query.

	![Picture 44](Linked_image_Files/PowerBI_Lab02A_image25.png)

	*The **DimEmployeeSalesTerritory** table stores one row for each employee and the sales territory regions they manage. The table supports relating many regions to a single employee. Some employees manage one, two, or possibly more regions. When you model this data, you will need to define a many-to-many relationship, which you will do in **Lab 05A***.

34. In the **Queries** pane, select the **DimProduct** query.

	![Picture 46](Linked_image_Files/PowerBI_Lab02A_image26.png)

	*The **DimProduct** table contains one row per product sold by the company*.

35. Horizontally scroll to reveal the last columns.

36. Notice the **DimProductSubcategory** column.

	*When you add transformations to this query in the next lab, you’ll use the **DimProductSubcategory** column to join tables*.

37. In the **Queries** pane, select the **DimReseller** query.

	![Picture 49](Linked_image_Files/PowerBI_Lab02A_image27.png)

	*The **DimReseller** table contains one row per reseller. Resellers sell, distribute, or value add Adventure Works’ products*.

38. To view column values, on the **View** ribbon tab, from inside the **Data Preview** group, check **Column Profile**.

	![Picture 41](Linked_image_Files/PowerBI_Lab02A_image28.png)

39. Select the **BusinessType** column header.

40. Notice that a new pane opens beneath the data preview pane.

41. Review the column statistics and value distribution.

42. Notice the data quality issue: there are two labels for warehouse (**Warehouse**, and the misspelled **Ware House**).

	![Picture 51](Linked_image_Files/PowerBI_Lab02A_image29.png)

43. Hover the cursor over the **Ware House** bar, and notice that there are five rows with this value.

	*In the next lab, you will apply a transformation to relabel these five rows*.

44. In the **Queries** pane, select the **DimSalesTerritory** query.

	![Picture 52](Linked_image_Files/PowerBI_Lab02A_image30.png)

	*The **DimSalesTerritory** table contains one row per sales region, including **Corporate HQ** (headquarters). Regions are assigned to a country, and countries are assigned to groups. In **Lab 04A**, will create a hierarchy to support analysis at region, country, or group level*.

45. In the **Queries** pane, select the **FactResellerSales** query.

	![Picture 54](Linked_image_Files/PowerBI_Lab02A_image31.png)

	*The **FactResellerSales** table contains one row per sales order line—a sales order contains one or more line items*.

46. Review the column quality for the **TotalProductCost** column, and notice that 8% of the rows are empty.

	![Picture 63](Linked_image_Files/PowerBI_Lab02A_image32.png)

	*Missing **TotalProductCost** column values is a data quality issue. To address the issue, in the next lab you will apply transformations to fill in missing values by using the product standard cost, which is stored in the **DimProduct** table*.

### Task 5: Get data from a CSV file

In this task, you will create a query based on a CSV file.

1. To add a new query, in the **Power Query Editor** window, on the **Home** ribbon tab, from inside the **New Query** group, click the **New Source** down-arrow, and then select **Text/CSV**.

	![Picture 70](Linked_image_Files/PowerBI_Lab02A_image33.png)

48. In the **Open** window, navigate to the **D:\DA100\Data** folder, and select the **ResellerSalesTargets.csv** file.

49. Click **Open**.

50. In the **ResellerSalesTargets.csv** window, notice the data preview.

51. Click **OK**.

	![Picture 71](Linked_image_Files/PowerBI_Lab02A_image34.png)

52. In the **Queries** pane, notice the addition of the **ResellerSalesTargets** query.

	![Picture 72](Linked_image_Files/PowerBI_Lab02A_image35.png)

	*The **ResellerSalesTargets** CSV file contains one row per salesperson, per year. Each row records 12 monthly sales targets (expressed in thousands). The business year for the Adventure Works company commences on July 1*.

53. Notice that no columns contain empty values.

	*When there isn’t a monthly sales target, a hyphen character is stored instead*.

54. Review the icons in each column header, to the left of the column name.

	![Picture 74](Linked_image_Files/PowerBI_Lab02A_image36.png)

	*The icons represent the column data type. **123** is whole number, and **ABC** is text*.

	*In the next lab, you’ll apply many transformations to achieve a different shaped result consisting of only three columns: **Date**, **EmployeeKey**, and **TargetAmount***.

### Task 6: Get additional data from a CSV file

In this task, you will create an additional query based on a different CSV file.

1. Use the steps in the previous task to create a query based on the **D:\DA100\Data**\**ColorFormats.csv** file.

	![Picture 75](Linked_image_Files/PowerBI_Lab02A_image37.png)

	*The **ColorFormats** CSV file contains one row per product color. Each row records the HEX codes to format background and font colors. In the next lab, you will integrate this data with the **DimProduct** query data*.

### Finish up

In this task, you will complete the lab.

1. On the **View** ribbon tab, from inside the **Data Preview** group, uncheck the three data preview options:

	* Column quality

	* Column distribution

	* Column profile

	![Picture 76](Linked_image_Files/PowerBI_Lab02A_image38.png)

57. To save the Power BI Desktop file, on the **File** backstage view, select **Save**.

	![Picture 77](Linked_image_Files/PowerBI_Lab02A_image39.png)

58. When prompted to apply the queries, click **Apply Later**.

	![Picture 86](Linked_image_Files/PowerBI_Lab02A_image40.png)

	*Applying the queries will load their data to the data model. You’re not ready to do that, as there are many transformations that must be applied first*.

59. Leave Power BI Desktop open.

	*In the next lab, you will apply various transformations to the queries, and then apply the queries to load them to the data model*.
