# Lab | Database normalization

**Task**: 
creating a new database structure with primary and foreign keys using [dbdiagram.io](https://dbdiagram.io/home)

## Normalization

### 1NF
no need to make changes as no cells contain more than one entry

### 2NF
no partial functional dependencies can be found in database

### 3NF
removing original language id in table "film"

## New structure
- deleting "film_text" as information is included in table "film" already
- adding category_id in table "film" to be able to remove table "film_category" 
- adding (payment_)amount and payment_date to table "rental" to be able to remove table "payment"
<br>
- reorganising tables to have a better overview of which tables are connected in which manner 


## Result of new ERD


### OPTIONAL changes to reduce amount of tables

Deleting tables with little information and adding them to existing tables: <br>

1. **Reason:** to have a better overview 
2. **Disadvantage:** adding redundant information to some tables (e.g. in table "address" info about city and country would appear for each staff member --> no problem with small amount of staff members, but for a huge company information might be redundant very easily)

 - integration of "city" + "country" in table "address" <br>
 - integration of "language" in table "film" <br>
 - integration of "category" in table "film" <br>