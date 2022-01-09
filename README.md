# Employeedata_SampleProject
--CREATE an employee table
CREATE TABLE dbo.Employeedata
(Emp_ID int,
Emp_name Varchar(20) not null,
Designation varchar(20) not null,
Department varchar(20) not null,
Location varchar(20) not null
);

Alter table Employeedata
Alter column DOJ varchar(20) not null;

--Insert values to the above created table
INSERT INTO dbo.Employeedata VALUES
(0001, 'Ajay Rai', 'Manager', 'Finance', 'Delhi', '01-01-2022'),
(0002, 'Neelam Singh','DGM', 'Opersations', 'Mumbai','20-12-2021'),
(0007, 'Rima Sen', 'Sr.MGR', 'Marketing', 'Mumbai', '16-11-2021'),
(0010 , 'Rahul Nayak', 'Executive', 'Management', 'Bangalore','05-01-2022'),
(0020, 'Mayra Roy','Intern', 'Marketing', 'Delhi','03-01-2022')
;
Select *
From dbo.Employeedata

--Clearing Data By Removing Duplicate Emp_ID
Delete 
From dbo.Employeedata
where Emp_ID in (Select Emp_ID From dbo.Employeedata
				group by Emp_ID 
				Having (count(Emp_ID)>1)
				)

Select *
From dbo.Employeedata

Select *
From dbo.Employeedata
Where Department = 'Marketing'
order by DOJ ASC
