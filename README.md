# VProjects

Building An Employee Travel Approval Application For Corporates

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




Creation Of Department Object For Travel Approval App:

For this Travel Approval we need to create 5 objects   
	Department
	Employee Detail
	Expense
	Expense Items and 
	Travel Approval. 

The below steps will assist you in creating those objects. 
 
 
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

<img width="1440" alt="6" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/38588bb1-6244-4a23-b715-b3c1b0e6a02b">




Data Import

From Setup, click the Home tab.

1)In the Quick Find box, enter Data Import and select Data Import Wizard.
2)Click Launch Wizard!
3)Click the Custom Objects tab and select the Departments object.
4)Select Add new records.
5)Click CSV and choose file Department_CSV which we made earlier. Click Next.
6)Since the field names in the CSV file (CSV Header) are the same as the field names in your object (Mapped Salesforce Object), the fields are automatically mapped. Click Next.

The next screen gives you a summary of your data import. Click Start Import.
Click OK on the popup.


<img width="1440" alt="7" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/a018acac-5a31-4ec9-b95a-793020187e96">




Creating A User In Salesforce


1.From Setup, in the Quick Find box, enter Users. 
2.Select Users. 
3.Click New User. 
4.Enter the First Name Travel Approval and Last Name manager and (Your) email address and a  unique username in the    
  form of an email address. By default, the username is the same as the email address. 
5.Select a User License as Salesforce. 

  NOTE- In the Developer edition  Salesforce license can only be used by 2 Users at a time in Dev Org, If you don’t find Salesforce   
  license then deactivate a user who has Salesforce license Or change the license type from Salesforce to any other. 

6.Select a profile as Standard user. 
7.Check Generate new password and notify the user immediately to have the user’s login name and a temporary password        
 emailed to your email. 
 
 
 <img width="1440" alt="2" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/151381cc-7c39-4e4b-ba50-7b882116440e">



Use Customization:

Customization refers to custom software development and coding to add robust features to your CRM platform. These features can be integrated with your business to have a scalable impact. 


Customize Travel Approval Object Page Layout
1. From the Object Manager, search for the Travel approval object  
2. click on page layouts and  click Travel Approval Layout 
3. Drag the Section from the top pane to the lower pane directly below the Information section. When dragging over the page, you get a visual indicator of where you can drop the new section. 
4. Name the section Trip Info, leave the rest of the settings at their default values, and  
5. Then click on OK. 
6. Drag Trip Start Date and Trip End Date, Status from the top pane into the left-hand column of the Trip Info 
  section. 
7. Drag the Destination State and Purpose of a trip from, department the top pane into the right-hand column of the Trip 
  Info section. 
8. Click Save. 


<img width="1440" alt="8" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/f4640f13-4b65-4b2e-9b47-2dee995804da">

<img width="1440" alt="9" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/6fae0293-c8b8-4fd5-a445-04ff4a2db210">




Add Business Logic To Travel App


Validation Rule - It can contain a formula or expression that evaluates the data in one or more fields & returns a value of true or false. Validation Rules also include an error message to display to the user when the rule returns a value true due to an invalid value/data. 

Formulae Fields - 1)First, we need to upload a zip file to your Salesforce environment that contains all the images we use. You should have 2)a file titled StatusImages.zip.
3)Click the setup
4)Click Static Resources in Quick Find & Click New.
5)Enter the following values for your static resource

Parameter	Value
Name		StatusImages
File		StatusImages.zip
Cache-Control	Private

Now, select the travel approval object.

Select Fields & Relationships, 
Click New
Select Formula data type, and Click Next.

Enter the following values:
Field Label: Status Indicator
Field Name: Status_Indicator (This automatically gets sent when you tab out of the Field Label field)
Formula Return Type: Tex

Click next & Copy and paste the following formula into the formula editor.

IF( ISPICKVAL( Status c c, 'Approved'), IMAGE("/resource/StatusImages/thumbs-up.png", "Accepted", 20, 20),
IF ( ISPICKVAL( Status c c, 'Rejected'), IMAGE("/resource/StatusImages/thumbs-down.png", "Rejected", 20, 20), IMAGE("/resource/StatusImages/draft.png", "In-Process", 20, 20)))

Click Next, Next, Save.

VALIDATION RULE:

<img width="1440" alt="10" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/6d838134-de3c-4cb6-abd3-c20d15e395e9">

FROMULA FIELD: 

<img width="1440" alt="11" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/de42994c-5c78-40b5-aab1-78ab14a13e53">



REPORTS:

Reports in Salesforce is a list of records that meet a particular criterion which gives an answer to a particular question. These records are displayed as a table that can be filtered or grouped based on any field. 


<img width="1440" alt="Screenshot 2023-05-16 at 2 05 30 PM" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/a60c4c2a-3823-4949-90d2-585ec65ddd18">


<img width="1440" alt="12" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/2a611345-bc12-4153-a183-9c7707f2c3a5">


<img width="1440" alt="13" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/b7872602-d2a6-4b57-9f6c-f7cb1537bdd8">



DASHBOARDS:

Dashboards let you curate data from reports using charts, tables, and metrics. If your colleagues need more information, then they're able to view your dashboard's data-supplying reports. Dashboard filters make it easy for users to apply different data perspectives to a single dashboard. 



<img width="1440" alt="14" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/f27c5a5a-3f4c-4d4c-9e45-1c309fa78285">


<img width="1440" alt="15" src="https://github.com/Vidyaputrevu/VProjects/assets/133752575/8a46537d-d366-46ed-b9b2-f0c5a1a48798">













![THANK YOU IMAGE](https://github.com/Vidyaputrevu/VProjects/assets/133752575/fdc274c1-0de1-4da2-a518-c10917095222)










