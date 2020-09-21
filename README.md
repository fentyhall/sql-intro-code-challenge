# Intro to Databases & SQL

## Part 1: Conceptual questions
1. Why do our applications need databases?
1. What is SQL?
3. What is a relational vs. non-relational database?

## Part 2: Coding Challenge - Building the DB and making some queries
* You've been working on building a real estate application for your friend. So far, you've done some domain modeling, mapped out the models and their relationships, and built classes with methods to reflect these relationships. Your friend tests out the app so far and notices that every time he closes it and reopens it, all of the listings and agents disappear and he has to start adding data from scratch. He is requesting that you add some data persistence to the application. You decide to use a sqlite3 database, which you can communicate with via SQL.
* Use SQL commands to accomplish the following:
1. Create a `real_estate` database
2. Create a table for the `agents` with necessary attributes
3. Check your database `schema` to make sure everything looks as intended
4. Add two new agents to the agents table
5. Write a query to return all the agents
6. Write a query to return all the agents with above 5 years of experience
7. Create a table for the `listings` with necessary attributes (location, status, price)
8. Bonus: How can you represent that a listing belongs to an agent in your db? Alter the `listings` table to reflect this relationships. Write a query to create a new listing that belongs to the first agent you created