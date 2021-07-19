# Lab | Sakila ER upadte descrption

### 1. ER reverse engineering

- Reverse engineering the current ER to get an overview of the status quo of the database relationships
- Identifying primary and foregn keys in every table 

### 2. Redundancies

- Checking for redundant columns across table and removing columns or tables when it makes sense
  > The table 'film_text' can be removed because all the information is already present in the table 'film'

### 3. Normalization

- Checking for 1NF
  > Assuming that every field in the database has only one value

- Checking for 2NF
  > There are no partial functional dependencies in the database

- Checking for 3NF
  > Column 'district in table 'address' transitive functional dependency with 'city_id'
  > 'country' is only referred to by 'city', 'city' is only reffered to by 'address'. 
  > New structure for addresses: a new table 'district' with 'district_id' as PK used in 'city' as a FK and includes 'country_id' as a FK

### 4. Key definitions

!(https://github.com/KevinSpurk/lab-database-normalization/blob/main/sakila_ERD_new.pdf)

