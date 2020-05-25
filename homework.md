# SQL Homework

The Springfield Cinema is having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'

```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:

```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1.  Return ALL the data in the 'movies' table.

    SELECT * FROM movies;

 id |                title                | year | show_time 
----+-------------------------------------+------+-----------
  1 | Iron Man                            | 2008 | 12:50
  2 | The Incredible Hulk                 | 2008 | 15:15
  3 | Iron Man 2                          | 2010 | 12:35
  4 | Thor                                | 2011 | 15:15
  5 | Captain America: The First Avenger  | 2011 | 23:35
  6 | Avengers Assemble                   | 2012 | 13:05
  7 | Iron Man 3                          | 2013 | 22:50
  8 | Thor: The Dark World                | 2013 | 20:05
  9 | Batman Begins                       | 2005 | 20:00
 10 | Captain America: The Winter Soldier | 2014 | 21:35
 11 | Guardians of the Galaxy             | 2014 | 20:50
 12 | Avengers: Age of Ultron             | 2015 | 22:45
 13 | Ant-Man                             | 2015 | 18:45
 14 | Captain America: Civil War          | 2016 | 17:25
 15 | Doctor Strange                      | 2016 | 18:00
 16 | Guardians of the Galaxy 2           | 2017 | 15:30
 17 | Spider-Man: Homecoming              | 2017 | 17:50
 18 | Thor: Ragnarok                      | 2017 | 20:00
 19 | Black Panther                       | 2018 | 14:05
(19 rows)


2.  Return ONLY the name column from the 'people' table

SELECT title FROM movies;
               title                
-------------------------------------
 Iron Man
 The Incredible Hulk
 Iron Man 2
 Thor
 Captain America: The First Avenger
 Avengers Assemble
 Iron Man 3
 Thor: The Dark World
 Batman Begins
 Captain America: The Winter Soldier
 Guardians of the Galaxy
 Avengers: Age of Ultron
 Ant-Man
 Captain America: Civil War
 Doctor Strange
 Guardians of the Galaxy 2
 Spider-Man: Homecoming
 Thor: Ragnarok
 Black Panther
(19 rows)

3.  Oops! Someone spelled Krusty The Clown's name wrong! Change it to reflect the proper spelling (Crusty should be Krusty).

    UPDATE people SET name = 'Krusty the Clown' WHERE name = 'Crusty the Clown';

      UPDATE 1

4.  Return ONLY Homer Simpson's name from the 'people' table.

SELECT name FROM people WHERE name = 'Homer Simpson';


                name      
        ---------------
        Homer Simpson
        (1 row)


5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

   DELETE FROM movies WHERE title = 'Batman Begins';

    DELETE 1


6.  We forgot one of the main characters! Add Bart Simpson to the 'people' table

    INSERT INTO people (name) VALUES ('Bart Simpson');
      
      INSERT 0 1

7.  Eric Cartman has decided to hijack our movie evening, Remove him from the table of people.

    DELETE FROM people WHERE name = 'Eric Cartman';
        DELETE 1

8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.

    INSERT INTO movies (title, show_time) VALUES ('Avengers: Infinity War', '00:00');
      INSERT 0 1

9.  The cinema would like to make the Iron Man movies a triple billing. Find out the show time of "Iron Man 2" and set the show time of "Iron Man 3" to start two hours later.

    UPDATE movies SET show_time = '14:35' WHERE title = 'Iron Man 3';
        UPDATE 1


## Extension

1.  Research how to delete multiple entries from your table in a single command.

      DELETE FROM table WHERE id IN (value1, value2, value3);
      DELETE FROM table WHERE id BETWEEN value1 AND value2;
