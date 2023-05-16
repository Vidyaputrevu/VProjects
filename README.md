# VProjects

Build An Employee Travel Approval Application For Corporates

The Travel Application for Corporate using Salesforce is a project that involves developing a customized solution for managing corporate travel using the Salesforce platform. It includes features such as booking management, travel itinerary management, expense tracking, and reporting, all integrated within the Salesforce CRM. This system can be used by corporate travelers to simplify their travel booking and management processes, and help them stay organized while on the go. The application can also provide companies with data and analytics to optimize their travel policies and reduce expenses, all within the Salesforce environment.


Creating Developer Org
Creating a developer org in salesforce. 
 
1.	Go to developers.salesforce.com/ 
2.	Click on sign up. 
3.	On the sign-up form, enter the following details: 
1.	First name & Last name 
2.	Email 
3.	Role: Developer 
4.	Company: College Name 
5.	County: India 
6.	Postal Code: pin code 
7.	Username: should be a combination of your name and company 
        This need not be an actual email id, you can give anything in the format: 
        username@organization.com 

<img width="1440" alt="Screenshot 2023-05-16 at 2 10 49 PM" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/2136946b-92b7-47c4-a76f-67713332521b">
<img width="1440" alt="2" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/829a6efc-0698-4e41-899f-2b73d4a8976e">

Creation Of Department Object For Travel Approval App
For this Travel Approval we need to create 5 objects   Department, Employee Detail, Expense, Expense Items, and Travel Approval. The below steps will assist you in creating those objects. 
 
Create Department Object:
 
1.	Click on the gear icon and then select Setup. 
2.	Click on the object manager tab just beside the home tab. 
3.	After the above steps, have a look on the extreme right you will find a Create Dropdown click on that and select Custom Object. 
4.	On the Custom Object Definition page, create the object as follows: 
5.	Label: Department 
6.	Plural Label: Departments 
7.	Record Name: Department Name 
8.	Check the Allow Reports checkbox 
9.    Check the Allow Search checkbox 
10.   Click Save. 

In the same way create 4 more objects Employee Detail, Expense, Expense Items, and Travel Approval                 
 Note – 
1. While making Expense Object select data type “Auto Number” in “Enter Record Name  Label and Format” section. 
2. While making Employee Detail Object put “Employee Name” in “Enter Record Name  Label and Format” section. 

<img width="1440" alt="3" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/b28d62d1-758e-4a08-a1a8-c6e95c6d34af">


Custom Tab Creation
Now create a custom tab. Click the Home tab. 
 
1.	Enter Tabs in Quick Find and select Tabs. 
2.	Under Custom Object Tabs, click New. 
3.	For Object, select Department. 
4.	For Tab Style, select any icon. 
5.	Leave all defaults as is. Click Next, Next, and Save 
6.	In the same way create Tabs for all Custom Objects - Employee Detail, Expense, Expense Items, Travel Approval. 

<img width="1440" alt="4" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/66232bb9-c02c-43bb-b7a0-820397de87c9">




Create Travel Approval App
Create the Travel Approval app

From Setup, enter App Manager in the Quick Find and select App Manager.
Click New Lightning App.
Enter Travel Approval as the App Name, then click Next
Under App Options, leave the default selections and click Next.
Under Utility Items, leave as is and click Next.
From Available Items, select Department, Employee Detail, Expense, Expense Items, Travel Approval, Reports, and Dashboards and move them to Selected Items. Click Next.
From Available Profiles, select System Administrator and move it to Selected Profiles.Click Save & Finish.

<img width="1440" alt="5" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/23d93fad-19cf-42b8-abba-1a13f629b427">


Creation Of Fields For The Department Object:

1.Click the gear icon and select Setup. This launches Setup in a new tab. 
2.Click the Object Manager tab next to Home. 
3.Select Department 
4.Select Fields & Relationships from the left navigation 
5.Click New 
6.Select the Text as the Data Type, click Next. 
7.For Field Label, enter Department Code and enter 5 in Length. 
8.Click Next, Next, then Save & New. 
9.Follow above steps and create two more Text type field - District & State. 
10.Also, Provide Length 40 for both District and State field. 
11.Create URL type field & give “School website” as the field label. 

These are fields and their data types we need to create and make one by one – 

NOTE- See activity 2, 3, 4 below to create a lookup field, Roll-up summary field & Picklist field 
 
 Object Name         Field Name             Data Type  

1. Employee Detail-  Date of Birth          Date 
                     Gender                 Picklist (Male, Female) 
                     Department             Lookup (Department)(See activity 2 to create lookup) 
	 	                  Employee Id            Text (Length - 12) 
 	 	    
2. Expense-         Employee           	    Lookup (Employee Detail) 
                    Total Item              Rollup summary (Expense Item) 
 	 	    
3. Expense Item -   Expense             	    Master Detail (Expense) 
                    Expense Type     	       Pick List (Values are- Transport, Hotel, Meal, Others) 
	 	 	               Amount               	    Currency 
 
4. Travel Approval- Employee Name     	      Lookup (Employee Detail) 
	     	 	           Department           	   Lookup (Department) 
                    Destination state    	   Text (Length – 40) 
	 	 	               Purpose of trip      	   Text (Length – 256) 
	 	 	               Trip start date           Date 
	 	 	               Trip End date        	    Date 
	 	 	               Status                    Picklist (Values are- Approved, Rejected) 
                    
        NOTE- Make Trip Start Date and Trip End Date field required when making these field 






