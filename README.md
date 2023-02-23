# Celestial Bodies Database Project
This is a database project for celestial bodies created using PostgreSQL. The project consists of 5 tables - galaxy, star, planet, moon, and blackhole - and includes information such as age of galaxy, color of star, and number of planets.

![](/images/database_schema.png)

## Getting Started

To use the database, follow these steps:

1. Install PostgreSQL on your local machine
2. Clone this repository
3. Create a new database in PostgreSQL using the createdb command (e.g. createdb celestial)
4. Restore the database using the pg_restore command (e.g. pg_restore -d celestial universe.sql)
5. Connect to the database using your preferred SQL client (e.g. pgAdmin, DBeaver, etc.)

## Usage
Once you have the database set up, you can start exploring the data by querying the tables using SQL commands. Here are some example queries:

1. Get a list of all galaxys on the db:  
    `SELECT * FROM galaxy;`
    ![](/images/galaxy_all.png)
    ---

    
2. Get a list of all stars in the Milky Way galaxy:  
    `SELECT * FROM star WHERE galaxy_id = (SELECT galaxy_id FROM galaxy WHERE name = 'Milky Way');`
    ![](/images/star_from_mily_way.png)   
    ---

    
3. Get a list of all planets that have at least one moon:  
    `SELECT planet.* FROM planet INNER JOIN moon ON planet.planet_id = moon.planet_id;`

    ![](/images/planet_one_moon.png)
