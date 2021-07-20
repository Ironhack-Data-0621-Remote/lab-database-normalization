# NORMALIZATION SAKILA DATABASE

Following this steps to bring the sakila database in a normalized form:  \
showing the starting point, normalize it (1NF, 2NF, 3NF), visualize the reult with db diagramm

This is how the database sakila looks before normalization: 
![photo](https://raw.githubusercontent.com/CharlotteStiller/lab-database-normalization/main/Sakila_Before_N.JPG)

## 1NF - First normal form  \
**Rules for 1NF**  \
Rule 1 - Each table cell should contain a single value.

I check if there are any cells with more than one single value and found two columns with more than one value: 

In the "address" table are two values in one column "address" (street, house number). I decided to not split street and house number, because there will be no relevance to order/filter the costumers after their house number or street. 

In the "film" table are more than one value in the "special_features" column. So in the first normal form I would split the different values from the column "special_features" and have multiple columns with the same film_id (and the columns that comes with this film_id) - like the table below shows. 

| film_id | special_feature |
| ------------------ | ------------------ |
| 156 | Commentaries |
| 156 | Deleted Scenes | 
| 156 | Trailers |
| 157 | Commentaries | 



## 2NF  - Second normal form
**Rules for 2NF**  \
Rule 1 - Be in 1NF  \
Rule 2 - Single Column Primary Key that does not functionally dependant on any subset of candidate key relation  \

1) film - special_features
I decided to give the different special_feature from 1NF a key value and put them in a new table special_feature. So every film_id is a single columns primary key in the "film" table.

| special_feature | special_feature_id |
| ------------------ | ------------------ |
| Trailers | 1 |
| Deleted Scenes | 2 | 
| Commentaries | 3 |
| Behinde the Scenes | 4 | 

To connect the information from the column "special_features_id" to the "film_id" I created a new table "film_special_features":

| film_id | special_feature_id |
| ------------------ | ------------------ |
| 156 | 3 |
| 156 | 2 | 
| 156 | 1 |
| 157 | 3 | 

After this I could delete the column "special_features" from the "film" table.


2) film - original_language_id
There is no information connected to the original_language_id, so there are only null values and no functional values. For this reason I decided to delete this column from the table "film". 


## 3NF  \
**Rules for 2NF**  \
Rule 1 - It is in the Second Normal form  \
Rule 2 - And, it doesn't have Transitive Dependency  \


1) rental 
All Informations from the "costumer_id" is already connected through they "payment" table. So I decided to deleted the the columns "customer_id" from the "rental" table. 
For the "staff_id" it is the same. Because the "rental_id" and "staff_id" are allready in the "payment" table connected. 

2) store 
The information about the adress of the store is also given in the "staff" table, so I decided to delete the "adress_id" from the "store" table. 


## new structure 
I ordered the table so the connections are all clear and the film informations is on the right side. You are able to see all the primary/foreign keys in the table itselfs. The same for the inventory 


This is how the database sakila looks after normalization: 
![photo](https://github.com/CharlotteStiller/lab-database-normalization/blob/main/Sakila_After_N.png?raw=true)




Links:  \
https://dbdiagram.io/  \
https://www.guru99.com/database-normalization.html  \
https://www.studytonight.com/dbms/database-normalization.php  \
