# Node.js PostgreSQL Express CRUD operation

This is a simple RESTful API built with Node.js, Express, and PostgreSQL. The API provides CRUD operations for managing users.

## Installation


1. **Install dependencies**:

   ```bash
   npm install
   ```

2. **Set up PostgreSQL database**:

   Ensure you have PostgreSQL installed and running. Create a database named `node-postgres` and a table `users` with the following SQL command:

   ```sql
   CREATE TABLE users (
     id SERIAL PRIMARY KEY,
     name VARCHAR(100) NOT NULL,
     email VARCHAR(100) UNIQUE NOT NULL
   );
   ```

## Configuration


1. **Update PostgreSQL client setup**:

   Ensure the `pool` configuration in `index.js` matches your database credentials.

## Usage

1. **Start the server**:

   ```bash
   npm start
   ```

   The server will start on port `3000` or the port specified in the `.env` file.

2. **Access the API**:

   You can now access the API at `http://localhost:3000`.

## Endpoints

- **Create User**  
  `POST /users`  
  Request body: `{ "name": "John Doe", "email": "john.doe@example.com" }`  
  Response: `201 Created` with the newly created user.

- **Get All Users**  
  `GET /users`  
  Response: `200 OK` with a list of all users.

- **Get User by ID**  
  `GET /users/:id`  
  Response: `200 OK` with the user object or `404 Not Found` if the user does not exist.

- **Update User**  
  `PUT /users/:id`  
  Request body: `{ "name": "John Doe", "email": "john.doe@example.com" }`  
  Response: `200 OK` with the updated user or `404 Not Found` if the user does not exist.

- **Delete User**  
  `DELETE /users/:id`  
  Response: `200 OK` with a deletion message or `404 Not Found` if the user does not exist.


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
