Below are few changes that were made based on 1NF, 2NF, and 3NF.

1.
Remove film_category table and add category_id in film table
-- category_id is dependent on film_id
-- even if a 'film' is deleted from the film table, the category table is there
-- in result, removing the redundency of the tables
2.
Remove film_text table
-- Redundency from film table
3.
Create a new table 'film_features' and add columns film_id, special features
-- special_features is violating 1NF 
4.
Other minor changes
changes: table film_text, film_id --> change to Foreign key
Replace: store_id from cutomer table to rental





