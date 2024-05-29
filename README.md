# Database Project

``` 
 Project Name: Online Hotel Booking
 Performed By: Sayma Mushsharat(2007036)
```
<hr>

## Project Description:
This project is about online hotel booking database. In this database, we have 6 tables. These are:
1. Users : This table contains the information about the users. The attributes of this table are:
```
UserID : Primary Key
Username
Email
Password
DateOfBirth
```
2. Hotels : This table contains the information about the hotels. The attributes of this table are:
```
HotelID : Primary Key
HotelName
Location
Discription
Rating
ContactInfo
```
3. Rooms : This table contains the information about the rooms of the hotels. The attributes of this table are:
```
RoomID : Primary Key
HotelID : Foreign Key
RoomType
Price
NumberOfBeds
Availability
MaxOccupancy
```
4. Bookings : This table contains the information about the bookings of the users. The attributes of this table are:
```
BookingID : Primary Key
UserID : Foreign Key
RoomID : Foreign Key
CheckInDate
CheckOutDate
NumberOfGuest
BookingDate
BookingStatus
```
5. Payments : This table contains the information about the payments given by the users. The attributes of this table are:
```
PaymentID : Primary Key
BookingID : Foreign Key
Amount 
PaymentDate
PaymentMethod
PaymentStatus
```
4. Reviews : This table contains the information about the reviews given by the users. The attributes of this table are:
```
ReviewID : Primary Key
HotelID : Foreign Key
UserID : Foreign Key
Rating
Feedback
```



<hr>

## Table Creation
``` 

CREATE TABLE Users (
    UserID number(6) PRIMARY KEY,
    UserName VARCHAR(50),
    Pass VARCHAR(50) ,
    Email VARCHAR(100) ,
    DateOfBirth varchar(30)
);

CREATE TABLE Hotels (
    HotelID number(6) PRIMARY KEY,
    HotelName VARCHAR(50),
    Location VARCHAR(50) ,
    Discription VARCHAR(100) ,
    Rating number(2,1),
    ContactInfo varchar(30)
);


CREATE TABLE Rooms (
    RoomID number(6) PRIMARY KEY,
    HotelID number(6),
    RoomType VARCHAR(50) ,
    Price number(10,2),
    NumberOfBeds number(6),
    Availability VARCHAR(10) ,
    MaxOccupancy number(6),
    FOREIGN KEY (HotelID) REFERENCES Hotels(HotelID)
    
);

CREATE TABLE Bookings (
    BookingID number(6) PRIMARY KEY,
    UserID number(6) ,
    RoomID number(6),
    CheckInDate VARCHAR(50),
    CheckOutDate VARCHAR(50) ,
    NumberOfGuest number(6),
    BookingDate VARCHAR(10) ,
    BookingStatus VARCHAR(10) ,
    FOREIGN KEY (UserID) REFERENCES Users(UserID),
    FOREIGN KEY (RoomID) REFERENCES Rooms(RoomID)
    
);

CREATE TABLE Payments (
    PaymentID number(6) PRIMARY KEY,
    BookingID number(6),
    Amount number(10,2),
    PaymentDate VARCHAR(50) ,
    PaymentMethod VARCHAR(50) ,
    PaymentStatus VARCHAR(50) ,
    FOREIGN KEY (BookingID) REFERENCES Bookings(BookingID)
    
);

CREATE TABLE Reviews (
    ReviewID number(6) PRIMARY KEY,
    HotelID number(6),
    UserID number(6),
    Rating number(6) ,
    Feedback VARCHAR(50) ,
    FOREIGN KEY (HotelID) REFERENCES Hotels(HotelID),
    FOREIGN KEY (UserID) REFERENCES Users(UserID)
    
);

```
<hr>

# DML
- ## Insert
    - ### Inserting into Users Table
    ```
         -- Insert 10 user records into the Users table
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100001, 'JohnDoe', 'pass123', 'john.doe@example.com', '1990-01-15');
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100002, 'JaneDoe', 'pass124', 'jane.doe@example.com', '1992-05-22');
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100003, 'BobSmith', 'pass125', 'bob.smith@example.com', '1988-03-30');
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100004, 'AliceJones', 'pass126', 'alice.jones@example.com', '1991-07-19');
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100005, 'ChrisLee', 'pass127', 'chris.lee@example.com', '1989-11-25');
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100006, 'DianaRay', 'pass128', 'diana.ray@example.com', '1990-02-12');
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100007, 'EvanTodd', 'pass129', 'evan.todd@example.com', '1992-08-05');
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100008, 'GraceKim', 'pass130', 'grace.kim@example.com', '1987-04-26');
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100009, 'HenryFinn', 'pass131', 'henry.finn@example.com', '1993-09-17');
            INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100010, 'IvyHolt', 'pass132', 'ivy.holt@example.com', '1994-12-24');

    ```
    - ### Inserting into Hotels
    ```
     -- Insert 10 user records into the Users table
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100001, 'JohnDoe', 'pass123', 'john.doe@example.com', '1990-01-15');
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100002, 'JaneDoe', 'pass124', 'jane.doe@example.com', '1992-05-22');
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100003, 'BobSmith', 'pass125', 'bob.smith@example.com', '1988-03-30');
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100004, 'AliceJones', 'pass126', 'alice.jones@example.com', '1991-07-19');
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100005, 'ChrisLee', 'pass127', 'chris.lee@example.com', '1989-11-25');
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100006, 'DianaRay', 'pass128', 'diana.ray@example.com', '1990-02-12');
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100007, 'EvanTodd', 'pass129', 'evan.todd@example.com', '1992-08-05');
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100008, 'GraceKim', 'pass130', 'grace.kim@example.com', '1987-04-26');
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100009, 'HenryFinn', 'pass131', 'henry.finn@example.com', '1993-09-17');
        INSERT INTO Users(UserID, UserName, Pass, Email, DateOfBirth) VALUES (100010, 'IvyHolt', 'pass132', 'ivy.holt@example.com', '1994-12-24');



    ```
    - ### Inserting into Rooms
    ```
    -- Insert 10 room records into the Rooms table
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300001, 200001, 'Standard', 150.00, 2, 'Yes', 2);
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300002, 200001, 'Deluxe', 200.00, 2, 'No', 3);
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300003, 200002, 'Suite', 300.00, 1, 'Yes', 2);
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300004, 200002, 'Standard', 180.00, 2, 'Yes', 4);
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300005, 200003, 'Suite', 350.00, 1, 'No', 2);
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300006, 200003, 'Standard', 150.00, 2, 'Yes', 2);
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300007, 200004, 'Deluxe', 220.00, 2, 'No', 3);
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300008, 200004, 'Standard', 160.00, 2, 'Yes', 4);
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300009, 200005, 'Suite', 320.00, 1, 'No', 2);
        INSERT INTO Rooms(RoomID, HotelID, RoomType, Price, NumberOfBeds, Availability, MaxOccupancy) VALUES (300010, 200005, 'Standard', 140.00, 2, 'Yes', 2);
    ```    
    - ### Inserting into Bookings
    ```
    -- Insert 10 booking records into the Bookings table
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400001, 100001, 300001, '2023-06-15', '2023-06-20', 2, '2023-05-10', 'Confirmed');
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400002, 100002, 300003, '2023-07-01', '2023-07-05', 2, '2023-06-01', 'Confirmed');
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400003, 100003, 300005, '2023-08-10', '2023-08-15', 1, '2023-07-15', 'Pending');
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400004, 100004, 300002, '2023-09-05', '2023-09-10', 3, '2023-08-20', 'Cancelled');
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400005, 100005, 300004, '2023-10-15', '2023-10-20', 4, '2023-09-10', 'Confirmed');
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400006, 100006, 300006, '2023-11-01', '2023-11-05', 2, '2023-10-01', 'Confirmed');
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400007, 100007, 300008, '2023-12-10', '2023-12-15', 4, '2023-11-10', 'Pending');
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400008, 100008, 300010, '2024-01-05', '2024-01-10', 2, '2023-12-20', 'Cancelled');
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400009, 100009, 300007, '2024-02-15', '2024-02-20', 3, '2024-01-15', 'Confirmed');
        INSERT INTO Bookings(BookingID, UserID, RoomID, CheckInDate, CheckOutDate, NumberOfGuest, BookingDate, BookingStatus) VALUES (400010, 100010, 300009, '2024-03-01', '2024-03-05', 1, '2024-02-01', 'Pending');
    ```
    - ### Inserting into Payments
    ```
          -- Insert 10 payment records into the Payments table
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500001, 400001, 750.00, '2023-05-10', 'Credit Card', 'Completed');
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500002, 400002, 1200.00, '2023-06-01', 'Debit Card', 'Completed');
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500003, 400003, 1750.00, '2023-07-15', 'PayPal', 'Pending');
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500004, 400004, 1000.00, '2023-08-20', 'Credit Card', 'Refunded');
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500005, 400005, 720.00, '2023-09-10', 'Credit Card', 'Completed');
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500006, 400006, 300.00, '2023-10-01', 'Debit Card', 'Completed');
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500007, 400007, 640.00, '2023-11-10', 'PayPal', 'Pending');
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500008, 400008, 280.00, '2023-12-20', 'Credit Card', 'Refunded');
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500009, 400009, 660.00, '2024-01-15', 'Debit Card', 'Completed');
                INSERT INTO Payments(PaymentID, BookingID, Amount, PaymentDate, PaymentMethod, PaymentStatus) VALUES (500010, 400010, 1600.00, '2024-02-01', 'Credit Card', 'Pending');
    ```
    - ### Inserting into Reviews
    ```
         -- Insert 10 review records into the Reviews table
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600001, 200001, 100001, 5, 'Outstanding service and location!');
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600002, 200002, 100002, 4, 'Great views but room could be cleaner.');
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600003, 200003, 100003, 5, 'Perfect for a mountain getaway!');
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600004, 200004, 100004, 3, 'Decent place but noisy at night.');
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600005, 200005, 100005, 4, 'Loved the sunsets, will come back!');
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600006, 200006, 100006, 5, 'Truly a royal experience!');
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600007, 200007, 100007, 4, 'Good service but expensive.');
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600008, 200008, 100008, 3, 'Unique but too remote.');
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600009, 200009, 100009, 5, 'Quiet and peaceful, just what I needed.');
            INSERT INTO Reviews(ReviewID, HotelID, UserID, Rating, Feedback) VALUES (600010, 200010, 100010, 4, 'Great location but average food.');

    ```
    - ### All types of query that we performed during lab sessions
    ```
    -- Querying the database

        -- Query 1: Get all users
        SELECT * FROM Users;



        -- Query 2: Get all hotels
        SELECT * FROM Hotels;



        -- Query 3: Get all rooms
        SELECT * FROM Rooms;



        -- Query 4: Get all bookings
        SELECT * FROM Bookings;



        -- Query 5: Get all payments
        SELECT * FROM Payments;



        -- Query 6: Get all reviews
        SELECT * FROM Reviews;



        -- Query 7:Find users with a specific name (e.g. containing 'Smith')
        SELECT * FROM Users WHERE UserName LIKE '%Smith%';



        -- Query 8: Get all bookings that are unpaid
        SELECT * FROM Bookings WHERE BookingStatus = 'Unpaid';



        -- Query 9: Update hotel name based on HotelID 
        UPDATE Hotels 
        SET HotelName = 'Rana Plaza' 
        WHERE HotelID = 200001;



        -- Query 10: Delete a record from the Hotels table based on HotelID
        DELETE FROM Hotels WHERE HotelID = 200011;



        -- Query 11: Use of union, intersect, and except

        -Retrieve hotel names starting with 'E' or containing 'M'
        SELECT HotelName FROM Hotels WHERE HotelName LIKE 'E%' UNION SELECT HotelName FROM Hotels WHERE HotelName LIKE '%M%';

        -Retrieve hotel names starting with 'E' and containing 'M'
        SELECT HotelName FROM Hotels WHERE HotelName LIKE 'E%' INTERSECT SELECT HotelName FROM Hotels WHERE HotelName LIKE '%M%';

        -Retrieve hotel names starting with 'E' but not containing 'M'
        SELECT HotelName FROM Hotels WHERE HotelName LIKE 'E%' EXCEPT SELECT HotelName FROM Hotels WHERE HotelName LIKE '%M%';


        -- Query 12: Find rooms with the maximum number of beds 
        WITH MaxBeds AS (SELECT MAX(NumberOfBeds) AS MaxNumberOfBeds FROM Rooms)
        SELECT * FROM Rooms WHERE NumberOfBeds = (SELECT MaxNumberOfBeds FROM MaxBeds);




        -- Query 13: Find Average, Minimum, and Maximum Ratings from Reviews (using Aggregate function)
        SELECT AVG(Rating) AS AverageRating, MIN(Rating) AS MinRating, MAX(Rating) AS MaxRating
        FROM Reviews;



        -- Query 14: Find Room Types with Average Number of Beds Greater Than a Certain Number in a Specific Hotel
        SELECT RoomType, AVG(NumberOfBeds) AS AverageBeds FROM Rooms WHERE HotelID = 200001 GROUP BY RoomType HAVING AVG(NumberOfBeds) > 2;



        -- Query 15: use of Set Membership(AND, OR,NOT)
        
        -Retrieve all details about hotels located in "New York" that have "Deluxe" rooms available
        SELECT * FROM Hotels WHERE Location = 'New York' AND HotelID IN (SELECT HotelID FROM Rooms WHERE RoomType = 'Deluxe' AND Availability = 'Yes');

        -Retrieve all rooms that are priced above $300 or can accommodate more than 3 people
        SELECT * FROM Rooms WHERE Price > 300 OR MaxOccupancy > 3;

        -Find Bookings Made by Users Not From 'alice.jones@example.com' Domain
        SELECT * FROM Bookings WHERE UserID NOT IN (SELECT UserID FROM Users WHERE Email LIKE '%alice.jones@example.com');


        -- Query 16: Find List of Users Who Booked Suites in Highly Rated Hotels
        SELECT UserName FROM Users WHERE UserID IN (SELECT UserID FROM Bookings WHERE RoomID IN (SELECT RoomID FROM Rooms WHERE HotelID IN (SELECT HotelID FROM Hotels WHERE Rating > 4.5) AND RoomType = 'Suite'));



        -- Query 17: Use of some,all,exists and not exists

        -Retrieve bookings with a number of guests greater than some bookings
        SELECT * FROM Bookings WHERE NumberOfGuest > SOME (SELECT NumberOfGuest FROM Bookings);

        -Retrieve bookings with a number of guests greater than all bookings
        SELECT * FROM Bookings WHERE NumberOfGuest > ALL (SELECT NumberOfGuest FROM Bookings);

        -Retrieve bookings with a specific RoomID that exists in the Rooms table
        SELECT * FROM Bookings b WHERE EXISTS (SELECT 1 FROM Rooms r WHERE r.RoomID = b.RoomID);

        -Retrieve Users with no confirmed bookings
        SELECT UserID, UserName, Email FROM Users WHERE NOT EXISTS (SELECT 1 FROM Bookings WHERE Users.UserID = Bookings.UserID AND Bookings.BookingStatus = 'Confirmed');




        -- Query 18: Retrieve bookings for a specific year
        SELECT * FROM Bookings WHERE CheckInDate LIKE '%2024% ;



        -- Query 19: Retrieve bookings along with corresponding user information
        SELECT B.*, U.UserName, U.Email FROM Bookings B JOIN Users U ON B.UserID = U.UserID;



        -- Query 20: Using VIEW for Unpaid Bookings
        DROP VIEW IF EXISTS UnpaidBookingsView;
        CREATE VIEW UnpaidBookingsView AS 
        SELECT * FROM Bookings WHERE BookingStatus = 'Unpaid';

        SELECT * FROM UnpaidBookingsView;




    ```
 - ### PL/SQL
 ```
 
        -- Query 1: Display details of a specific hotel from the Hotels table
        SET SERVEROUTPUT ON;
        DECLARE 
            hotel_id Hotels.HotelID%TYPE;
            hotel_name Hotels.HotelName%TYPE;
            location Hotels.Location%TYPE;
            description Hotels.Discription%TYPE;
            rating Hotels.Rating%TYPE;
            contact_info Hotels.ContactInfo%TYPE;
        BEGIN
            SELECT HotelID, HotelName, Location, Discription, Rating, ContactInfo INTO hotel_id, hotel_name, location, description, rating, contact_info FROM Hotels WHERE HotelID = 200001; 

            DBMS_OUTPUT.PUT_LINE('HotelID: ' || hotel_id || ' HotelName: ' || hotel_name || ' Location: ' || location || ' Description: ' || description || ' Rating: ' || rating || ' ContactInfo: ' || contact_info);
        END;
        /


        -- Query 2: Insert a new record into the Hotels table
        SET SERVEROUTPUT ON;
        DECLARE 
            hotel_id Hotels.HotelID%TYPE := 200012; 
            hotel_name Hotels.HotelName%TYPE := 'Adventure Inn';
            location Hotels.Location%TYPE := 'Alaska';
            description Hotels.Discription%TYPE := 'Cozy lodge with beautiful mountain views';
            rating Hotels.Rating%TYPE := 4.7;
            contact_info Hotels.ContactInfo%TYPE := '987-654-3210';
        BEGIN
            INSERT INTO Hotels VALUES(hotel_id, hotel_name, location, description, rating, contact_info);
            COMMIT;
            DBMS_OUTPUT.PUT_LINE('Record inserted successfully: HotelID: ' || hotel_id);
        END;
        /


        -- Query 3: Fetch details of a specific hotel from the Hotels table into a rowtype variable
        SET SERVEROUTPUT ON;
        DECLARE 
            hotel_row Hotels%ROWTYPE;
        BEGIN
            SELECT * INTO hotel_row FROM Hotels WHERE HotelID = 200001;  

            DBMS_OUTPUT.PUT_LINE('HotelID: ' || hotel_row.HotelID || ', HotelName: ' || hotel_row.HotelName || ', Location: ' || hotel_row.Location || ', Description: ' || hotel_row.Discription || ', Rating: ' || hotel_row.Rating || ', ContactInfo: ' || hotel_row.ContactInfo);
        END;
        /


        -- Query 4: Fetch and display all records from the Hotels table using a cursor
        SET SERVEROUTPUT ON;
        DECLARE 
            cursor hotel_cursor IS SELECT * FROM Hotels;
            hotel_row Hotels%ROWTYPE;
        BEGIN
            OPEN hotel_cursor;
            FETCH hotel_cursor INTO hotel_row;
            WHILE hotel_cursor%FOUND LOOP
                DBMS_OUTPUT.PUT_LINE('HotelID: ' || hotel_row.HotelID || ', HotelName: ' || hotel_row.HotelName || ', Location: ' || hotel_row.Location || ', Description: ' || hotel_row.Discription || ', Rating: ' || hotel_row.Rating || ', ContactInfo: ' || hotel_row.ContactInfo);
                DBMS_OUTPUT.PUT_LINE('Row count: ' || hotel_cursor%ROWCOUNT);
                FETCH hotel_cursor INTO hotel_row;
            END LOOP;
            CLOSE hotel_cursor;
        END;
        /


        -- Query 5: Fetch hotel names into an array and display them using PL/SQL
        SET SERVEROUTPUT ON;
        DECLARE 
        counter NUMBER;
        hotel_name Hotels.HotelName%TYPE;
        TYPE HOTELNAMEARRAY IS VARRAY(5) OF Hotels.HotelName%TYPE; 
        A_HOTELNAME HOTELNAMEARRAY := HOTELNAMEARRAY();
        BEGIN
        counter := 1;
        -- Assuming HotelID range from some specific IDs
        FOR x IN 200001..200005 LOOP
            SELECT HotelName INTO hotel_name FROM Hotels WHERE HotelID = x;
            A_HOTELNAME.EXTEND();
            A_HOTELNAME(counter) := hotel_name;
            counter := counter + 1;
        END LOOP;
        
        counter := 1;
        WHILE counter <= A_HOTELNAME.COUNT LOOP
            DBMS_OUTPUT.PUT_LINE(A_HOTELNAME(counter)); 
            counter := counter + 1;
        END LOOP;
        END;
        /


        -- Query 5: Update and Display Hotel Names from Hotels Table Using a VARRAY
        DECLARE 
        counter NUMBER := 1;
        hotel_name2 Hotels.HotelName%TYPE;
        TYPE HOTELNAMEARRAY IS VARRAY(5) OF Hotels.HotelName%TYPE;
        A_HOTELNAME HOTELNAMEARRAY := HOTELNAMEARRAY('Grand Plaza', 'Sea Breeze Resort', 'Mountain Retreat', 'Urban Hotel', 'Sunset Villas'); 
        -- VARRAY with a fixed size of 5 elements and initialized with preliminary hotel names
        BEGIN
        counter := 1;
        FOR x IN 200001..200005  
        LOOP
            SELECT HotelName INTO hotel_name2 FROM Hotels WHERE HotelID = x;
            A_HOTELNAME(counter) := hotel_name2;
            counter := counter + 1;
        END LOOP;
        counter := 1;
        WHILE counter <= A_HOTELNAME.COUNT 
        LOOP 
            DBMS_OUTPUT.PUT_LINE(A_HOTELNAME(counter)); 
            counter := counter + 1;
        END LOOP;
        END;



        -- Query 6: Categorize hotels based on their rating and display category messages
        DECLARE 
        counter NUMBER := 1;
        hotel_name Hotels.HotelName%TYPE;
        hotel_rating Hotels.Rating%TYPE;
        TYPE HOTELNAMEARRAY IS VARRAY(5) OF Hotels.HotelName%TYPE;
        A_HOTELNAME HOTELNAMEARRAY := HOTELNAMEARRAY('Grand Plaza', 'Sea Breeze Resort', 'Mountain Retreat', 'Urban Hotel', 'Sunset Villas'); 
        -- VARRAY with a fixed size of 5 elements and initialized with preliminary hotel names
        BEGIN
        counter := 1;
        FOR x IN 200001..200005  
        LOOP
            SELECT HotelName, Rating INTO hotel_name, hotel_rating FROM Hotels WHERE HotelID = x;
            IF hotel_rating >= 4.5 THEN
                DBMS_OUTPUT.PUT_LINE(hotel_name || ' is a ' || 'premium quality hotel');
            ELSIF hotel_rating >= 4.0 THEN
                DBMS_OUTPUT.PUT_LINE(hotel_name || ' is a ' || 'high quality hotel');
            ELSE
                DBMS_OUTPUT.PUT_LINE(hotel_name || ' is a ' || 'standard quality hotel');
            END IF;
        END LOOP;
        END;



        -- Query 7: -- Create or Replace Procedure to Fetch Hotel Name based on HotelID and Modify a Numeric Value
        CREATE OR REPLACE PROCEDURE GetHotelDetails(
        hotel_id IN NUMBER,
        hotel_name OUT VARCHAR2,
        next_id IN OUT NUMBER
        )
        AS
        t_show CHAR(30);
        BEGIN
        t_show := 'From procedure: ';
        SELECT HotelName INTO hotel_name FROM Hotels WHERE HotelID = hotel_id;
        next_id := hotel_id + 1;
        DBMS_OUTPUT.PUT_LINE(t_show || hotel_name || ' ID is ' || hotel_id || ' Next ID: ' || next_id);
        END;
        /


        SET SERVEROUTPUT ON;
        DECLARE 
        hotel_id Hotels.HotelID%TYPE := 200001; 
        hotel_name Hotels.HotelName%TYPE;
        next_id NUMBER;
        BEGIN
        GetHotelDetails(hotel_id, hotel_name, next_id);
        END;
        /



        -- Query 8: Create or Replace Function to Fetch Hotel Name by HotelID
        SET SERVEROUTPUT ON;
        CREATE OR REPLACE FUNCTION GetHotelName(var1 IN NUMBER) RETURN VARCHAR2 AS
        hotel_name Hotels.HotelName%TYPE;
        BEGIN
        SELECT HotelName INTO hotel_name FROM Hotels WHERE HotelID = var1;
        RETURN hotel_name;
        END;
        /

        SET SERVEROUTPUT ON;
        DECLARE 
        hotel_name_value VARCHAR2(50);
        BEGIN
        hotel_name_value := GetHotelName(200001); 
        DBMS_OUTPUT.PUT_LINE('Hotel Name: ' || hotel_name_value);
        END;
        /



        -- Query 9: Create or Replace Trigger to Handle Cascade Deletions with Bookings
        SET SERVEROUTPUT ON;
        CREATE OR REPLACE TRIGGER BookingCascadeDelete
        BEFORE DELETE ON Bookings
        REFERENCING OLD AS o NEW AS n
        FOR EACH ROW
        BEGIN
        DELETE FROM Payments WHERE BookingID = :o.BookingID;
        DELETE FROM Reviews WHERE BookingID = :o.BookingID;
        END;
        /


        -- Query 10: Create or Replace Trigger to Update Booking Details After Room Update
        SET SERVEROUTPUT ON;
        CREATE OR REPLACE TRIGGER UpdateBookingDetails
        AFTER UPDATE ON Rooms
        REFERENCING OLD AS o NEW AS n
        FOR EACH ROW
        ENABLE
        BEGIN
        UPDATE Bookings
        SET CheckInDate = (CASE WHEN :n.Price != :o.Price THEN 'Check new prices' ELSE CheckInDate END)
        WHERE RoomID = :o.RoomID;
        END;
        /
        
 ```

