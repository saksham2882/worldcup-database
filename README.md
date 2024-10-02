# World Cup Database Project

Welcome to the **World Cup Database** project, created as part of the [freeCodeCamp Relational Database Certification](https://www.freecodecamp.org/learn). This project demonstrates fundamental database management skills, including database design, data manipulation, and query writing using **PostgreSQL**. The project revolves around a real-world scenario of storing and querying data from the FIFA World Cup.

## Project Structure

This repository contains the following files necessary for the completion and functionality of the project:

- **`worldcup.sql`**: A SQL dump file that includes the schema and data required to set up the World Cup database.
- **`games.csv`**: A CSV file containing historical World Cup match data, including year, round, teams involved, and the scoreline.
- **`insert_data.sh`**: A Bash script designed to read data from `games.csv` and insert the relevant data into the database.
- **`queries.sh`**: A script containing SQL queries to extract insights and information from the database.
- **`expected_output.txt`**: The expected output of the queries, used for validation purposes.

## Database Schema

The database consists of two tables:

- **`teams`**:
  - `team_id`: A unique serial identifier for each team (Primary Key).
  - `name`: A unique text field representing the team's name.
  
- **`games`**:
  - `game_id`: A unique serial identifier for each game (Primary Key).
  - `year`: The year the game was played.
  - `round`: The tournament round (e.g., Group Stage, Final).
  - `winner_id`: A foreign key referencing the winning team's `team_id` from the `teams` table.
  - `opponent_id`: A foreign key referencing the opponent team's `team_id` from the `teams` table.
  - `winner_goals`: The number of goals scored by the winning team.
  - `opponent_goals`: The number of goals scored by the opponent.

## Features

- **Efficient Data Management**: Utilizes PostgreSQL for relational data management, ensuring efficient data storage and retrieval.
- **Automated Data Insertion**: The `insert_data.sh` script automates the process of reading data from a CSV file and inserting it into the appropriate database tables.
- **Complex Queries**: The `queries.sh` script demonstrates SQL querying techniques for extracting valuable insights from the dataset.

## Instructions for Use

### 1. Database Setup

To set up the database, run the following command to create and initialize the `worldcup` database using the provided `worldcup.sql` file:

```bash
psql -U freecodecamp -f worldcup.sql
```

### 2. Insert Data

Run the following command to populate the database from `games.csv`:

```bash
./insert_data.sh
```

### 3. Query the Database

To extract insights from the data, run the `queries.sh` script:

```bash
./queries.sh
```

It includes queries to retrieve:

- Total number of goals scored.
- Average goals by winning teams.
- List of teams playing specific rounds.
- Champions by year.

### 4. Backup and Restore the Database

#### Backup

You can back up the database using:

```bash
pg_dump -cC --inserts -U freecodecamp worldcup > worldcup.sql
```

#### Restore

To restore the database, use:

```bash
psql -U postgres < worldcup.sql
```

## Contributing

Contributions are welcome! Fork the repository, create a new branch for your feature, and submit a pull request.

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT). See the [LICENSE]() file for more details.

## Acknowledgements

This project is part of the [freeCodeCamp](https://www.freecodecamp.org/learn) curriculum. Thanks to the [freeCodeCamp](https://www.freecodecamp.org) community for support and resources.
