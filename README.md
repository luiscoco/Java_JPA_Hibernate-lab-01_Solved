# Java_JPA_Hibernate-lab-01_Solved

## Exercise 1

**Entity definition**

**Goal**

Learn how to describe an entity in terms of Java Persistence API

**Subject**

You need to describe the Company entity that is mapped onto two database tables: Company and CompanyDetail. 

Here are the tables DDLs:

```
CREATE TABLE Company (
	
  Company_id		INT PRIMARY KEY,

  Company_name	VARCHAR(50)

);
```

```
CREATE TABLE CompanyDetail (

  Company_id			INT PRIMARY KEY,

CompanyDetail_address	VARCHAR(100)

);
```

Attributes of Company entity are mapped to tables’ fields as follows:

o	Company.id  Company.Company_id

o	Company.name  Company.Company_name

o	Company.address  CompanyDetail.CompanyDetail_address

**Description**

1.	Open module jpa-lab-01

2.	Open class edu.jpa.entity.Company

3.	Specify class-level annotation @Entity. This lets JPA runtime to know that this particular class should be treated as an entity.

4.	Specify class-level annotation @Table with the name of primary table “Country”.

5.	Specify class-level annotation @SecondaryTable with the name of secondary table “CompanyDetail”. The parameter pkJoinColumns of @SecondaryTable annotation specifies how to join primary and secondary table when building an entity: it should be @PrimaryKeyJoinColumn(name = "Company_id", referencedColumnName = "Company_id").

6.	Define Country entity fields: id (of the type Integer), name (of the type String) and address (of the type String).

7.	Specify field-level annotation @Column for each field with information which field is to be mapped on this particular field. Example: @Column(name="Company_id", table="Company")

8.	Specify field-level annotation @Id for the id field.

9.	Open and run the class edu.jpa.Launcher. There should be no errors if entity is defined correctly.

10.	Open database DB_LAB_01 using MySQL Workbench and look on the created database objects.

## Solution

In Workbench: right‑click db_lab_01 → Set as Default Schema (or run USE DB_LAB_01;).

Refresh schemas (right‑click Schemas → Refresh).

Run:

```
SHOW TABLES FROM DB_LAB_01;

DESCRIBE DB_LAB_01.Company;

DESCRIBE DB_LAB_01.CompanyDetail;

SELECT * FROM DB_LAB_01.Company;

SELECT * FROM DB_LAB_01.CompanyDetail;
```

Tip

Ensure Workbench is connected to the same server/port as the app (localhost:3306).

You can check with SELECT DATABASE(), @@port;.


<img width="1292" height="823" alt="image" src="https://github.com/user-attachments/assets/fe3d6745-6377-4a95-85f0-02af75ddab7b" />
