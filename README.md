# LESSON-5-LEARNING-MODULE
LESSON 5: LEARNING MODULE: INTRO TO PL/SQL AND SQL IN ORACLE

--Example 1
BEGIN DBMS_OUTPUT.PUT_LINE
    ('Lyca');
END;
--Ques: What do you think DBMS_OUTPUT.PUT_LINE does?
DBMS_OUTPUT.PUT_LINE is a PL/SQL procedure that prints messages to the console or output buffer

--Example 2
DECLARE
    my_name VARCHAR2(50) := 'Lyca';
    age NUMBER := 17;
BEGIN
    DBMS_OUTPUT.PUT_LINE
    ('My name is ' || my_name ||
    ' and I am ' || age || 
    ' years old.');
END;

--Ques: What happens if you change VARCHAR2 to NUMBER for my_name?
It will get an error because DBMS_OUTPUT.PUT_LINE expects a string

--Module 1 Activity:
DECLARE
    game_title VARCHAR2(50) := 
    'Blood Strike';
    developer VARCHAR2(50) := 
    'NetEase Games';
    year_release NUMBER := 2023;
BEGIN
    DBMS_OUTPUT.PUT_LINE
    ('Game title:' || game_title ||
    ', Developer: ' || developer ||
', Year Release: ' || year_release);
END;

--Challenge Questions:
How would you modify the code if you added another copy of the item?
1. Using UPDATE or INSERT to create a new row.


‌Could you add an extra detail, like genre or type?
2. Yes, using INSERT to add new records or rows of data into a table


--Module 2 Activity:
DECLARE
    daily_allowance NUMBER := 70;
    week NUMBER := 5;
    total_allowance NUMBER;
BEGIN
    total_allowance := 
    daily_allowance * week;
    DBMS_OUTPUT.PUT_LINE('After ' ||
    week || ' week, my total allowance is ' || 
    total_allowance || ' pesos.');
END;

--Challenge Questions:
‌How would you modify the code if your monthly savings amount changed?
1. I use UPDATE  to modify the existing data in a table


--Module 3 Activity:
DECLARE
   score NUMBER := 40;
BEGIN
   IF score <= 40 THEN
   DBMS_OUTPUT.PUT_LINE
   ('Congratulations, you passed!');
ELSE
   DBMS_OUTPUT.PUT_LINE('You did not
    pass. Keep trying!');

END IF;
END;

--Challenge Questions:
What happens if the condition changes (e.g., passing grade increases)?
1. It depends on the type of query and the context in which the condition is applied.


--Module 4 Activity:
CREATE TABLE FAV_ANIME (
  anime_id NUMBER,
  anime_title VARCHAR2(50),
  release_year NUMBER
);

INSERT INTO FAV_ANIME(anime_id, 
    anime_title, release_year)
VALUES (1, 'Haikyu', 2014);

INSERT INTO FAV_ANIME(anime_id, 
    anime_title, release_year)
VALUES (2, 'Hunter x Hunter', 2011);

INSERT INTO FAV_ANIME(anime_id, 
    anime_title, release_year)
VALUES (3, 'Jujutsu Kaisen', 2020);

--Challenge Questions:
1. Update an items details 
UPDATE employees
SET salary = 5000
WHERE employee_id = 101;

2.Delete an item from the table
DELETE FAV_ANIME
WHERE anime_id = 1;

--Module 5 Activity:
CREATE TABLE GADGETS (
    gadget_id NUMBER, 
    gadget_type VARCHAR2(50),
    gadget_price NUMBER
);

CREATE TABLE BRANDS ( 
    brand_id NUMBER, 
    brand_name VARCHAR2(50),
    gadget_id NUMBER
);

INSERT INTO GADGETS (gadget_id,
    gadget_type,gadget_price)
VALUES (1, 'cellphone', 8999);

INSERT INTO GADGETS (gadget_id,
    gadget_type,gadget_price)
VALUES (2, 'tablet', 15729);

INSERT INTO GADGETS (gadget_id,
    gadget_type,gadget_price)
VALUES (3, 'samrt watch', 54490);




INSERT INTO BRANDS (brand_id,
    brand_name, gadget_id)
VALUES (11, 'XIAOMI', 1);

INSERT INTO BRANDS (brand_id,
    brand_name, gadget_id)
VALUES (22, 'SAMSUNG', 2);

INSERT INTO BRANDS (brand_id,
    brand_name, gadget_id)
VALUES (33, 'APPLE', 3);

SELECT GADGETS.gadget_type
FROM GADGETS
JOIN BRANDS 
ON GADGETS.gadget_id = 
    BRANDS.gadget_id;
