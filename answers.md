
    1. Selects the names of all products that are not on sale.

    sqlite> select * from products where on_sale = 'f';
    1|2013-04-01 20:09:41.969902|Teddy Bear|17.99|f
    3|2013-04-01 20:09:41.973999|Cat Ears|99.99|f
    6|2013-04-01 20:09:41.978579|Card Against Humanity|25.0|f
    9|2013-04-01 20:09:41.983386|Set of 12 Mason Jars|6.22|f


    2. Selects the names of all products that cost less than £20.
    
    sqlite> select * from products where price < 20;
    1|2013-04-01 20:09:41.969902|Teddy Bear|17.99|f
    4|2013-04-01 20:09:41.975612|The Ruby Programming Language|19.99|t
    5|2013-04-01 20:09:41.977249|Silicon Valley Monopoly|10.99|t
    9|2013-04-01 20:09:41.983386|Set of 12 Mason Jars|6.22|f

    3. Selects the name and price of the most expensive product.
    
    sqlite> select name, MAX(price) from products;
    Cat Ears|99.99


    4. Selects the name and price of the second most expensive product.

    sqlite> select name, MAX(price) from products where price < (select MAX(price) from products);
    Brown Leather Boots|82.0    

    5. Selects the name and price of the least expensive product.

    sqlite> select name, MIN(price) from products;
    Set of 12 Mason Jars|6.22

    6. Selects the names and prices of all products, ordered by price in descending order.

    sqlite> select name, price from products ORDER BY price DESC;
    Cat Ears|99.99
    Brown Leather Boots|82.0
    Lonely Pillow|78.82
    Card Against Humanity|25.0
    Hoodie|25.0
    Set of silverware|22.99
    The Ruby Programming Language|19.99
    Teddy Bear|17.99
    Silicon Valley Monopoly|10.99
    Set of 12 Mason Jars|6.22

    7. Selects the average price of all products.

    sqlite> select *, AVG(price) from products;
    10|2013-04-01 20:09:41.984861|Set of silverware|22.99|t|38.899

    8. Selects the sum of the price of all products.

    sqlite> select *, SUM(price) from products;
    10|2013-04-01 20:09:41.984861|Set of silverware|22.99|t|388.99

    9. Selects the sum of the price of all products whose prices is less than £20.

    sqlite> select *, SUM(price) from products where price < 20;
    9|2013-04-01 20:09:41.983386|Set of 12 Mason Jars|6.22|f|55.19

    10. Selects the id of the user with your name.

    sqlite> select id from users where name = "Elena Sanna";
    12

    11. Selects the names of all users whose names start with the letter "J".
    
    sqlite> select name from users where name like 'J%';
    Jon Rogers
    James Gotsell


    12. Selects the number of users whose first names are "Spencer".
    
    sqlite> select name from users where name like 'Spencer%';
    Spencer Meyer

    13. Selects the number of users who want a "Teddy Bear".

    sqlite> select name from products where name like 'Teddy Bear%';
    Teddy Bear

    14. Selects the count of items on the wishlish of the user with your name.

    select count(items) from wishlist where name = "Elena Sanna";


    select count(w.product_id) 
    from wishlists as w 
      join users as u
      on w.user_id = u.id
    where u.name = "Elena Sanna";
    8

    15. Selects the count and name of all products on the wishlist, ordered by count in descending order.

    select name, count(name) from products join wishlists as w on w.product_id = products.id group by name order by count(name) desc;
    Hoodie|17
    Card Against Humanity|16
    Cat Ears|15
    The Ruby Programming Language|9
    Teddy Bear|6
    Silicon Valley Monopoly|5
    Brown Leather Boots|4
    Lonely Pillow|2
    Set of 12 Mason Jars|2


    16. Selects the count and name of all products that are not on sale on the wishlist, ordered by count 
    in descending order.


    17. Inserts a user with the name "Jonathan Anderson" into the users table. Ensure the created_at column is set to the current time.
    
    insert jonathan anderson cos it doesnt exist
    <!-- sql insert time -->

    18. Selects the id of the user with the name "Jonathan Anderson"?
    
    select id from users where name = "johnathan Anderson3";
    17

    19. Inserts a wishlist entry for the user with the name "Jonathan Anderson" for the product "The Ruby Programming Language".
    

    20. Updates the name of the "Jonathan Anderson" user to be "Jon Anderson".
    

    21. Deletes the user with the name "Jon Anderson".
    

    22. Deletes the wishlist item for the user you just deleted.
Please supply SQL statements, and the results they generate.
###Hints
  - As with anything, if you get stuck, move on, then go back if you have time.
  - Don't spend all night on it!
  - Use the resources on teh internetz to solve harder ones - there are solutions to these questions that work with what we've learnt today, but other tools exist in SQL that could make the queries 'better' or 'easier'.
Add Comment






