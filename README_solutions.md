# Normalizing Sakila database
## 1NF
The Sakila database is already in 1NF as each cell (to my experience) only contains 1 value
## 2NF
The Sakila database is already in 2NF as there are no multiple functional dependencies within any table.
However, the 'film_text' table seems redundant, as all the information is already available in the 'film' table. Hence, this table is deleted in the proposed new structure. 
## 3NF
