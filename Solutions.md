

### Instructions
1. Create a table called Person that records a person's ID, Name, Age, Height ( in cm ), City, FavoriteColor. 
    * ID should be an auto-incrementing id/primary key - Use type: INTEGER PRIMARY KEY AUTOINCREMENT
   CREATE TABLE Persons (
    ID integer PRIMARY KEY AUTOINCREMENT,
    Name string varchar(50),
    Age int,
  	Height int,
  	City string,
  	FavoriteColor string varchar(50)
);
2. Add 5 different people into the Person database. 
    * Remember to not include the ID because it should auto-increment.
    solution:
    INSERT INTO Persons (Name, Age, Height, City, FavoriteColor)
    VALUES ('Christian', '46', '74', 'Boise', 'Blue');

3. List all the people in the Person table by Height from tallest to shortest.
    
    SELECT * FROM Person ORDER BY Height desc;

4. List all the people in the Person table by Height from shortest to tallest.

    SELECT * FROM Person ORDER BY Height;

5. List all the people in the Person table by Age from oldest to youngest.

    SELECT * FROM Person ORDER BY Age desc;

6. List all the people in the Person table older than age 20.

    SELECT * FROM Person WHERE Age > 20;

7. List all the people in the Person table that are exactly 18.

    SELECT * FROM Person WHERE Age = 18;

8. List all the people in the Person table that are less than 20 and older than 30.

    SELECT * FROM Person WHERE Age < 20 and Age > 30;

9. List all the people in the Person table that are not 27 (Use not equals).

    SELECT * FROM Person WHERE Age != 27;

10. List all the people in the Person table where their favorite color is not red.

    SELECT * FROM Person WHERE FavoriteColor != 'Red';

11. List all the people in the Person table where their favorite color is not red and is not blue.

      SELECT * FROM Person WHERE FavoriteColor != 'Red' AND FaovoriteColor != 'Blue';

12. List all the people in the Person table where their favorite color is orange or green.

    SELECT * FROM Person WHERE FavoriteColor = 'Orange' OR FavoriteColor = 'Green';

13. List all the people in the Person table where their favorite color is orange, green or blue (use IN).

    SELECT * FROM Person WHERE FavoriteColor IN ('Orange', 'Green', 'Blue');

14. List all the people in the Person table where their favorite color is yellow or purple (use IN).

    SELECT * FROM Person WHERE FavoriteColor IN ('Yellow', 'Purple');

    ## Table - Orders

### Instructions

1. Create a table called Orders that records: PersonID, ProductName, ProductPrice, Quantity.

    CREATE TABLE Orders (
    PersonID 		string,
    ProductName 	string,
    ProductPrice 	integer,
    Quantity 		integer
    );

2. Add 5 Orders to the Orders table.
    * Make orders for at least two different people.
    * PersonID should be different for different people.

        INSERT INTO Orders
        VALUES ('James', 'Pens', '5.00', '3');

3. Select all the records from the Orders table.

    SELECT * FROM Orders;

4. Calculate the total number of products ordered.

    SELECT SUM(Quantity) FROM Orders;

5. Calculate the total order price.

    SELECT SUM(ProductPrice * Quantity) FROM Orders;

6. Calculate the total order price by a single PersonID.

    SELECT SUM(ProductPrice * Quantity) FROM Orders WHERE PersonID ='Sally';

 ## Table - Artist

### Instructions

1. Add 3 new Artists to the Artist table. ( It's already created )
    INSERT INTO Artist (Name) VALUES('Susan');

2. Select 10 artists in reverse alphabetical order.

    SELECT * FROM Artist WHERE ArtistID > '10' AND ArtistID < '20' ORDER BY ArtistID desc;

3. Select 5 artists in alphabetical order.

    SELECT * FROM Artist WHERE ArtistID > '10' AND ArtistID < '15';

4. Select all artists that start with the word "Black".

    SELECT * FROM Artist WHERE Name LIKE "Black%";

5. Select all artists that contain the word "Black".

    SELECT * FROM Artist WHERE Name LIKE "%Black%";

## Table - Employee

### Instructions

1. List all Employee first and last names only that live in Calgary.

    SELECT LastName, FirstName FROM Employee WHERE City="Calgary";

2. Find the first and last name and birthdate for the youngest employee.

    SELECT FirstName, LastName, MAX(BirthDate) AS BirthDate FROM Employee;

3. Find the first and last name and birthdate for the oldest employee.

    SELECT FirstName, LastName, MIN(BirthDate) AS BirthDate FROM Employee;

4. Find everyone that reports to Nancy Edwards (Use the ReportsTo column).
   * You will need to query the employee table to find the Id for Nancy Edwards

    SELECT * FROM Employee WHERE ReportsTo = 2;

5. Count how many people live in Lethbridge.

    SELECT COUNT(*) AS People_In_Lethbridge FROM Employee WHERE City ="Lethbridge";


## Table - Invoice 

### Instructions

1. Count how many orders were made from the USA.

    SELECT COUNT(*) AS Total_USA_Orders FROM Invoice WHERE BillingCountry ="USA";

2. Find the largest order total amount.

    SELECT MAX(Total) AS Largest_Sale FROM Invoice;

3. Find the smallest order total amount.

    SELECT MIN(Total) AS Largest_Sale FROM Invoice;

4. Find all orders bigger than $5.

    SELECT * FROM Invoice WHERE Total > 5;

5. Count how many orders were smaller than $5.

    SELECT * FROM Invoice WHERE Total < 5;

6. Count how many orders were in CA, TX, or AZ (use IN).

    SELECT COUNT(BillingState) FROM Invoice WHERE BillingState IN ('CA', 'TX', 'AZ');

7. Get the average total of the orders.

    SELECT AVG(Total) AS AVG_Price FROM Invoice;

8. Get the total sum of the orders.

    SELECT SUM(Total) AS SUM_of_all_Orders FROM Invoice;