# 1. What is SOQL?

SOQL stands for **Salesforce Object Query Language**.

It is used in Salesforce to retrieve data from objects, similar to SQL in databases.

SOQL helps us:

* Read records
* Filter data
* Search information
* Generate reports
* Access related object data

Example:
Get all students from the Computer Science department.

---

# 2. What is an Apex Trigger?

An Apex Trigger is a special Apex code that automatically runs when data changes occur in Salesforce.

Triggers execute when:

* A record is created
* Updated
* Deleted
* Restored

Triggers help automate business logic based on data changes.

Example:
When a student registers for a course:

* Trigger checks seat availability
* Updates remaining seats automatically
* Sends notification if course becomes full

---

# 3. Difference Between Concepts

## Flow vs Trigger

| Feature       | Flow                  | Apex Trigger              |
| ------------- | --------------------- | ------------------------- |
| Type          | No-code automation    | Code-based automation     |
| Used By       | Admins                | Developers                |
| Complexity    | Simple to medium      | Medium to advanced        |
| Customization | Limited               | Highly flexible           |
| Performance   | Good for simple tasks | Better for complex logic  |
| Example       | Send reminder email   | Advanced validation logic |

---

## Before Trigger vs After Trigger

| Feature                 | Before Trigger          | After Trigger              |
| ----------------------- | ----------------------- | -------------------------- |
| Runs                    | Before record is saved  | After record is saved      |
| Purpose                 | Validate or modify data | Perform actions after save |
| Can Update Same Record? | Yes                     | Usually No                 |
| Database ID Available?  | No                      | Yes                        |
| Example                 | Validate fee amount     | Send confirmation email    |

---

# 4. Trigger Use Cases in College Management System

## 1. Auto Generate Student ID

When a new student record is inserted:

* Trigger creates unique student ID automatically.

Example:
`CSE-2026-001`

---

## 2. Update Remaining Course Seats

When a student enrolls in a course:

* Trigger decreases available seats count.

---

## 3. Block Registration if Course is Full

Before course enrollment:

* Trigger checks seat availability.
* Stops enrollment if seats are full.

---

## 4. Notify Student for Low Attendance

When attendance record is updated:

* Trigger sends warning notification if attendance < 75%.

---

## 5. Prevent Exam Registration for Pending Fees

Before exam registration:

* Trigger checks fee payment status.
* Blocks registration if dues are pending.

---

# 5. Query Examples (English Query Ideas)

## Example 1

Get all students from the CSE department.

---

## Example 2

Find students whose attendance is below 75%.

---

## Example 3

Show all courses with available seats greater than 10.

---

## Example 4

Get students who have not paid fees.

---

## Example 5

Find faculty members teaching more than 3 courses.

---

## Example 6

Display all students enrolled in the Artificial Intelligence course.

---

## Example 7

Get courses that are already full.

---

# 6. Reflection

## Why enterprise systems react automatically to data changes

Enterprise systems handle thousands or millions of records daily. Manual monitoring of every data change is impossible.

Automatic reactions are important because they:

* Improve speed
* Reduce human effort
* Maintain data accuracy
* Prevent business rule violations
* Provide instant notifications
* Improve customer and user experience

For example:

* When fees are unpaid → automatic reminder sent
* When seats are full → registration blocked
* When attendance is low → warning generated

Triggers and automation help enterprise systems respond immediately whenever data changes occur. This creates efficient, intelligent, and scalable business operations.
