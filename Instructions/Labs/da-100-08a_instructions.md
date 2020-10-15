### Lab 08A

Designing a Report in Power BI Desktop, Part 1

# Overview

**The estimated time to complete the lab is 45 minutes**

In this lab, you will create a three-page report named **Sales Report**. You will then publish it to Power BI, whereupon you will open and interact with the report.

In this lab, you learn how to:

* Use Power BI Desktop to create a live connection

* Design a report

* Configure visual fields and format properties

# Exercise 1: Create a Report

In this exercise, you will create a three-page report named **Sales Report**.

### Task 1: Create a new file

In this task, you will create a live connection to the **Sales Analysis** dataset.

1. To open the Power BI Desktop, on the taskbar, click the Microsoft Power BI Desktop shortcut.

	![Picture 2](Linked_image_Files/PowerBI_Lab08A_image1.png)

2. At the top-right corner of the welcome screen, click **X**.

	![Picture 1](Linked_image_Files/PowerBI_Lab08A_image2.png)

3. Click the **File** ribbon tab to open the backstage view, and then select **Save**.

	![Picture 13](Linked_image_Files/PowerBI_Lab08A_image3.png)

4. In the **Save As** window, navigate to the **D:\DA100\Lab08a\Solution** folder.

5. In the **File Name** box, enter **Sales Report**.

	![Picture 14](Linked_image_Files/PowerBI_Lab08A_image4.png)

6. Click **Save**.

	![Picture 17](Linked_image_Files/PowerBI_Lab08A_image5.png)

### Task 2: Create a live connection

In this task, you will create a live connection to the **Sales Analysis** dataset.

1. To create a live connection, on the **Home** ribbon tab, from inside the **Data** group, click **Get Data**, down-arrow, and then select **Power BI Datasets**.

	![Picture 6](Linked_image_Files/PowerBI_Lab08A_image6.png)

8. In the **Select a Dataset to Create a Report** window, select the **Sales Analysis** dataset.

	![Picture 7](Linked_image_Files/PowerBI_Lab08A_image7.png)

9. Click **Create**.

	![Picture 9](Linked_image_Files/PowerBI_Lab08A_image8.png)

10. At the bottom-right corner, in the status bar, notice that the live connection has been established.

11. In the **Fields** pane, notice that the data model table are listed.

	*Power BI Desktop can no longer be used to develop the data model; in live connection mode, it’s only a report authoring tool. It is possible, however, to create measures—but they are measures that are only available within the report. You won’t add any report-scoped measures in this lab*.

12. Save the Power BI Desktop file.

	*Recall that you added the **Salespeople** role to the model in **Lab 05A**. Because you’re the owner of the Power BI dataset, the roles are not enforced. This explains why, in this lab, you can see all data*.

	*When you share reports and dashboards to non-owners of the dataset, their account (or a security group of which they’re a member) must be mapped to the **Salespeople** role. You will configure this before sharing content in **Lab 12A***.

### Task 3: Design page 1

In this task, you will design the first report page. When you’ve completed the design, the page will look like the following:  
	![Picture 40](Linked_image_Files/PowerBI_Lab08A_image9.png)

1. To rename the page, at the bottom-left, right-click **Page 1**, and then select **Rename**.

	![Picture 36](Linked_image_Files/PowerBI_Lab08A_image10.png)

	*Tip: You can also double-click the page name*.

14. Rename the page as **Overview**, and then press **Enter**.

	![Picture 37](Linked_image_Files/PowerBI_Lab08A_image11.png)

15. To add an image, on the **Insert** ribbon tab, from inside the **Elements** group, click **Image**.

	![Picture 10](Linked_image_Files/PowerBI_Lab08A_image12.png)

16. In the **Open** window, navigate to the **D:\DA100\Data** folder.

17. Select the **AdventureWorksLogo.jpg** file, and then click **Open**.

	![Picture 11](Linked_image_Files/PowerBI_Lab08A_image13.png)

18. Drag the image to reposition it at the top-left corner, and also drag the guide markers to resize it.

	![Picture 12](Linked_image_Files/PowerBI_Lab08A_image14.png)

19. To add a slicer, first de-select the image by clicking an empty area of the report page.

20. In the **Fields** pane, select the **Date | Year** field (not the **Year** level of the hierarchy).

21. Notice that a table of year values has been added to the report page.

22. To convert the visual from a table to a slicer, in the **Visualizations** pane, select the **Slicer**.

	![Picture 15](Linked_image_Files/PowerBI_Lab08A_image15.png)

23. To convert the slicer from a list to a dropdown, at the top-right of the slicer, click the down-arrow, and then select **Dropdown**.

	![Picture 18](Linked_image_Files/PowerBI_Lab08A_image16.png)

24. Resize and reposition the slicer so it sits beneath the image, and so it is the same width as the image.

	![Picture 19](Linked_image_Files/PowerBI_Lab08A_image17.png)

25. In the **Year** slicer, select **FY2020**, and then collapse the dropdown list.

	![Picture 20](Linked_image_Files/PowerBI_Lab08A_image18.png)

	*The report page is now filtered by year **FY2020***.

26. De-select the slicer by clicking an empty area of the report page.

27. Create a second slicer, based on the **Region | Region** field (not the **Region** level of the hierarch).

28. Leave the slicer as a list, and then resize and reposition the slicer beneath the **Year** slicer.

	![Picture 21](Linked_image_Files/PowerBI_Lab08A_image19.png)

29. To format the slicer, beneath the **Visualizations** pane, open the **Format** pane.

	![Picture 22](Linked_image_Files/PowerBI_Lab08A_image20.png)

30. Expand then **Selection Controls** group.

	![Picture 23](Linked_image_Files/PowerBI_Lab08A_image21.png)

31. Set the **Show “Select All” Option** to **On**.

	![Picture 24](Linked_image_Files/PowerBI_Lab08A_image22.png)

32. In the **Region** slicer, notice that the first item is now **Select All**.

	*When selected, this item either selects all, or de-selects all items. It makes it easier for report users to set the right filters*.

33. De-select the slicer by clicking an empty area of the report page.

34. To add a chart to the page, in the **Visualizations** pane, click the **Line and Stacked Column Chart** visual type.

	![Picture 25](Linked_image_Files/PowerBI_Lab08A_image23.png)

35. Resize and reposition the visual so it sits to the right of the logo, and so it fills the width of the report page.

	![Picture 26](Linked_image_Files/PowerBI_Lab08A_image24.png)

36. Drag the following fields into the visual:

	* Date | Month

	* Sales | Sales

37. In the visual fields pane (not the **Fields** pane—the visual fields pane is located beneath the **Visualizations** pane), notice that the fields are assigned to the **Shared Axis** and **Column Values** wells.

	![Picture 27](Linked_image_Files/PowerBI_Lab08A_image25.png)

	*By dragging visuals into a visual, they will be added to default wells. For precision, you can drag fields directly into the wells, as you will do now*.

38. From the **Fields** pane, drag the **Sales | Profit Margin** field into the **Line Values** well.

	![Picture 28](Linked_image_Files/PowerBI_Lab08A_image26.png)

39. Notice that the visual has 11 months only.

	*The last month of the year, 2020 June, does not have any sales (yet). By default, the visual has eliminated months with BLANK sales. You will now configure the visual to show all months*.

40. In the visual fields pane, in the **Shared Axis** well, for the **Month** field, click the down-arrow, and then select **Show Items With No Data**.

	![Picture 29](Linked_image_Files/PowerBI_Lab08A_image27.png)

41. Notice that the month **2020 June** now appears.

42. De-select the chart by clicking an empty area of the report page.

43. To add a chart to the page, in the **Visualizations** pane, click the **Map** visual type.

	![Picture 32](Linked_image_Files/PowerBI_Lab08A_image28.png)

44. Resize and reposition the visual so it sits beneath the column/line chart, and so it fills half the width of the report page.

	![Picture 33](Linked_image_Files/PowerBI_Lab08A_image29.png)

45. Add the following fields to the visual wells:

	* Location: **Region | Country**

	* Legend: **Product | Category**

	* Size: **Sales | Sales**

46. De-select the chart by clicking an empty area of the report page.

47. To add a chart to the page, in the **Visualizations** pane, click the **Stacked Bar Chart** visual type.

	![Picture 34](Linked_image_Files/PowerBI_Lab08A_image30.png)

48. Resize and reposition the visual so it fills the remaining report page space.

	![Picture 35](Linked_image_Files/PowerBI_Lab08A_image31.png)

49. Add the following fields to the visual wells:

	* Axis: **Product | Category**

	* Value: **Sales | Quantity**

50. To format the visual, open the **Format** pane.

	![Picture 38](Linked_image_Files/PowerBI_Lab08A_image32.png)

51. Expand the **Data Colors** group, and then set the **Default Color** property to a suitable color (in contrast to the column/line chart).

52. Set the **Data Labels** property to **On**.

	![Picture 39](Linked_image_Files/PowerBI_Lab08A_image33.png)

53. Save the Power BI Desktop file.

	*The design of the first page is now complete*.

  
‎ 

### Task 4: Design page 2

In this task, you will design the second report page. When you’ve completed the design, the page will look like the following:

![Picture 41](Linked_image_Files/PowerBI_Lab08A_image34.png)

*When detailed instructions have already been provided in the labs, the lab steps will now provide more concise instructions. If you need the detailed instructions, you can refer back to other tasks*.

1. To create a new page, at the bottom-left, click the plus icon.

	![Picture 42](Linked_image_Files/PowerBI_Lab08A_image35.png)

55. Rename the page to **Profit**.

	![Picture 43](Linked_image_Files/PowerBI_Lab08A_image36.png)

56. Add a slicer based on the **Region | Region** field.

57. Use the **Format** pane to enable the “Select All” option (in the **Selection Controls** group).

58. Resize and reposition the slicer so it sits at the left side of the report page, and so it is about half the page height.

	![Picture 44](Linked_image_Files/PowerBI_Lab08A_image37.png)

59. Add a matrix visual, and resize and reposition it so it fills the remaining space of the report page

	![Picture 45](Linked_image_Files/PowerBI_Lab08A_image38.png)

60. Add the **Date | Fiscal** hierarchy to the matrix **Rows** well.

	![Picture 46](Linked_image_Files/PowerBI_Lab08A_image39.png)

61. Add the following five **Sales** table fields to the **Values** well:

	* Orders (from the **Counts** folder)

	* Sales

	* Cost

	* Profit

	* Profit Margin

	![Picture 3](Linked_image_Files/PowerBI_Lab08A_image40.png)

62. In the **Filters** pane (located at the left of the **Visualizations** pane), notice the **Filter On This Page** well (you may need to scroll down).

	![Picture 57](Linked_image_Files/PowerBI_Lab08A_image41.png)

63. From the **Fields** pane, drag the **Product | Category** field into the **Filter On This Page** well.

64. Inside the filter card, at the top-right, click the arrow to collapse the card.

	![Picture 58](Linked_image_Files/PowerBI_Lab08A_image42.png)

	*Fields added to the **Filters** pane can achieve the same result as a slicer. One difference is they don’t take up space on the report page. Another difference is that they can be configured for more advanced filtering requirements*.

65. Add each of the following **Product** table fields to the **Filter On This Page** well, collapsing each, directly beneath the **Category** card:

	* Subcategory

	* Product

	* Color

	![Picture 60](Linked_image_Files/PowerBI_Lab08A_image43.png)

66. To collapse the **Filters** pane, at the top-right of the pane, click the arrow.

	![Picture 68](Linked_image_Files/PowerBI_Lab08A_image44.png)

67. Save the Power BI Desktop file.

	The design of the second page is now complete.

### Task 5: Design page 3

In this task, you will design the third and final report page. When you’ve completed the design, the page will look like the following:  
	![Picture 69](Linked_image_Files/PowerBI_Lab08A_image45.png)

1. Create a new page, and then rename it as **My Performance**.

	*Recall that row-level security was configured to ensure users only ever see data for their sales regions and targets. When this report is distributed to salespeople, they will only ever see their sales performance results*.

69. To simulate the row-level security filters during report design and testing, add the **Salesperson (Performance) | Salesperson** field to the **Filters** pane, inside the **Filters On This Page** well.

70. In the filter card, scroll down the list of salespeople, and then check **Michael Blythe**.

	![Picture 73](Linked_image_Files/PowerBI_Lab08A_image46.png)

	*You will be instructed to delete this filter before you distribute the report in an app in **Lab 12A***.

71. Add a dropdown slicer based on the **Date | Year** field, and then resize and reposition it so it sits at the top-left corner of the page.

	![Picture 70](Linked_image_Files/PowerBI_Lab08A_image47.png)

72. In the slicer, select **FY2019**.

	![Picture 71](Linked_image_Files/PowerBI_Lab08A_image48.png)

73. Add a **Multi-row Card** visual, and then resize and reposition it so it sits to the right of the slicer and fills the remaining width of the page.

	![Picture 72](Linked_image_Files/PowerBI_Lab08A_image49.png)

	![Picture 74](Linked_image_Files/PowerBI_Lab08A_image50.png)

74. Add the following four fields to the visual:

	* Sales | Sales

	* Targets | Target

	* Targets | Variance

	* Targets | Variance Margin

75. Format the visual:

	* In the **Data Labels** group, increase the **Text Size** property to **28pt**

	* In the **Background** group, set the **Color** to a light gray color

	![Picture 79](Linked_image_Files/PowerBI_Lab08A_image51.png)

76. Add a **Clustered Bar Chart** visual, and then resize and reposition it so it sits beneath the multi-row card visual and fills the remaining height of the page, and half the width of the multi-row card visual.

	![Picture 77](Linked_image_Files/PowerBI_Lab08A_image52.png)

	![Picture 78](Linked_image_Files/PowerBI_Lab08A_image53.png)

77. Add the following fields to the visual wells:

	* Axis: **Date | Month**

	* Value: **Sales | Sales** and **Targets | Target**

	![Picture 80](Linked_image_Files/PowerBI_Lab08A_image54.png)

78. To create a copy of the visual, press **Ctrl+C**, and then press **Ctrl+V**.

79. Position the copied visual to the right of the original visual.

	![Picture 82](Linked_image_Files/PowerBI_Lab08A_image55.png)

80. To modify the visualization type, in the **Visualizations** pane, select **Clustered Column Chart**.

	![Picture 81](Linked_image_Files/PowerBI_Lab08A_image56.png)

	*It’s now possible to see the same data expressed by two different visualization types. This isn’t a good use of the page layout, but you will improve it in **Lab 09A** by superimposing the visuals. By adding buttons to the page, you will allow the report user to determine which of the two visuals is visible*.

	*The design of the third and final page is now complete*.

### Task 6: Publish the report

In this task, you will publish the report.

1. Select the **Overview** page.

82. Save the Power BI Desktop file.

83. On the **Home** ribbon tab, from inside the **Share** group, click **Publish**.

	![Picture 64](Linked_image_Files/PowerBI_Lab08A_image57.png)

84. Publish the report to your **Sales Analysis** workspace.

85. Leave Power BI Desktop open.

	*In the next exercise, you will explore the report in the Power BI service*.

# Exercise 2: Explore the Report

In this exercise, you will explore the **Sales Report** in the Power BI service.

### Task 1: Explore the report

In this task, you will explore the **Sales Report** in the Power BI service.

1. In the Edge, in the Power BI service, in the **Navigation** pane, review the contents of your **Sales Analysis** workspace, and then click the **Sales Report** report.

	![Picture 83](Linked_image_Files/PowerBI_Lab08A_image58.png)

	*The report publication has added a report to your workspace. If you don’t see it, press **F5** to reload the browser, and then expand the workspace again*.

87. In the **Regions** slicer, while pressing the **Ctrl** key, select multiple regions.

88. In the column/line chart, select any month column to cross filter the page.

89. While pressing the **Ctrl** key, select an additional month.

	*By default, cross filtering filters the other visuals on the page*.

90. Notice that the bar chart is filtered and highlighted, with the bold portion of the bars representing the filtered months.

91. Hover the cursor over the visual, and then at the top-right, click the filter icon.

	![Picture 88](Linked_image_Files/PowerBI_Lab08A_image59.png)

	*The filter icon allows you to understand all filters that are applied to the visual, including slicers and cross filters from other visual*.

92. Hover the cursor over a bar, and then notice the tooltip information.

93. To undo the cross filter, in the column/line chart, click an empty area of the visual.

94. Hover the cursor over the map visual, and then at the top-right, click the **In Focus** icon.

	![Picture 85](Linked_image_Files/PowerBI_Lab08A_image60.png)

	*In focus mode zooms the visual to full page size*.

95. Hover the cursor over different segments of the pie charts to reveal tooltips.

96. To return to the report page, at the top-left, click **Back to Report**.

	![Picture 86](Linked_image_Files/PowerBI_Lab08A_image61.png)

97. Hover the cursor over the map visual again, and then click the ellipsis (…), and notice the menu options.

	![Picture 87](Linked_image_Files/PowerBI_Lab08A_image62.png)

98. Try out each of the options.

99. At the left, in the **Pages** pane, select the **Profit** page.

	![Picture 84](Linked_image_Files/PowerBI_Lab08A_image63.png)

100. Notice that the **Region** slicer has a different selection to the **Region** slicer on the Overview page.  
	*The slicers are not synchronized. In the next lab, you will modify the report design to ensure they sync between pages*.

101. In the **Filters** pane (located at the right), expand a filter card, and apply some filters.      
*The **Filters** pane allows you to define more filters than could possibly fit on a page as slicers*.

102. In the matrix visual, use the plus (+) button to expand into the **Fiscal** hierarchy.

103. Select the **My Performance** page.  
	![Picture 89](Linked_image_Files/PowerBI_Lab08A_image64.png)

104. At the top-right on the menu bar, click View, and then select Full Screen.  
	![Picture 90](Linked_image_Files/PowerBI_Lab08A_image65.png)

105. Interact with the page by modifying the slicer, and cross filtering the page.

106. At the bottom-left, notice the commands to change page, navigate backwards or forwards between pages, or to exit full screen mode.

107. Exit full screen mode.  
	![Picture 91](Linked_image_Files/PowerBI_Lab08A_image66.png)

108. To return to the workspace, in the breadcrumb trail, click your workspace name.  
	![Picture 92](Linked_image_Files/PowerBI_Lab08A_image67.png)

109. Leave the Edge browser window open.  
	*You will enhance the report design with advanced features in **Lab 09A***.
