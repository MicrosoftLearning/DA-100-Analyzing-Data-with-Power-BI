

### Lab 10A

Creating a Power BI Dashboard

# Overview

**The estimated time to complete the lab is 45 minutes**

In this lab, you will create the **Sales Monitoring** dashboard.

In this lab, you learn how to:

* Pin visuals to a dashboard

* Use Q&A to create dashboard tiles

* Configure a dashboard tile alert

# Exercise 1: Create a Dashboard

In this exercise, you will create the **Sales Monitoring** dashboard. The completed dashboard will look like the following:  

![Picture 8](Linked_image_Files/PowerBI_Lab10A_image1.png)

### Task 1: Create a dashboard

In this task, you will create the **Sales Monitoring** dashboard.

1. In Edge, in the Power BI service, open the **Sales Report** report.

2. To create a dashboard and pin the logo image, hover the cursor over the Adventure Works logo.

3. At the top-right corner, click the pushpin.

	![Picture 2](Linked_image_Files/PowerBI_Lab10A_image2.png)

4. In the **Pin to Dashboard** window, in the **Dashboard Name** box, enter **Sales Monitoring**.

	![Picture 3](Linked_image_Files/PowerBI_Lab10A_image3.png)

5. Click **Pin**.

	![Picture 1](Linked_image_Files/PowerBI_Lab10A_image4.png)

6. Set the **Year** slicer to **FY2020**.

	![Picture 4](Linked_image_Files/PowerBI_Lab10A_image5.png)

7. Set the **Region** slicer to **Select All**.

	*When pinning visuals to a dashboard, they will use the current filter context. Once pinned, the filter context cannot be changed. For time-based filters, it’s a better idea to use a relative date slicer (or, Q&A using a relative time-based question)*.

8. Pin the **Sales and Profit Margin by Month** (column/line) visual to the **Sales Monitoring** dashboard.

9. Open the **Navigation** pane, and then open the **Sales Monitoring** dashboard.

	![Picture 5](Linked_image_Files/PowerBI_Lab10A_image6.png)

10. Notice that the dashboard has two tiles.

	![Picture 6](Linked_image_Files/PowerBI_Lab10A_image7.png)

11. To resize the logo tile, drag the bottom-right corner, and resize the tile to become one unit wide, and two units high.

	*Tile sizes are constrained into a rectangular shape. It’s only possible to resize into multiples of the rectangular shape*.

12. To add a tile based on a question, at the top-left of the dashboard, click **Ask a Question About Your Data**.

	![Picture 7](Linked_image_Files/PowerBI_Lab10A_image8.png)

13. You can use the Q&A feature to ask a question, and Power BI will respond will a visual.

14. Click any one of the suggested questions beneath the Q&A box, in gray boxes.

15. Review the response.

16. Remove all text from the Q&A box.

17. In the Q&A box, enter the following: **Sales YTD**

	![Picture 11](Linked_image_Files/PowerBI_Lab10A_image9.png)

18. Notice the response of **(Blank)**.

	![Picture 14](Linked_image_Files/PowerBI_Lab10A_image10.png)

	*Recall you added the **Sales YTD** measure in **Lab 06B**. This measure is Time Intelligence expression and it requires a filter on the **Date** table to produce a result*.

19. Extend the question with: **in year FY2020**.

	![Picture 12](Linked_image_Files/PowerBI_Lab10A_image11.png)

20. Notice the response is now **$33M**.

	![Picture 13](Linked_image_Files/PowerBI_Lab10A_image12.png)

21. To pin the response to the dashboard, at the top-right corner, click **Pin Visual**.

	![Picture 15](Linked_image_Files/PowerBI_Lab10A_image13.png)

22. When prompted to pin the tile to the dashboard, click **Pin**.

	![Picture 17](Linked_image_Files/PowerBI_Lab10A_image14.png)

	*There’s a possible bug that will only allow you to pin to a new dashboard. It’s because your Power BI session has reverted to your “My Workspace”. If this happens, do not pin to a new dashboard. Return to your **Sales Analysis** workspace, open the dashboard again, and recreate the Q&A question*.

23. To return to the dashboard, at the top-left corner, click **Exit Q&amp;A**.

	![Picture 16](Linked_image_Files/PowerBI_Lab10A_image15.png)

### Task 2: Edit tile details

In this task, you will edit the details of two tiles.

1. Hover the cursor over the **Sales YTD** tile, and then at the top-right of the tile, click the ellipsis, and then select **Edit Details**.

	![Picture 18](Linked_image_Files/PowerBI_Lab10A_image16.png)

25. In the **Tile Details** pane (located at the right), in the **Subtitle** box, enter **FY2020**.

	![Picture 19](Linked_image_Files/PowerBI_Lab10A_image17.png)

26. At the bottom of the pane, click **Apply**.

	![Picture 20](Linked_image_Files/PowerBI_Lab10A_image18.png)

27. Notice that the **Sales YTD** tile displays a subtitle.

	![Picture 21](Linked_image_Files/PowerBI_Lab10A_image19.png)

28. Edit the tile details for the **Sales, Profit Margin** tile.

29. In the **Tile Details** pane, in the **Functionality** section, check **Display Last Refresh Time**.

	![Picture 22](Linked_image_Files/PowerBI_Lab10A_image20.png)

30. Click **Apply**.

	![Picture 23](Linked_image_Files/PowerBI_Lab10A_image21.png)

31. Notice that the tile describes the last refresh time (which you did when refreshing the data model in Power BI Desktop).

Later in this lab, you’ll simulate a data refresh, and notice that the refresh time updates.

### Task 3: Configure an alert

In this task, you will configure a data alert.

1. Hover the cursor over the **Sales YTD** tile, click the ellipsis, and then select **Manage Alerts**.

	![Picture 24](Linked_image_Files/PowerBI_Lab10A_image22.png)

33. In the **Manage Alerts** pane (located at the right), click **Add Alert Rule**.

	![Picture 25](Linked_image_Files/PowerBI_Lab10A_image23.png)

34. In the **Threshold** box, replace the value with **35000000** (35 million).

	![Picture 26](Linked_image_Files/PowerBI_Lab10A_image24.png)

	*This configuration will ensure you’re notified whenever the tile updates to a value above 35 million*.

35. At the bottom of the pane, click **Save and Close**.

	![Picture 27](Linked_image_Files/PowerBI_Lab10A_image25.png)

	*In the next exercise, you’ll refresh the dataset. Typically, this should be done by using scheduled refresh, and Power BI could use a gateway to connect to the SQL Server database. However, due to constraints in the classroom setup, there is no gateway. So, you’ll open Power BI Desktop, perform a manual data refresh, and upload the file*.

# Exercise 2: Refresh the Dataset

In this exercise, you will first load sales order data for June 2020 into the **AdventureWorksDW2020** database, and then add your classroom partner’s account to the database.. You will then open your Power BI Desktop file, perform a data refresh, and then upload the file to your **Sales Analysis** workspace.

### Task 1: Update the lab database

In this task, you will run a PowerShell script to update data in the **AdventureWorksDW2020** database.

1. In File Explorer, inside the **D:\DA100\Setup** folder, right-click the **UpdateDatabase-2-AddSales.ps1** file, and then select **Run with PowerShell**.

	![Picture 28](Linked_image_Files/PowerBI_Lab10A_image26.png)

	37. When prompted to press any key to continue, press **Enter** again.

	*The **AdventureWorksDW2020** database now includes sales orders June 2020*.

38. Inside the **D:\DA100\Setup** folder, right-click the **UpdateDatabase-3-AddPartnerAccount.ps1** file, and then select **Run with PowerShell**.

39. When prompted, enter the account name of your classroom partner, and then press **Enter**.

	*You only need to enter their account name (all characters before the @ symbol). Choose somebody sitting near you—you will work together in pairs to complete **Lab 12A**, which covers sharing Power BI content*.

	*Their account name is added so you can test the row-level security. You partner is now Pamela Ansam-Wolfe, whose sales performance is measured by the sales of two sales territory regions: US Northwest and US Southwest*.

### Task 2: Refresh the Power BI Desktop file

In this task, you will open the Sales Analysis Power BI Desktop file, perform a data refresh, and then upload the file to your **Sales Analysis** workspace.

1. Open your **Sales Analysis** Power BI Desktop file, stored in the **D:\DA100\MySolution** folder.

	*When the file was published in **Lab 06B**, if you weren’t confident you completed the lab successfully you were advised to upload the solution file instead. If you uploaded the solution file, be sure now to open the solution file again now. It’s located in the **D:\DA100\Lab06B\Solution** folder*.

41. On the **Home** ribbon, from inside the **Queries** group, click **Refresh**.

	![Picture 30](Linked_image_Files/PowerBI_Lab10A_image27.png)

42. When the refresh completes, save the Power BI Desktop file.

43. Publish the file to your **Sales Analysis** workspace.

44. When prompted to replace the dataset, click **Replace**.

	![Picture 31](Linked_image_Files/PowerBI_Lab10A_image28.png)

	*The dataset in the Power BI service now has June 2020 sales data*.

45. Close Power BI Desktop.

46. In Edge, in the Power BI service, in your **Sales Analysis** workspace, notice that the **Sales Analysis** report was also published.

	This report was used to test the model a you developed it in **Lab 05A** and **Lab 06A**.

47. Remove the **Sales Analysis** report (not dataset).

# Exercise 3: Review the Dashboard

In this exercise, you will review the dashboard to notice updated sales, and that the alert was triggered.

### Task 1: Review the dashboard

In this task, you will review the dashboard to notice updated sales, and that the alert was triggered.

1. In Edge, in the Power BI service, open the **Sales Monitoring** dashboard.

49. In the **Sales, Profit Margin** tile, in the subtitle, notice that the data was refreshed **NOW**.

50. Notice also that there is now a column for **2020 Jun**.

	![Picture 33](Linked_image_Files/PowerBI_Lab10A_image29.png)

	*The alert on the **Sales YTD** tile should have triggered also. After a short while, the alert should notify you that sales now exceeds the configured threshold value*.

51. Notice that the **Sales YTD** tile has updated to **$37M**.

52. Verify that the **Sales YTD** tile displays an alert notification icon.

	*If you don’t see the notification, you might need to press **F5** to reload the browser. If you still don’t see the notification, wait some minutes longer*.

	![Picture 35](Linked_image_Files/PowerBI_Lab10A_image30.png)

	*Alert notifications appear on the dashboard tile, and can be delivered by email, and push notifications to mobile apps including the Apple Watch8*.
