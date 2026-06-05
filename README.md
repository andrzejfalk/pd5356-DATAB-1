# pd5356-DATAB-1
**Schema (MySQL v5.7)**

    CREATE TABLE patients (
    
        id INT PRIMARY KEY,
        name VARCHAR(255) NOT NULL,
        date_of_birth DATE,
        email VARCHAR(255),
        phone_number VARCHAR(20),
        weight DECIMAL(5,2),
        height DECIMAL(5,2)
    );

---

**Query #1**

    INSERT INTO patients
    (id, name, date_of_birth, email, phone_number, weight, height)
    VALUES
    (1, 'John Doe', '1985-06-15', 'john.doe@gmail.com', '1234567890', 72.50, 180),
    (2, 'Jane Smith', '1990-03-20', 'jane.smith@gmail.com', '987654321', 60.00, 165),
    (3, 'Maria Garcia', '1978-12-05', NULL, '1122334455', 68.00, 170),
    (4, 'James Brown', '2000-07-15', 'james.brown@yahoo.com', '5566778899', 80.25, 175),
    (5, 'Emily Davis', '1995-02-10', 'emily.davis@outlook.com', '6677889900', 55.50, 160);

There are no results to be displayed.

---
**Query #2**

    SELECT * FROM patients;

| id  | name         | date_of_birth | email                   | phone_number | weight | height |
| --- | ------------ | ------------- | ----------------------- | ------------ | ------ | ------ |
| 1   | John Doe     | 1985-06-15    | john.doe@gmail.com      | 1234567890   | 72.5   | 180.0  |
| 2   | Jane Smith   | 1990-03-20    | jane.smith@gmail.com    | 987654321    | 60.0   | 165.0  |
| 3   | Maria Garcia | 1978-12-05    |                         | 1122334455   | 68.0   | 170.0  |
| 4   | James Brown  | 2000-07-15    | james.brown@yahoo.com   | 5566778899   | 80.25  | 175.0  |
| 5   | Emily Davis  | 1995-02-10    | emily.davis@outlook.com | 6677889900   | 55.5   | 160.0  |

---
**Query #3**

    SELECT *
    FROM patients
    WHERE weight > 65;

| id  | name         | date_of_birth | email                 | phone_number | weight | height |
| --- | ------------ | ------------- | --------------------- | ------------ | ------ | ------ |
| 1   | John Doe     | 1985-06-15    | john.doe@gmail.com    | 1234567890   | 72.5   | 180.0  |
| 3   | Maria Garcia | 1978-12-05    |                       | 1122334455   | 68.0   | 170.0  |
| 4   | James Brown  | 2000-07-15    | james.brown@yahoo.com | 5566778899   | 80.25  | 175.0  |

---
**Query #4**

    SELECT *
    FROM patients
    ORDER BY height DESC;

| id  | name         | date_of_birth | email                   | phone_number | weight | height |
| --- | ------------ | ------------- | ----------------------- | ------------ | ------ | ------ |
| 1   | John Doe     | 1985-06-15    | john.doe@gmail.com      | 1234567890   | 72.5   | 180.0  |
| 4   | James Brown  | 2000-07-15    | james.brown@yahoo.com   | 5566778899   | 80.25  | 175.0  |
| 3   | Maria Garcia | 1978-12-05    |                         | 1122334455   | 68.0   | 170.0  |
| 2   | Jane Smith   | 1990-03-20    | jane.smith@gmail.com    | 987654321    | 60.0   | 165.0  |
| 5   | Emily Davis  | 1995-02-10    | emily.davis@outlook.com | 6677889900   | 55.5   | 160.0  |


---
**Query #5**

    UPDATE patients
    SET email = 'john.updated@gmail.com'
    WHERE name = 'John Doe';

There are no results to be displayed.

---
**Query #6**

    DELETE FROM patients
    WHERE id = 3;

There are no results to be displayed.

---
**Query #7**

    ALTER TABLE patients
    ADD blood_type CHAR(3);

There are no results to be displayed.

---
**Query #8**

    UPDATE patients
    SET blood_type = '0+'
    WHERE name = 'John Doe';

There are no results to be displayed.

---
**Query #9**

    UPDATE patients
    SET blood_type = 'AB+'
    WHERE name = 'Jane Smith';

There are no results to be displayed.

---
**Query #10**

    UPDATE patients
    SET blood_type = 'A-'
    WHERE name = 'James Brown';

There are no results to be displayed.

---
**Query #11**

    UPDATE patients
    SET blood_type = 'B+'
    WHERE name = 'Emily Davis';

There are no results to be displayed.

---
**Query #12**

    SELECT *
    FROM patients;

| id  | name        | date_of_birth | email                   | phone_number | weight | height | blood_type |
| --- | ----------- | ------------- | ----------------------- | ------------ | ------ | ------ | ---------- |
| 1   | John Doe    | 1985-06-15    | john.updated@gmail.com  | 1234567890   | 72.5   | 180.0  | 0+         |
| 2   | Jane Smith  | 1990-03-20    | jane.smith@gmail.com    | 987654321    | 60.0   | 165.0  | AB+        |
| 4   | James Brown | 2000-07-15    | james.brown@yahoo.com   | 5566778899   | 80.25  | 175.0  | A-         |
| 5   | Emily Davis | 1995-02-10    | emily.davis@outlook.com | 6677889900   | 55.5   | 160.0  | B+         |

---
**Query #13**

    SELECT *
    FROM patients
    ORDER BY id
    LIMIT 2 OFFSET 2;

| id  | name        | date_of_birth | email                   | phone_number | weight | height | blood_type |
| --- | ----------- | ------------- | ----------------------- | ------------ | ------ | ------ | ---------- |
| 4   | James Brown | 2000-07-15    | james.brown@yahoo.com   | 5566778899   | 80.25  | 175.0  | A-         |
| 5   | Emily Davis | 1995-02-10    | emily.davis@outlook.com | 6677889900   | 55.5   | 160.0  | B+         |

---

[View on DB Fiddle](https://www.db-fiddle.com/f/xfBiuLGeQRZ3fUPJbd7mAg/0)



[View on DB Fiddle](https://www.db-fiddle.com/)
