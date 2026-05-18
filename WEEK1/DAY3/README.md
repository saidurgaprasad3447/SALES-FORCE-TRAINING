# 1. Difference Between App, Object, Record, and Field

| Term   | Meaning                                           | Example                    |
| ------ | ------------------------------------------------- | -------------------------- |
| App    | Collection of related features, tabs, and objects | College Admission App      |
| Object | Database table used to store data                 | Student Object             |
| Record | Single row/data entry inside an object            | One student’s details      |
| Field  | Individual data item in a record                  | Student Name, Phone Number |

### Simple Understanding

* App contains Objects
* Object contains Records
* Record contains Fields

---

# 2. Standard vs Custom Objects

| Standard Objects                        | Custom Objects                       |
| --------------------------------------- | ------------------------------------ |
| Already provided by Salesforce          | Created by users                     |
| Used for common business needs          | Used for specific requirements       |
| Examples: Account, Contact, Opportunity | Examples: Student, Course, Admission |
| Cannot be deleted easily                | Fully customizable                   |

Example:

* Account → Standard Object
* Student → Custom Object

---

# 3. Your College Data Model

## Objects

1. Student
2. Course
3. Faculty
4. Admission

---

## Relationships

* One Course can have many Students
* One Faculty can manage many Courses
* One Student can have one Admission record

---

# College Data Model Diagram

![Image](https://images.openai.com/static-rsc-4/UA_cQ9z90sajhmNi2MmjscJWxHG_qCVuK4cahcOoPFN-WPwERvqbT8PKq8R9mSB3BUVxIUsIqOPYRHX0CK2EG2acaawQ89Uhgp5X7hLa9DSxMGQLv4TFsE41OI6YyZnWkIAoeWTVndWB2PxcDzlVffN4M-GR93SmGUgLGnur5mdFu_LbRKUARMfqrlvtlfTJ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/meCT7a85w38zODZn6Qq02NGgme56aFclo0UdmBl9mscyHLprsAGB0R28wh3B9uEC-nN8umH5wJTP7uscppqj-g-D47hljVFYmp_4g9iq9DRpLwCTHYgnkKd2nOAWpbGIR_jLh5E_zxEmklxxlQaHT90WPp41ei2W3u0YChelkMWdaAA-34B0D8tqTUjIU0nd?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/SaQe4ToaB2ZruVixQBONP4GyNPbRCwCvS0-jGllV-BelFZJNUqrVc2CDUoFDMC_h8Vy68WbY7SDf6jpELzFTwBo8ClVO9Hq7mjxRJu1c8GDHb5h6rh9JQcj5Wmgnma4vMt_kKiMjkZglbXrYl46wPTSm5oFVDe847tmnd4bN3hv-z4DPQqO8JYvle9mljido?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/CyMsqW0Vp0Cce3JDbSha0uuppsZ-2kogKTbC3D7gysiDeiRCPZl_bHSMVxkVrCvVU8kbjYqM1-u-2pNMMJ0uAWVhltdM1ycI4e7LGwxWbOvtmb91opV9a565Tw7JIuCJLrAyjnaGs-5BszcI_pTthKWgpUGq0J_hTxyhQXk1r6F5NGjHao9elbpQwg7nX5cG?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/TcLOhA3CVX7JKGCgdgcTT4dwvvDhX3LKK0nxZF8jOwQm6tPCeohtVuixNbBfBoy5KWfa9HSWQ26XNAi2lvZEE8sap17rsMVjr0IqQZMCM0gfughTSPV4dBOwOv16fgPCuIAxqKwHFJRB1wRkH299kgRs3pc6us7MaMqhu724F0hw68-mZweVoaDQ25WfGnJ-?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/bfMkK_iVp0Py0kKFcKpq9IDJQsWMqE5MN4THVyEaWZwxw5JGjkbxN9hzNQ3pTBkXGJmZC18G1ZcW0gCCf6MDVBtt0br_HBR74d-BVJjQC5mO0OcyEDYbAI1s_nMnijfL4w_KFmK5cvmrxER56EO6xHmiZHefaK6CtX57EW0PpSMrrBSxNWwPFdzes4rDiCze?purpose=fullsize)

### Relationship Explanation

| Object              | Relationship                       |
| ------------------- | ---------------------------------- |
| Student → Course    | Many Students belong to one Course |
| Course → Faculty    | Many Courses handled by Faculty    |
| Student → Admission | Each student has admission details |

---

# 4. Formula Fields

A Formula Field automatically calculates values using formulas.

Purpose:

* Avoids manual calculations
* Updates automatically

## Examples

### Example 1: Student Full Name

Formula:

```text
First_Name + " " + Last_Name
```

Explanation:

* Combines first and last name automatically.

---

### Example 2: Total Fee Balance

Formula:

```text
Total_Fee - Paid_Fee
```

Explanation:

* Calculates remaining fee automatically.

---

### Example 3: Age Calculation

Formula:

```text
TODAY() - Date_of_Birth
```

Explanation:

* Calculates student age from date of birth.

[Salesforce Formula Fields Help](https://help.salesforce.com/s/articleView?id=platform.customize_formulafields.htm&type=5&utm_source=chatgpt.com)

---

# 5. Validation Rules

Validation Rules check whether entered data is correct before saving records.

Purpose:

* Prevent wrong or incomplete data
* Improve data quality

## Examples

### Example 1: Phone Number Validation

Rule:

* Phone number must contain 10 digits.

Explanation:

* Prevents invalid phone numbers.

---

### Example 2: Mandatory Email Validation

Rule:

* Email field cannot be empty.

Explanation:

* Ensures every student has email information.

---

### Example 3: Fee Validation

Rule:

```text
Paid_Fee > Total_Fee
```

Explanation:

* Prevents users from entering extra payment amount.

[Salesforce Validation Rules Guide](https://help.salesforce.com/s/articleView?id=sf.fields_about_field_validation.htm&type=5&utm_source=chatgpt.com)

---

# 6. Reflection: Why Structured Enterprise Data Matters

Structured enterprise data is important because it helps organizations manage information properly and efficiently.

Benefits:

* Easy data storage and retrieval
* Better decision making
* Reduces duplicate data
* Improves accuracy
* Supports automation
* Generates reports quickly
* Helps teams work together

Example in College System:

* Student details
* Course information
* Admission status
* Fee records

All data is connected and organized, making management easier and faster.
