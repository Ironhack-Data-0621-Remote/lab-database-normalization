![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Lab | Database normalization | Sumampouw

### How to:

1. I use [dbdiagram.io](https://dbdiagram.io/home) to propose a new structure for the `Sakila` database.
2. The task asked to define primary keys and foreign keys for the new database.
3. Original sixteen table ![Sakila database](https://education-team-2020.s3-eu-west-1.amazonaws.com/data-analytics/3.4-lab-sakila-normalization.png)

### Deliverable

The Sakila database schema is shown below. Sixteen tables are representing a relatively easy-to-understand inventory of films, staff, customers, and stores. Sakila is a MySQL sample schema that the database based on a DVD rental system. 

I partially ignore my relational modeling experience when modeling schemas – “normalization” is not the desired end state. Instead of driving my decision on the nature of the data, I move it on operations. The most significant finding is which “entities” get linked. My first shot at mapping the data – which may prove flawed as I play with dbdiagramio – collapsed the sixteen tables into just three tables: FILMS, STORES, and CUSTOMERS. ACTORS became a nested document in FILMS, STAFF and INVENTORY were nested into STORES, while RENTALS and PAYMENTS nested into CUSTOMERS.   Whether these nestings turn out to be good design decisions will depend somewhat on the application. Some operations are going to be awkward, while others' data will expedite others.

#### New propose table: 
![photo](https://github.com/sumampouw/lab-database-normalization/blob/main/new_sakiladb_ss.png)
