
# Project Title

MIST 4610 Group Project 1

## Team Name

39217 Group 7

## Team Members

Miral Lakhani 
Dylan McMorrow 
Aafreen Anjum 
Jack Drummond 
Ishi Gupta 

## Problem Description

Our primary goal is to create a relational database that significantly improves the efficiency and quality of a medical center's operations. The central entity in our database model is the "Visit Entity," representing each medical patient's visit. This "Visit Entity" is intricately linked with other key components, including the "Patient," "Visit Record," "Physician," "Room," and "Billing" entities. Our focus is on accurately modeling these relationships, generating realistic sample data, and populating these entities with relevant attributes.

Moreover, we aim to implement fully functional query capabilities on this data. These queries will not only facilitate day-to-day operations but also yield valuable business insights into the medical center's functioning. This enhanced database will provide us with a comprehensive and detailed view of patient visits, medical records, physician-patient interactions, room allocation, and billing processes. By effectively leveraging this database, we can drive informed decision-making, streamline operations, and ultimately enhance the overall performance and quality of care within the medical center.

We have attached screenshots from the initial conversation with our client. As evident in our data model below, we adjusted some of the entities originally proposed by our client to better suit their needs and boost efficiency.

<img width="682" alt="Screenshot 2023-11-03 at 6 11 37 PM" src="https://github.com/mirLakhani/healthcare1/assets/148798235/2474a82f-0ae2-41c6-9a28-68fe3f909649">
<img width="678" alt="Screenshot 2023-11-03 at 6 11 47 PM" src="https://github.com/mirLakhani/healthcare1/assets/148798235/979a9908-bffd-49e9-95cb-cd80e62e840a">
<img width="609" alt="Screenshot 2023-11-03 at 6 12 26 PM" src="https://github.com/mirLakhani/healthcare1/assets/148798235/3b3ef953-2ff6-4f7f-b1a8-3310634d85df">

## Data Model Explanation

Our model is designed to represent the structure of a small to medium sized emergency healthcare clinic. The Patient entity stores information about all patients who come to the clinic to seek medical care, such as their name, contact information, and any relevant allergies to medications. Each patient will have one or more emergency contacts listed, which is represented by the 1 to many relationship between the Patient and Contact entities. The Contact table stores information about each emergency contact such as their name, address, phone number, email, and the relationship to the patient (e.g. mother, aunt, etc.).

We then have the Visit entity, which is central to the entire model. The Visit table is updated each time a patient comes to the front desk and fills out paperwork, regardless if any tests were performed. Each patient can have as many visits as needed, which is represented by the 1 to many relationship between the Patient and Visit entities. A visit is also associated with a particular physician, whose information is stored in the Physician table. Every visit is associated with one patient and one primary physician. A physician will have many visits over the course of their career, but each visit only has one physician, which can be seen by the one to many relationship between Physician and Visit.

Each visit also takes place in a particular room. Information about each room such as its number, name, and the wing it is located in (North, South, East, or West) is stored in the Room entity. Each visit is associated with one room, but a particular room will be associated with many visits, which can be seen in the one to many relationship between Room and Visit. It is important to note that while a patient may have tests done in multiple rooms on the same visit (X-ray in one room, MRI in another), each visit is assigned a primary room number where the Physician meets with them privately. 

The clinic also owns a lot of different pieces of medical equipment. Information about this equipment is stored in the Equipment table. The table stores the name of the equipment (e.g. an X-Ray machine), the date the equipment was purchased, and also the price. Additionally every piece of equipment is associated with a particular room. One room can have multiple pieces of equipment, but a particular piece of equipment can only belong to one room. This is shown by the one to many relationship between Room and Equipment. 

Additionally, the clinic can perform many different tests. The Test entity stores information about the different types of medical tests done on a patient. Examples include blood tests, MRIs, etc., and the visitRecord entity stores information about each visit and any potential tests performed. There is a one to many relationship between visitRecord and Test because a particular test can be done multiple times on the same patient, and therefore be found in multiple different visit records. There is also a one to many relationship between Visit and visitRecord because during each visit a patient can have multiple tests performed on them, which will each go into a separate visit record.

Each Visit is associated with one bill (also known as an invoice). This is represented by the one to one relationship between the Visit and Billing tables. While each visit can be associated with multiple visit records, it is important to note that a visit can only have one bill in total, regardless of the number of visit records associated with one visit. 

Each visitRecord then has the potential to generate a Prescription for the patient. One visitRecord can generate multiple prescriptions (E.g. a test revealing a broken bone may lead to multiple pain relief medications prescribed), and each prescription is only tied to one visitRecord. This is evident by the one to many relationship between visitRecord and Prescription. 

This clinic also stores many different medications, which we have organized in the Medications table. The clinic also maintains a list of approved suppliers for which they get their medications from. At this particular clinic, each medication is provided by only one supplier. This is represented by the one to many relationship between the Supplier and Medication tables, as one supplier can provide different medications, but each medication is tied to a particular supplier. Each prescription can only have one medication listed on it. That being said, a particular medication can be listed in multiple different prescriptions. This is evident in the one to many relationship between Medications and Prescriptions.

## Data Model Screenshot
<img width="742" alt="Screenshot 2023-11-03 at 5 38 35 PM" src="https://github.com/mirLakhani/healthcare1/assets/148798235/b5d7190a-99f3-4f0b-8b53-54587d13b7ab">

## Data Dictionary Screenshots
<img width="723" alt="Billing" src="https://github.com/mirLakhani/healthcare1/assets/148798235/9f7f3440-4967-4e27-95d0-826d3ff32f5d">
<img width="700" alt="Contact" src="https://github.com/mirLakhani/healthcare1/assets/148798235/8a3d381f-00cf-4679-be51-c21f5fdc03b7">
<img width="708" alt="Equipment" src="https://github.com/mirLakhani/healthcare1/assets/148798235/b60a9b56-d79c-402d-9cd8-42585d468c9d">
<img width="697" alt="Medication" src="https://github.com/mirLakhani/healthcare1/assets/148798235/b35f8ac5-2817-44f1-a1a4-0adcf02624fb">
<img width="692" alt="Patient" src="https://github.com/mirLakhani/healthcare1/assets/148798235/73004685-0184-4ab6-a277-ba1e9c48b69e">
<img width="703" alt="Physician" src="https://github.com/mirLakhani/healthcare1/assets/148798235/a90cd7c4-d113-4c29-b297-18f1ef36153f">
<img width="643" alt="prescription" src="https://github.com/mirLakhani/healthcare1/assets/148798235/c5104983-bb3f-41e7-91bb-8f2369f6b2f0">
<img width="714" alt="Room" src="https://github.com/mirLakhani/healthcare1/assets/148798235/59f79f7e-2b4e-476e-9444-e5235c8011bc">
<img width="706" alt="Supplier" src="https://github.com/mirLakhani/healthcare1/assets/148798235/eaf32f54-677e-46ee-b700-0557202a2199">
<img width="696" alt="Test" src="https://github.com/mirLakhani/healthcare1/assets/148798235/d8b09d89-f3bf-4b0d-a5bb-b2b99badf11e">
<img width="683" alt="Visit" src="https://github.com/mirLakhani/healthcare1/assets/148798235/550d9aa0-552b-4711-bb7e-5e350cb7fd64">
<img width="685" alt="Visit Record" src="https://github.com/mirLakhani/healthcare1/assets/148798235/b2224cca-c2b7-420b-90ad-35bde5cf4844">


## Query Matrix
<img width="707" alt="Screenshot 2023-11-03 at 5 54 29 PM" src="https://github.com/mirLakhani/healthcare1/assets/148798235/e666f19e-c3d4-4fe2-8e4a-cd5538bde4a5">

Query 1:

Query 1 lists the equipment ID and name of equipment that is not currently assigned to a room.
<img width="712" alt="Query 1" src="https://github.com/mirLakhani/healthcare1/assets/148798235/7ad44341-e518-4f48-b0f6-b21a31da2c15">


The provided query is essential for management to identify equipment that is not currently assigned to any room, enabling efficient resource allocation and cost control. It would help managers identify which equipment could be allocated into rooms to ensure that they are maintaining operational efficiency within the medical center.

Query 2:

Query 2 lists physicians’ names who did not have any visits on April 29, 2023.
<img width="708" alt="Query 2" src="https://github.com/mirLakhani/healthcare1/assets/148798235/eae3ea90-a16d-4565-a7e7-022d3e9376f8">


This query can allow managers to quickly identify which physicians did not see any patients on a particular day. This will help them when they are scheduling the physicians for the upcoming weeks.

Query 3: 

Query 3 lists all physicians and the total number of visits they have conducted.
<img width="696" alt="Query 3" src="https://github.com/mirLakhani/healthcare1/assets/148798235/49f65154-dbab-4582-ba8c-5fce0cb71ffe">


This query allows managers to monitor physician progress and could be used for Employee of the Week purposes.

Query 4: 

Query 4 calculates the average price of equipment in each room.
<img width="678" alt="Query 4" src="https://github.com/mirLakhani/healthcare1/assets/148798235/19a588fd-7aa1-4ec4-bfb5-7f2e4fa94469">


This query allows the clinic managers to see which rooms they have invested the most money into for equipment, and which rooms they have invested the least in. It gives an idea of which rooms could use further investment in equipment in order to improve the care and treatment for patients.

Query 5:

Query 5 lists the patients with a total billing amount exceeding 3000 dollars.
<img width="689" alt="Query 5" src="https://github.com/mirLakhani/healthcare1/assets/148798235/ec8d9c19-a435-4e83-8aa1-323889b68423">


This query enables clinic managers to find which patients have spent $3000 or more on a single bill for a visit, in case the the managers would like to decide to give a future discount or rebate to those patients.

Query 6:

Query 6 lists the patient names and the number of visits they have whose status is not ‘Canceled’.
<img width="692" alt="Query 6" src="https://github.com/mirLakhani/healthcare1/assets/148798235/1ed30024-d1e0-43e3-8875-10d98c3924fc">


This query permits clinic managers to identify the number of visits a patient has scheduled and actually attended. Canceled appointments are frequent occurrences for clinics. Therefore it is important for managers to have the ability to omit them when finding the number of appointments a patient has had.

Query 7:

Query 7 displays the name (last name and first name concatenated) of the physician and the amount of billing he has generated. Order results in a descending value of dollars’ worth of billing.
<img width="692" alt="Query 7" src="https://github.com/mirLakhani/healthcare1/assets/148798235/3a105f23-c3ee-434d-b9e7-588d0617e932">


This query grants the clinic the capability to find the total billing amount each doctor has generated. There are numerous reasons this is valuable. For instance, a physician could be overcharging patients accidentally, or maybe the clinic is interested in seeing the physicians who have produced the most revenue so that the clinic can give them a salary bonus.

Query 8:

Query 8 lists the five suppliers that have supplied the most medications, and the number of medications have they have supplied
<img width="693" alt="Query 8" src="https://github.com/mirLakhani/healthcare1/assets/148798235/2ecaa742-b848-4efc-85a1-36b78a6289ae">


This query provides a rundown of the suppliers that have supplied the highest number of medications. This is important because it can help managers identify which suppliers the clinic should consider negotiating better terms with. 

Query 9:

Query 9 lists the visit with the highest number of tests performed.
<img width="694" alt="Query 9" src="https://github.com/mirLakhani/healthcare1/assets/148798235/ba9411cb-fb92-4886-8b01-34d94c4f2b27">


This query allows managers to identify the highest amount of tests conducted during one visit. Perhaps they are considering adding an additional charge if a certain number of tests are conducted, and they wish to see the largest number in order to help them make a more informed decision.

Query 10:

Query 10 lists the number of bills of each patient with an amount that is greater than their own average bill amount.
<img width="685" alt="Query 10" src="https://github.com/mirLakhani/healthcare1/assets/148798235/30c81e2d-4e0e-43e9-bed8-2fbbf84ba35f">


This query allows the clinic staff to give more detailed information on billing to their patients. A patient who has had numerous visits may want to know the number of visits that have exceeded the average billing amount of one of their own visits.

## Database Information
Name of Database: ns_F2339217Group7
