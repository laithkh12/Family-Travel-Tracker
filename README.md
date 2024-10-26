# Country Visited Tracker

This project is a web application built with Node.js, Express, and PostgreSQL that allows users to track countries they have visited. Users can add countries to their list, switch between different users, and add new users with personalized color preferences.

## Features

- Track visited countries for each user.
- Add new countries and associate them with the current user.
- Switch between existing users or add new users with custom colors.
- User-friendly interface built with EJS templates.

## Technologies Used

- Node.js
- Express
- PostgreSQL
- dotenv (for environment variable management)
- EJS (Embedded JavaScript templates)

## Prerequisites

Make sure you have the following installed:

- [Node.js](https://nodejs.org/)
- [PostgreSQL](https://www.postgresql.org/)
- [npm](https://www.npmjs.com/)

## Setup

1. **Clone the repository**:

   ```bash
   git clone https://github.com/your-username/country-visited-tracker.git
   cd country-visited-tracker
   ```
2. **Install dependencies:
   ```bash
   npm install
   ```
3 **Set up PostgreSQL:
  ```bash
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(50),
  color VARCHAR(20)
);

CREATE TABLE countries (
  country_code VARCHAR(3) PRIMARY KEY,
  country_name VARCHAR(50)
);

CREATE TABLE visited_countries (
  id SERIAL PRIMARY KEY,
  country_code VARCHAR(3) REFERENCES countries(country_code),
  user_id INTEGER REFERENCES users(id)
);
```
4. **Configure environment variables:
   ```bash
   DB_PASSWORD=your_postgres_password
   ```
5. **Run the server:
   ```bash
   node app.js
   ```

## Usage
- Open a browser and go to http://localhost:3000.
- You will see a list of visited countries for the current user.
- Use the input box to add new countries by name.
- Switch between users using the dropdown or add new users with custom colors.

## File Structure
- app.js: Main server file, contains route handling and database queries.
- public/: Contains static assets.
- views/: Contains EJS templates for rendering HTML.
- .env: Environment file to store sensitive data like database password.

## Dependencies
- express: Web framework for Node.js.
- body-parser: Middleware to parse incoming request bodies.
- pg: PostgreSQL client for Node.js.
- dotenv: Loads environment variables from .env.
- ejs: Embedded JavaScript templates for rendering dynamic content.
