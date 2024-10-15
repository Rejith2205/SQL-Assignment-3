### **SQL DML COMMANDS--Assignment -3**
**Create a table named Managers with fields : Manager_Id  First_name   Last_Name, DOB ,Age ->Gender Department Salary -> NOT NULL. Use check constraint** 
 * 1 Insert 10 rows
 * 2 Write a query that retrieves the name and date of birth of the manager with Manager_Id.
 * 3 Write a query to display the annual income of all managers.
 * 4 Write a query to display records of all managers except ‘Soumya’.
 * 5 Write a query to display details of managers whose department is IT and earns more than 25000 per month.
 * 6 Write a query to display details of managers whose salary is between 10000 and 35000**

### **specify which database to be used**

**USE EMPLOYEE;**
![USE employee](https://github.com/user-attachments/assets/5d8dbd35-44d6-43e5-91c2-2c3da5ffe9ae)

### **CREATE TABLE MANAGERS**
**Create table Managers
		(Manager_ID Varchar (10) UNIQUE,
		First_Name Varchar (30) NOT NULL,
		Last_Name Varchar(30) NOT NULL,
DOB date,Age int,Gender varchar(10) NOT NULL , CHECK (Gender='Male' or Gender ='Female' or Gender = 'Transgender'),
Department varchar(15) NOT NULL, CHECK( Department = 'IT' or Department = 'FINANCE'  OR Department = 'HR'),
		Salary int NOT NULL,CHECK (Salary>=10000 AND Salary <=100000),
		primary key (Manager_ID));**

![Table creation](https://github.com/user-attachments/assets/c0bcbd01-53fc-46bc-b666-1f05a2f927ab)

### **INSERTED THE SINGLE ROW INTO THE TABLE WHICH SATIFIES ALL THE CONDITIONS OF THE CONSTRAINTS**

**INSERT INTO managers
(Manager_ID,First_Name,Last_Name,DOB,Age,Gender, Department,Salary)        VALUES
        		('IT012345','RAJU','Unni','19750125','49','Male','IT','35000');**

![Insert first row](https://github.com/user-attachments/assets/603e1c4a-2501-4340-89a8-7f3946eb3cf1)

### **INSERTED  ANOTHER ROW INTO THE TABLE WITHOUT CHANGING THE Manager_ID,the new record has inserted into the table since the primarykey condition has not satisfied with the same Manager_id**

**INSERT INTO managers
		(Manager_ID,First_Name,Last_Name,DOB,Age,Gender, Department,Salary)
        VALUES
       		 ('IT012345','Manu','Narayan','19850125','39','Male','IT','40000');**

![Primary key constraint](https://github.com/user-attachments/assets/8ca4b757-3630-42fe-b247-0b481690a817)

### **INSERTED  ANOTHER ROW INTO THE TABLE  CHANGING THE Manager_ID and all other fileds except   DOB & Age for which the value has not passed to the table. However the record hass inserted   sucessfully to the table since the constraints NOT NULL was not applied to these two fields**

  **INSERT INTO managers
		(Manager_ID,First_Name,Last_Name,Gender, Department,Salary)
        VALUES
      		 ('IT012347','Anu','Narayan','Female','IT','45000');**


![Not Null field without insertion](https://github.com/user-attachments/assets/8f49b61e-0927-4d91-b2f8-449169527726)

### *INSERTED  ANOTHER ROW INTO THE TABLE  CHANGING THE Manager_ID and all other fileds.    The value passed to the field 'department' as 'Man'. The row has not inserted into the  table since the Check value has not met*    

**INSERT INTO managers
		(Manager_ID,First_Name,Last_Name,DOB,Age,Gender, Department,Salary)
        VALUES
      		  ('IT012348','Tony','Thomas','19800502','44','Man','IT','50000');**
          
![Check constraint Gender verified](https://github.com/user-attachments/assets/24599e87-a552-4cfb-ab6c-8e9f698bc620)

### *INSERTED  ANOTHER 6 ROW INTO THE TABLE  CHANGING THE Manager_ID and all other fileds.    The value has updated successfully to the table*                

              
  **INSERT INTO managers
		(Manager_ID,First_Name,Last_Name,DOB,Age,Gender, Department,Salary)
        VALUES
      	('FINA012349','Soumya','Manoj','19850526','39','Female','FINANCE','65000'),
         	 ('HR012350','Renju','Rajan','19890403','35','Female','HR','75000'),
          	 ('HR012351','Somu','Sam','19900321','34','Male','HR','80000'),
           	 ('FINA012352','Emily','Liju','19820502','42','FEmale','FINANCE','95000'),
            	 ('IT012353','Soji','Jimmy','19990102','25','Female','IT','65000'),
            	  ('IT012354','Deepu','Thomas','19920128','32','Male','IT','49000');**


![Inserting 6 rows](https://github.com/user-attachments/assets/a166c3fc-e21d-401d-8175-3500cf609dd4)

### *Query to retrieve the names and date of birth of the manager with manager id*     
   
**SELECT Manager_id,
        CONCAT (First_name, Last_name) as Name,
        DOB from  Managers;**
        
![retrieves name data of birth manager id](https://github.com/user-attachments/assets/935310da-d6ae-4e24-97b5-b4cc87b94a45)

### *Write a query to display records of all managers except ‘SOUMYA’*

**SELECT * FROM MANAGERS
        WHERE
 FIRST_NAME NOT LIKE 'SOUMYA%'**

![soumya](https://github.com/user-attachments/assets/28bb5eff-15a0-4281-aa98-cf66db37f279)

### *Write a query to display details of managers whose department is IT and earns more than 25000 per month.*

**SELECT * FROM MANAGERS       
       WHERE DEPARTMENT LIKE'IT%'
       AND SALARY >'25000';**

![department IT](https://github.com/user-attachments/assets/93cec2d0-ce5d-4eed-b033-e7e0d318876a)

### *Write a query to display details of managers whose salary is between 10000 and 35000.*

**SELECT * FROM MANAGERS
       WHERE SALARY BETWEEN '10000'AND '35000';**

![salary 10k-35k](https://github.com/user-attachments/assets/e597e201-d031-4087-b3e7-03a4aee338eb)










