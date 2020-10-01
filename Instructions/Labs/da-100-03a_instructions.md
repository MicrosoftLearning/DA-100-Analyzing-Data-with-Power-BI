

### Lab 03A

Loading Data in Power BI Desktop

# Overview

**The estimated time to complete the lab is 45 minutes**

In this lab, you will commence apply transformations to each of the queries created in the previous lab. You will then apply the queries to load each as a table to the data model.

In this lab, you learn how to:

* Apply various transformations

* Apply queries to load them to the data model

# Exercise 1: Load Data

In this exercise, you will apply transformations to each of the queries created in the previous lab.

*If you’re not confident you completed the previous lab successfully, you can open the previous lab’s solution file, which is found in the **D:\DA100\Lab02A\Solution** folder*.

### Task 1: Configure the Salesperson query

In this task, you will configure the **Salesperson** query.

1. In the **Power Query Editor** window, in the **Queries** pane, select the **DimEmployee** query.

    ![Picture 1](Linked_image_Files/PowerBI_Lab03A_image1.png)

2. To rename the query, in the **Query Settings** pane (located at the right), in the **Name** box, replace the text with **Salesperson**, and then press **Enter**.

    *The query name will determine the model table name. It’s recommended to define concise, yet friendly, names*.

3. In the **Queries** pane, verify that the query name has updated.

    ![Picture 87](Linked_image_Files/PowerBI_Lab03A_image2.png)

    *You will now filter the query rows to retrieve only employees who are salespeople*.

4. To locate a specific column, on the **Home** ribbon tab, from inside the **Manage Columns** group, click the **Choose Columns** down-arrow, and then select **Go to Column**.

    ![Picture 88](Linked_image_Files/PowerBI_Lab03A_image3.png)

    *Tip: This technique is useful when a query contains many columns. Usually, you can simply horizontally scroll to locate the column*.

5. In the **Go to Column** window, to order the list by column name, click the **AZ** sort button, and then select **Name**.

    ![Picture 94](Linked_image_Files/PowerBI_Lab03A_image4.png)

6. Select the **SalesPersonFlag** column, and then click **OK**.

7. To filter the query, in the **SalesPersonFlag** column header, click the down-arrow, and then uncheck **FALSE**.

    ![Picture 95](Linked_image_Files/PowerBI_Lab03A_image5.png)

8. Click **OK**.

    ![Picture 96](Linked_image_Files/PowerBI_Lab03A_image6.png)

9. In the **Query Settings** pane, in the **Applied Steps** list, notice the addition of the **Filtered Rows** step.

    ![Picture 98](Linked_image_Files/PowerBI_Lab03A_image7.png)

    *Each transformation you create results in additional step logic. It’s possible to edit or delete steps. It’s also possible to select a step to preview the query results at that stage of transformation*.

10. To remove columns, on the **Home** ribbon tab, from inside the **Manage Columns** group, click the **Choose Columns** icon.

    ![Picture 99](Linked_image_Files/PowerBI_Lab03A_image8.png)

11. In the **Choose Columns** window, to uncheck all columns, uncheck the **(Select All Columns)** item.

    ![Picture 102](Linked_image_Files/PowerBI_Lab03A_image9.png)

12. To include columns, check the following six columns:

    * EmployeeKey

    * EmployeeNationalIDAlternateKey

    * FirstName

    * LastName

    * Title

    * EmailAddress

13. Click **OK**.

    ![Picture 104](Linked_image_Files/PowerBI_Lab03A_image10.png)

14. In the **Applied Steps** list, notice the addition of another query step.

    ![Picture 112](Linked_image_Files/PowerBI_Lab03A_image11.png)

15. To create a single name column, first select the **FirstName** column header.

16. While pressing the **Ctrl** key, select the **LastName** column.

    ![Picture 116](Linked_image_Files/PowerBI_Lab03A_image12.png)

17. Right-click either of the select column headers, and then in the context menu, select **Merge Columns**.

    ![Picture 117](Linked_image_Files/PowerBI_Lab03A_image13.png)

    *Many common transformations can be applied by right-clicking the column header, and then choosing them from the context menu. Note, however, that all transformations—and more—are available in the ribbon*.

18. In the **Merge Columns** window, in the **Separator** dropdown list, select **Space**.

19. In the **New Column Name** box, replace the text with **Salesperson**.

    ![Picture 119](Linked_image_Files/PowerBI_Lab03A_image14.png)

20. Click **OK**.

    ![Picture 5636](Linked_image_Files/PowerBI_Lab03A_image15.png)

21. To rename the **EmployeeNationalIDAlternateKey** column, double-click the **EmployeeNationalIDAlternateKey** column header.

22. Replace the text with **EmployeeID**, and then press **Enter**.

    *When instructed to rename columns, it’s important that you rename them exactly as described*.

23. Use the previous steps to rename the **EmailAddress** column to **UPN**.

    *UPN is an acronym for User Principal Name. The values in this column will be used when you configure row-level security in **Lab 05A***.

24. At the bottom-left, in the status bar, verify that the query has five columns and 18 rows.

    ![Picture 5638](Linked_image_Files/PowerBI_Lab03A_image16.png)

    *It’s important that you do not proceed if your query does not produce the correct result—it won’t be possible to complete later labs. If it doesn’t, refer back to the steps in this task to fix any problems*.

### Task 2: Configure the SalespersonRegion query

In this task, you will configure the **SalespersonRegion** query.

1. In the **Queries** pane, select the **DimEmployeeSalesTerritory** query.

    ![Picture 5639](Linked_image_Files/PowerBI_Lab03A_image17.png)

26. In the **Query Settings** pane, rename the query to **SalespersonRegion**.

27. To remove the last two columns, first select the **DimEmployee** column header.

28. While pressing the **Ctrl** key, select the **DimSalesTerritory** column header.

29. Right-click either of the select column headers, and then in the context menu, select **Remove Columns**.

    ![Picture 5640](Linked_image_Files/PowerBI_Lab03A_image18.png)

30. In the status bar, verify that the query has two columns and 39 rows.

    ![Picture 5641](Linked_image_Files/PowerBI_Lab03A_image19.png)

### Task 3: Configure the Product query

In this task, you will configure the **Product** query.

*When detailed instructions have already been provided in the labs, the lab steps will now provide more concise instructions. If you need the detailed instructions, you can refer back to other tasks*.

1. Select the **DimProduct** query.

    ![Picture 5643](Linked_image_Files/PowerBI_Lab03A_image20.png)

32. Rename the query to **Product**.

33. Locate the **FinishedGoodsFlag** column, and then filter the column to retrieve products that are finished goods (i.e. TRUE).

34. Remove all columns, except the following:

    * ProductKey

    * EnglishProductName

    * StandardCost

    * Color

    * DimProductSubcategory

35. Notice that the **DimProductSubcategory** column represents a related table (it contains **Value** links).

36. In the **DimProductSubcategory** column header, at the right of the column name, click the expand button.

    ![Picture 5644](Linked_image_Files/PowerBI_Lab03A_image21.png)

37. To uncheck all columns, uncheck the **(Select All Columns)** item.

38. Check the **EnglishProductSubcategoryName** and **DimProductCategory** columns.

    ![Picture 5646](Linked_image_Files/PowerBI_Lab03A_image22.png)

    *By selecting these two columns, a transformation will be applied to join to the **DimProductSubcategory** table, and then include these columns. The **DimProductCategory** column is, in fact, another related table*.

39. Uncheck the **Use Original Column Name as Prefix** checkbox.

    ![Picture 5647](Linked_image_Files/PowerBI_Lab03A_image23.png)

    *Query column names must always be unique. When checked, this checkbox would prefix each column with the expanded column name (in this case **DimProductSubcategory**). Because it’s known that the selected columns don’t collide with columns in the **Product** query, the option is deselected*.

40. Click **OK**.

    ![Picture 5648](Linked_image_Files/PowerBI_Lab03A_image24.png)

41. Notice that the transformation resulted in two columns, and that the **DimProductSubcategory** column has been removed.

42. Expand the **DimProductCategory**, and then introduce only the **EnglishProductCategoryName** column.

43. Rename the following four columns:

    * **EnglishProductName** to **Product**

    * **StandardCost** to **Standard Cost** (include a space)

    * **EnglishProductSubcategoryName** to **Subcategory**

    * **EnglishProductCategoryName** to **Category**

44. In the status bar, verify that the query has six columns and 397 rows.

    ![Picture 5651](Linked_image_Files/PowerBI_Lab03A_image25.png)

### Task 4: Configure the Reseller query

In this task, you will configure the **Reseller** query.

1. Select the **DimReseller** query.

    ![Picture 5653](Linked_image_Files/PowerBI_Lab03A_image26.png)

46. Rename the query to **Reseller**.

47. Remove all columns, except the following:

    * ResellerKey

    * BusinessType

    * RellerName

    * DimGeography

48. Expand the **DimGeography** column, to include only the following three columns:

    * City

    * StateProvinceName

    * EnglishCountryRegionName

    ![Picture 5656](Linked_image_Files/PowerBI_Lab03A_image27.png)

49. In the **Business Type** column header, click the down-arrow, and then review the items, and the incorrect spelling of warehouse.

    ![Picture 2](Linked_image_Files/PowerBI_Lab03A_image28.png)

  
‎ 

50. Right-click the **Business Type** column header, and then select **Replace Values**.

    ![Picture 4](Linked_image_Files/PowerBI_Lab03A_image29.png)

51. In the **Replace Values** window, configure the following values:

    * In the **Value to Find** box, enter **Ware House**

    * In the **Replace With** box, enter **Warehouse**

    ![Picture 5](Linked_image_Files/PowerBI_Lab03A_image30.png)

52. Click **OK**.

    ![Picture 6](Linked_image_Files/PowerBI_Lab03A_image31.png)

53. Rename the following four columns:

    * **BusinessType** to **Business Type** (include a space)

    * **ResellerName** to **Reseller**

    * **StateProvinceName** to **State-Province**

    * **EnglishCountryRegionName** to **Country-Region**

54. In the status bar, verify that the query has six columns and 701 rows.

    ![Picture 5657](Linked_image_Files/PowerBI_Lab03A_image32.png)

### Task 5: Configure the Region query

In this task, you will configure the **Region** query.

1. Select the **DimSalesTerritory** query.

    ![Picture 5659](Linked_image_Files/PowerBI_Lab03A_image33.png)

56. Rename the query to **Region**.

57. Apply a filter to the **SalesTerritoryAlternateKey** column to remove the value 0 (zero).

    ![Picture 5660](Linked_image_Files/PowerBI_Lab03A_image34.png)

58. Remove all columns, except the following:

    * SalesTerritoryKey

    * SalesTerritoryRegion

    * SalesTerritoryCountry

    * SalesTerritoryGroup

59. Rename the following three columns:

    * **SalesTerritoryRegion** to **Region**

    * **SalesTerritoryCountry** to **Country**

    * **SalesTerritoryGroup** to **Group**

60. In the status bar, verify that the query has four columns and 10 rows.

    ![Picture 5661](Linked_image_Files/PowerBI_Lab03A_image35.png)

### Task 6: Configure the Sales query

In this task, you will configure the **Sales** query.

1. Select the **FactResellerSales** query.

    ![Picture 5663](Linked_image_Files/PowerBI_Lab03A_image36.png)

62. Rename the query to **Sales**.

63. Remove all columns, except the following:

    * SalesOrderNumber

    * OrderDate

    * ProductKey

    * ResellerKey

    * EmployeeKey

    * SalesTerritoryKey

    * OrderQuantity

    * UnitPrice

    * TotalProductCost

    * SalesAmount

    * DimProduct

    *Recall in **Lab 02A** that a small percentage of **FactResellerSales** rows had missing **TotalProductCost** values. The **DimProduct** column has been included to retrieve the product standard cost, to fix the missing values*.

64. Expand the **DimProduct** column, and then include the **StandardCost** column.

65. To create a custom column, on the **Add Column** ribbon tab, from inside the **General** group, click **Custom Column**.

    ![Picture 5664](Linked_image_Files/PowerBI_Lab03A_image37.png)

66. In the **Custom Column** window, in the **New Column Name** box, replace the text with **Cost**.

    ![Picture 5665](Linked_image_Files/PowerBI_Lab03A_image38.png)

67. In the **Custom Column Formula** box, enter the following expression (after the equals symbol):

68. For your convenience, you can copy the expression from the **D:\DA100\Lab03A\Assets\Snippets.txt** file.

    **Power Query**

    ```
    if [TotalProductCost] = null then [OrderQuantity] * [StandardCost] else [TotalProductCost]
    ```

    *This expression tests if the **TotalProductCost** value is missing. If it is, produces a value by multiplying the **OrderQuantity** value by the **StandardCost** value; otherwise, it uses the existing **TotalProductCost** value*.

69. Click **OK**.

    ![Picture 5666](Linked_image_Files/PowerBI_Lab03A_image39.png)

70. Remove the following two columns:

    * TotalProductCost

    * StandardCost

71. Rename the following three columns:

    * **OrderQuantity** to **Quantity**

    * **UnitPrice** to **Unit Price** (include a space)

    * **SalesAmount** to **Sales**

72. To modify the column data type, in the **Quantity** column header, at the left of the column name, click the **1.2** icon, and then select **Whole Number**.

    ![Picture 5667](Linked_image_Files/PowerBI_Lab03A_image40.png)

    *Configuring the correct data type is important. When the column contains numeric value, it’s also important to choose the correct type if you expect to perform mathematic calculations*.

73. Modify the following three column data types to **Fixed Decimal Number**.

    * Unit Price

    * Sales

    * Cost

    ![Picture 5668](Linked_image_Files/PowerBI_Lab03A_image41.png)

    *The fixed decimal number data type stores values with full precision, and so requires more storage space that decimal number. It’s important to use the fixed decimal number type for financial values, or rates (like exchange rates)*.

74. In the status bar, verify that the query has 10 columns and 999+ rows.

    ![Picture 5669](Linked_image_Files/PowerBI_Lab03A_image42.png)

    *A maximum of 1000 rows will be loaded as preview data for each query*.

### Task 7: Configure the Targets query

In this task, you will configure the **Targets** query.

1. Select the **ResellerSalesTargets** query.

    ![Picture 5672](Linked_image_Files/PowerBI_Lab03A_image43.png)

76. Rename the query to **Targets**.

77. To unpivot the 12 month columns (**M01**-**M12**), first multi-select the **Year** and **EmployeeID** column headers.

    ![Picture 5673](Linked_image_Files/PowerBI_Lab03A_image44.png)

78. Right-click either of the select column headers, and then in the context menu, select **Unpivot Other Columns**.

    ![Picture 5674](Linked_image_Files/PowerBI_Lab03A_image45.png)

79. Notice that the column names now appear in the **Attribute** column, and the values appear in the **Value** column.

80. Apply a filter to the **Value** column to remove hyphen (-) values.

81. Rename the following two columns:

    * **Attribute** to **MonthNumber** (no space between the two words—it will be removed later)

    * **Value** to **Target**

    *You will now apply transformations to produce a date column. The date will be derived from the **Year** and **MonthNumber** columns. You will create the column by using the **Columns From Examples** feature*.

82. To prepare the **MonthNumber** column values, right-click the **MonthNumber** column header, and then select **Replace Values**.

    ![Picture 5676](Linked_image_Files/PowerBI_Lab03A_image46.png)

83. In the **Replace Values** window, in the **Value To Find** box, enter **M**.

    ![Picture 5677](Linked_image_Files/PowerBI_Lab03A_image47.png)

84. Click **OK**.

85. Modify the **MonthNumber** column data type to **Whole Number**.

    ![Picture 5678](Linked_image_Files/PowerBI_Lab03A_image48.png)

86. On the **Add Column** ribbon tab, from inside the **General** group, click The **Column From Examples** icon.

    ![Picture 5675](Linked_image_Files/PowerBI_Lab03A_image49.png)

87. Notice that the first row is for year **2017** and month number **7**.

88. In the **Column1** column, in the first grid cell, commence enter **7/1/2017**, and then press **Enter**.

    *The virtual machine uses US regional settings, so this date is in fact July 1, 2017*.

89. Notice that the grid cells update with predicted values.

    The feature has accurately predicted that you are combining values from two columns.

90. Notice also the formula presented above the query grid.

    ![Picture 5679](Linked_image_Files/PowerBI_Lab03A_image50.png)

91. To rename the new column, double-click the **Merged** column header.

92. Rename the column as **TargetMonth**.

    ![Picture 5680](Linked_image_Files/PowerBI_Lab03A_image51.png)

93. Click **OK**.

    ![Picture 5681](Linked_image_Files/PowerBI_Lab03A_image52.png)

94. Remove the following columns:

    * Year

    * MonthNumber

95. Modify the following column data types:

    * **Target** as fixed decimal number

    * **TargetMonth** as date

96. To multiply the **Target** values by 1000, select the **Target** column header, and then on the **Transform** ribbon tab, from inside the **Number Column** group, click **Standard**, and then select **Multiply**.

    ![Picture 5682](Linked_image_Files/PowerBI_Lab03A_image53.png)

97. In the **Multiply** window, in the **Value** box, enter **1000**.

    ![Picture 5683](Linked_image_Files/PowerBI_Lab03A_image54.png)

98. Click **OK**.

    ![Picture 5684](Linked_image_Files/PowerBI_Lab03A_image55.png)

99. In the status bar, verify that the query has three columns and 809 rows.

    ![Picture 5685](Linked_image_Files/PowerBI_Lab03A_image56.png)

### Task 8: Configure the ColorFormats query

In this task, you will configure the **ColorFormats** query.

1. Select the **ColorFormats** query.  
	![Picture 5687](Linked_image_Files/PowerBI_Lab03A_image57.png)

101. Notice that the first row contains the column names.

102. On the **Home** ribbon tab, from inside the **Transform** group, click **Use First Row as Headers**.  
    ![Picture 5688](Linked_image_Files/PowerBI_Lab03A_image58.png)

103. In the status bar, verify that the query has three columns and 10 rows.  
	![Picture 5689](Linked_image_Files/PowerBI_Lab03A_image59.png)

### Task 9: Update the Product query

In this task, you will update the **Product** query by merging the **ColorFormats** query.

1. Select the **Product** query.  
	![Picture 5690](Linked_image_Files/PowerBI_Lab03A_image60.png)

1. To merge the **ColorFormats** query, on the **Home** ribbon tab, from inside the **Combine** group, click **Merge Queries**.  
	![Picture 5654](Linked_image_Files/PowerBI_Lab03A_image61.png)  
	*Merging queries allows integrating data, in this case from different data sources (SQL Server and a CSV file)*.

1. In the **Merge** window, in the **Product** query grid, select the **Color** column header.  
	![Picture 5655](Linked_image_Files/PowerBI_Lab03A_image62.png)

1. Beneath the **Product** query grid, in the dropdown list, select the **ColorFormats** query.

1. In the **ColorFormats** query grid, select the **Color** column header.

1. When the **Privacy Levels** window opens, for each of the two data sources, in the corresponding dropdown list, select **Organizational**.  
	![Picture 5691](Linked_image_Files/PowerBI_Lab03A_image63.png)  
	*Privacy levels can be configured for data source to determine whether data can be shared between sources. Setting each data source as **Organizational** allows them to share data, if necessary. Note that Private data sources can never be shared with other data sources. It doesn’t mean that Private data cannot be shared; it means that the Power Query engine cannot share data between the sources*.

1. Click **Save**.  
	![Picture 5692](Linked_image_Files/PowerBI_Lab03A_image64.png)

1. In the **Merge** window, click **OK**.  
	![Picture 5693](Linked_image_Files/PowerBI_Lab03A_image65.png)

1. Expand the **ColorFormats** column to include the following two columns:
    * Background Color Format  
    * Font Color Format

	![Picture 5694](Linked_image_Files/PowerBI_Lab03A_image66.png)

1. In the status bar, verify that the query now has eight columns and 397 rows.  
	![Picture 5695](Linked_image_Files/PowerBI_Lab03A_image67.png)

### Task 10: Update the ColorFormats query

In this task, you will update the **ColorFormats** to disable its load.

1. Select the **ColorFormats** query.  
	![Picture 321](Linked_image_Files/PowerBI_Lab03A_image68.png)

115. In the **Query Settings** pane, click the **All Properties** link.  
	![Picture 322](Linked_image_Files/PowerBI_Lab03A_image69.png)

116. In the **Query Properties** window, uncheck the **Enable Load To Report** checkbox.  
	![Picture 323](Linked_image_Files/PowerBI_Lab03A_image70.png)  
	*Disabling the load means it will not load as a table to the data model. This is done because the query was merged with the Product query, which is enabled to lad to the data model*.

117. Click **OK**.  
	![Picture 324](Linked_image_Files/PowerBI_Lab03A_image71.png)

### Finish up

In this task, you will complete the lab.

1. Verify that you have eight queries, correctly named as follows:

    * Salesperson

    * SalespersonRegion

    * Product

    * Reseller

    * Region

    * Sales

    * Target

    * ColorFormats (which will not load to the data model)

119. To load the data model, on the **File** backstage view, select **Close &amp; Apply**.  
	![Picture 326](Linked_image_Files/PowerBI_Lab03A_image72.png)  
	*All load-enabled queries are now loaded to the data model*.

120. In the **Fields** pane (located at the right), notice the seven tables loaded to the data model.  
	![Picture 3](Linked_image_Files/PowerBI_Lab03A_image73.png)

121. Save the Power BI Desktop file.

122. Leave Power BI Desktop open.  
	*In the next lab, you will configure data model tables and relationships*.
