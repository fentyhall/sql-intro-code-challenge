# Intro to Databases & SQL

## Part 1: Conceptual questions
1. Why do our applications need databases?
1. What is SQL?
3. What is a relational vs. non-relational database?

## Part 2: Coding Challenge - Building the DB and making some queries
* You've been working on building a real estate application for your friend. So far, you've done some domain modeling, mapped out the models and their relationships, and built classes with methods to reflect these relationships. Your friend tests out the app so far and notices that every time he closes it and reopens it, all of the listings and agents disappear and he has to start adding data from scratch. He is requesting that you add some data persistence to the application. You decide to use a sqlite3 database, which you can communicate with via SQL.
* Use SQL commands to accomplish the following:
1. Create a `real_estate` database
    sqlite3 real_database.db

2. Create a table for the `agents` with necessary attributes
    ```sql
    CREATE TABLE agents (
    id INTEGER PRIMARY KEY,
    name TEXT,
    telephone TEXT,
    yrs_experience INTEGER
    );
    ```

3. Check your database `schema` to make sure everything looks as intended
    .schema

4. Add two new agents to the agents table
    ```sql
    sqlite> INSERT INTO agents (name, telephone, yrs_experience) VALUES ("Daniel", "222-222-2222", 16);
    sqlite> INSERT INTO agents (name, telephone, yrs_experience) VALUES ("Wayne", "337-222-2222", 17);
    ```

5. Write a query to return all the agents
    ```sql
    .headers on
    .mode column
    SELECT * FROM agents;
    id          name        telephone     yrs_experience
    ----------  ----------  ------------  --------------
    1           Daniel      222-222-2222  16            
    2           Wayne       337-222-2222  17       
    ```

6. Write a query to return all the agents with above 16 years of experience
    ```sql
    SELECT *
    FROM agents
    WHERE yrs_experience > 16;
    id          name        telephone     yrs_experience
    ----------  ----------  ------------  --------------
    2           Wayne       337-222-2222  17            
    ```

7. Create a table for the `listings` with necessary attributes (location, status, price)
    ```sql
    CREATE TABLE listings (
    id INTEGER PRIMARY KEY,
    location TEXT,
    status TEXT,
    price INTEGER, 
    agent_id INTEGER);
    ```

8. Bonus: How can you represent that a listing belongs to an agent in your db? Alter the `listings` table to reflect this relationships. Write a query to create a new listing that belongs to the first agent you created
    ```sql
    SELECT listings.*, agents.name AS agent_name, agents.yrs_experience
    FROM listings
    JOIN agents
    ON listings.agent_id = agents.id;
    ```