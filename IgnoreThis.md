USE Sakila;
SHOW tables;

SELECT * from actor;
#1. Lists all actors

SELECT last_name from actor WHERE first_name = 'John';
#2. gives surname Suvari

SELECT * from actor WHERE last_name = 'Neeson';
#3. provides 2 rows, Christian and Jayne

SELECT * from actor WHERE actor_id % 10 = 0;
#4. Lists actor ids divisible by 10

SELECT title, description FROM film WHERE film_id = 100;
#5. Provides description

SELECT title FROM film WHERE rating = 'R';
#6. Lists titles of R movies

SELECT title FROM film WHERE rating != 'R';
#7. Lists non-R movies

SELECT * FROM film ORDER BY length ASC LIMIT 10;
#8. Lists 10 shortest movies

SELECT * FROM film ORDER BY length DESC;
#9. Lists films from longest length

SELECT * FROM film WHERE special_features LIKE '%Deleted Scenes%';
#10. Lists films with deleted scenes listed in special_features

SELECT * from actor GROUP BY last_name HAVING COUNT(last_name) >0 ORDER BY last_name DESC;
#11. Lists surnames reverse ABC with no repeats

SELECT last_name, COUNT(last_name) AS frequency FROM actor GROUP BY last_name HAVING COUNT(last_name)>1 ORDER BY frequency DESC;
#12. Shows surnames used more than once highest freq to lowest

SELECT * FROM actor a COUNT(actor_id) AS frequency FROM actor JOIN film_actor fa ON a.actor_id=fa.actor_id GROUP BY (last_name)>1 ORDER BY frequency DESC;

SELECT * from film_actor;
SELECT actor_id from film_actor ;
SELECT * from film_category;
SELECT * FROM category;
SELECT AVG(length) FROM film;
#15. gives average of 115.27

SELECT AVG(length) FROM film f JOIN film_category fc ON f.film_id=fc.film_id JOIN category c ON c.category_id=fc.category_id ORDER BY name DESC;
#16. almost there

SELECT * from film WHERE description LIKE '%robot%';
#17. lists all films where a robot is listed in description

SELECT COUNT(release_year) FROM film WHERE release_year = 2010;
#18. shows 0 released in 2010

SELECT title FROM film f JOIN film_category fc ON f.film_id=fc.film_id JOIN category c ON c.category_id=fc.category_id WHERE name = 'Horror';
#19. Lists all horror titles

SELECT first_name, last_name FROM actor WHERE actor_id = 2;
#20. gives Nick Wahlberg

SELECT title FROM film_list WHERE actors LIKE '%Fred Costner%';
#21. lists all films where appeared

SELECT COUNT(DISTINCT country) FROM country;
#22. Provides 109

SELECT name FROM language ORDER BY name DESC;
#23. Lists in reverse ABC

SELECT first_name, last_name from actor WHERE last_name LIKE '%son' ORDER BY first_name ASC;
#24. All names ending in son first name alphabetically

SELECT * from category;
SELECT * from film_category;

SELECT COUNT(film_id) AS category_id FROM category c JOIN film_category fc ON c.category_id=fc.category_id;
#25 work in progress
