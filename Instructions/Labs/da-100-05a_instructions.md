

### Lab 05A

Advanced Data Modeling in Power BI Desktop

# Overview

**The estimated time to complete the lab is 45 minutes**

In this lab, you will create a many-to-many relationship between the **Salesperson** table and the **Sales** table. You will also enforce row-level security to ensure that a salesperson can only analyze sales data for their assigned region(s).

In this lab, you learn how to:

* Configure many-to-many relationships

* Enforce row-level security

# Exercise 1: Create a Many-to many Relationship

In this exercise, you will create a many-to-many relationship between the **Salesperson** table and the **Sales** table.

If you’re not confident you completed the previous lab successfully, you can open the previous lab’s solution file, which is found in the **D:\DA100\Lab04A\Solution** folder.

### Task 1: Create a many-to-many relationship

In this task, you will create a many-to-many relationship between the **Salesperson** table and the **Sales** table.

1. In Power BI Desktop, in Report view, in the **Fields** pane, check the follow two fields to create a table visual:

	* Salesperson | Salesperson

	* Sales | Sales

	![Picture 1](Linked_image_Files/PowerBI_Lab05A_image1.png)

	*The table displays sales made by each salesperson. However, there is another relationship between salespeople and sales. Some salespeople belong to one, two, or possibly more sales regions. In addition, sales regions can have multiple salespeople assigned to them*.

	*From a performance management perspective, a salesperson’s sales (based on their assigned territories) need to be analyzed and compared with sales targets. In this exercise, you will create relationships to support this analysis*.

2. Notice that Michael Blythe has sold almost $9 million.

3. Switch to Model view.

4. Use the drag-and-drop technique to create the following two model relationships:

	* **Salesperson | EmployeeKey** to **SalespersonRegion | EmployeeKey**

	* **Region | SalesTerritoryKey** to **SalespersonRegion | SalesTerritoryKey**

	*The **SalespersonRegion** table can be considered to be a bridging table*.

5. Switch to Report view, and then notice that the visual has not updated—the sales result for Michael Blythe has not changed.

6. Switch back to Model view, and then follow the relationship filter directions (arrowhead) from the **Salesperson** table.

	*Consider this: the **Salesperson** table filters the **Sales** table. It also filters the **SalespersonRegion** table, but it does not continue to propagate to the **Region** table (the arrowhead is pointing the wrong way)*.

	![Picture 380](Linked_image_Files/PowerBI_Lab05A_image2.png)

7. To edit the relationship between the **Region** and **SalespersonRegion** tables, double-click the relationship.

8. In the **Edit Relationship** window, in the **Cross Filter Direction** dropdown list, select **Both**.

9. Check the **Apply Security Filter in Both Directions** checkbox.

	*This setting will ensure that bi-directional filtering is applied when row-level security is being enforced. You will configure a security role in the next exercise*.

	![Picture 381](Linked_image_Files/PowerBI_Lab05A_image3.png)

10. Click **OK**.

	![Picture 335](Linked_image_Files/PowerBI_Lab05A_image4.png)

11. Notice that the relationship has a double arrowhead.

	![Picture 382](Linked_image_Files/PowerBI_Lab05A_image5.png)

12. Switch to Report view, and then notice that the sales values have not changed.

	*The issue now relates to the fact that there are two possible filter propagation paths between the **Salesperson** and **Sales** tables. This ambiguity is internally resolved, based on a “least number of tables” assessment. To be clear, you should not design models with this type of ambiguity—it will be addressed in part in this lab, and by the next lab*.

13. Switch to Model view.

14. To force filter propagation via the bridging table, double-click the relationship between the **Salesperson** and **Sales** tables.

15. In the **Edit Relationship** window, uncheck the **Make This Relationship Active** checkbox.

	![Picture 383](Linked_image_Files/PowerBI_Lab05A_image6.png)

16. Click **OK**.

	![Picture 5696](Linked_image_Files/PowerBI_Lab05A_image7.png)

	*The filter propagation is now forced to take the only active path*.

17. In the diagram, notice that the inactive relationship is represented by a dashed line.

	![Picture 5697](Linked_image_Files/PowerBI_Lab05A_image8.png)

18. Switch to Report view, and then notice that the sales for Michael Blythe is now nearly $22 million.

	![Picture 5698](Linked_image_Files/PowerBI_Lab05A_image9.png)

19. Notice also, that the sales for each salesperson—if added—would exceed the total.

	*This observation is a many-to-many relationships, due to the double, triple, etc. counting of regional sales results. Consider Brian Welcker, the second salesperson listed. His sales amount equals the total sales amount. It’s the correct result simply due to the fact the he’s the Director of Sales; his sales are measured by the sales of all regions*.

	*While the many-to-many relationship is now working, it’s now not possible to analyze sales made by a salesperson (the relationship is inactive). In the next lab, you’ll introduce a calculated table that will represent salesperson for performance analysis (of their regions)*.

20. Switch to Modeling view, and then in the diagram, select the **Salesperson** table.

21. In the **Properties** pane, in the **Name** box, replace the text with **Salesperson (Performance)**.

	*The renamed table now reflects its purpose: it is used to report and analyze the performance of salespeople based on the sales of their assigned sales regions*.

### Task 2: Relate the Targets table

In this task, you will create a relationship to the **Targets** table

1. Create a relationship from the **Salesperson (Performance) | EmployeeID** column and the **Targets | EmployeeID** column.

2. In Report view, add the **Targets | Target** field to the table visual.

	Widen the table visual to reveal all data. 

	![Picture 5699](Linked_image_Files/PowerBI_Lab05A_image10.png)

3. It’s now possible to visualize sales and targets—but take care, for two reasons. First, there is no filter on a time period, and so targets also including future target values. Second, targets are not additive, and so the total should not be displayed. They can either disabled by using a visual formatting property or removed by using calculation logic. You’ll write a target measure in **Lab 06B** that will return BLANK when more than one salesperson is filtered.

# Exercise 2: Enforce row-level security

In this exercise, you will enforce row-level security to ensure a salesperson can only ever see sales made in their assigned region(s).

### Task 1: Enforce row-level security

In this task, you will enforce row-level security to ensure a salesperson can only ever see sales made in their assigned region(s).

1. Switch to Data view.

	![Picture 5701](Linked_image_Files/PowerBI_Lab05A_image11.png)

2. In the **Fields** pane, select the **Salesperson (Performance)** table.

3. Review the data, noticing that Michael Blythe (EmployeeKey 281) has been assigned your Power BI account (**UPN** column).

	*Recall that Michael Blythe is assigned to three sales regions: US Northeast, US Central, and US Southeast*.

4. Switch to Report view.

5. On the **Modeling** ribbon tab, from inside the **Security** group, click **Manage Roles**.

	![Picture 5700](Linked_image_Files/PowerBI_Lab05A_image12.png)

6. In the **Manage Roles** window, click **Create**.

	![Picture 5702](Linked_image_Files/PowerBI_Lab05A_image13.png)

7. In the box, replace the selected text with the name of the role: **Salespeople**, and then press **Enter**.

	![Picture 5703](Linked_image_Files/PowerBI_Lab05A_image14.png)

8. To assign a filter, for the **Salesperson (Performance)** table, click the ellipsis (…) character, and then select **Add Filter | [UPN]**.

	![Picture 5704](Linked_image_Files/PowerBI_Lab05A_image15.png)

9. In the **Table Filter DAX Expression** box, modify the expression by replacing **“Value”** with **USERPRINCIPALNAME()**.

	![Picture 5705](Linked_image_Files/PowerBI_Lab05A_image16.png)

	*USERNAME() is a Data Analysis Expressions (DAX) function that retrieves the authenticated user. This means that the **Salesperson (Performance)** table will filter by the User Principal Name (UPN) of the user querying the model*.

10. Click **Save**.

	![Picture 5706](Linked_image_Files/PowerBI_Lab05A_image17.png)

11. To test the security role, on the **Modeling** ribbon tab, from inside the **Security** group, click **View As**.

	![Picture 5708](Linked_image_Files/PowerBI_Lab05A_image18.png)

12. In the **View as Roles** window, check the **Other User** item, and then in the corresponding box, enter your account name.

	*Tip: You can copy it from the **MySettings.txt** file*.

13. Check the **Salespeople** role.

	![Picture 5709](Linked_image_Files/PowerBI_Lab05A_image19.png)

	*This configuration results in using the **Salespeople** role and impersonating the user with your account name*.

14. Click **OK**.

	![Picture 5710](Linked_image_Files/PowerBI_Lab05A_image20.png)

15. Notice the yellow banner above the report page, describing the test security context.

	![Picture 5711](Linked_image_Files/PowerBI_Lab05A_image21.png)

16. In the table visual, notice that only the salesperson **Michael Blythe** is listed.

	![Picture 5713](Linked_image_Files/PowerBI_Lab05A_image22.png)

17. To stop testing, at the right of the yellow banner, click **Stop Viewing**.

	![Picture 5712](Linked_image_Files/PowerBI_Lab05A_image23.png)

	*When the Power BI Desktop file is published to the Power BI service, there will be a post-publication task to map security principals to the **Salespeople** role. You will do this in **Lab 06B***.

### Finish up

In this task, you will complete the lab.

1. Save the Power BI Desktop file.

2. Leave Power BI Desktop open.

	*In the next lab, you will enhance the data model with calculations using DAX*.
