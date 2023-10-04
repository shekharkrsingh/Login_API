# Login_API
Certainly, let's provide detailed instructions to help users use  API effectively and avoid common errors:

---

## Comprehensive User Guide for Your API

### Introduction
This user guide offers a comprehensive overview of your API for managing user data within a MongoDB database. It not only covers installation but also provides detailed information on each API endpoint and practical tips to ensure smooth usage.

### Prerequisites
Before using this API, ensure you have the following prerequisites in place:

1. **Node.js and npm**: Install Node.js and npm (Node Package Manager) on your machine if not already installed.

2. **MongoDB**: Have MongoDB installed and running either locally or on a remote server. Ensure the MongoDB connection URL in your `.env` file correctly points to your database.

### Installation
To set up and run your API without any errors, follow these steps:

1. **Clone the Repository**: Clone the project repository to your local machine.

2. **Navigate to the Project Directory**: Open your terminal or command prompt and navigate to the project's root directory.

3. **Install Dependencies**: Execute the following command to install the necessary dependencies:
   ```bash
   npm install
   ```

4. **Create an Environment File**: In the project's root directory, create a file named `.env` and define the following environment variables:
   ```env
   PORT=7000
   DATABASE_URL=mongodb://127.0.0.1:27017/userDB
   ```
   Adjust the `PORT` and `DATABASE_URL` values as needed.

5. **Start the API Server**: Launch the API server with the following command:
   ```bash
   npm start
   ```

### API Endpoints

#### 1. Create a User
- **Endpoint:** `POST /api/v1/createUser`
- **Description:** Use this endpoint to create a new user. To avoid errors, make sure to provide the required user details accurately in the request body.

   **Request Body Tips:**
   - `firstName` and `lastName`: Enter the user's first and last name.
   - `email`: Use a unique email address for each user.
   - `phoneNo`: Provide a valid phone number.
   - `password`: Ensure the password is secure and not easily guessable.
   - `profileImageLink`, `DOB`, and `address`: Optional fields for additional user information.

#### 2. Update a User
- **Endpoint:** `PUT /api/v1/updateUser`
- **Description:** Use this endpoint to update an existing user's information. To prevent errors, include the unique user ID and provide updated user details accurately.

   **Request Body Tips:**
   - `_id`: Ensure the correct user ID is provided.
   - Include the same fields as in the "Create a User" endpoint for the updated information.

#### 3. Delete a User
- **Endpoint:** `DELETE /api/v1/deleteUser`
- **Description:** Use this endpoint to delete a user by providing their unique ID. Be cautious when using this endpoint as it permanently removes the user from the database.

   **Request Body Tips:**
   - `_id`: Double-check the user ID to avoid accidental deletions.

#### 4. Get a User
- **Endpoint:** `GET /api/v1/getUser`
- **Description:** Retrieve user data by specifying their email and password. To ensure success, provide the correct email and password combination.

   **Request Body Tips:**
   - `email` and `password`: Verify the accuracy of these credentials to retrieve the correct user data.

### Error Handling
- If an error occurs during API requests, the API will return a 500 Internal Server Error with a JSON response containing an error message.

### Handling Duplicate Emails
- The API handles scenarios where a user tries to create an account with an email that already exists or update a user's email to an email already associated with another user.
- When creating or updating a user:
   - If the email is already in use, the API returns a 400 Bad Request error with the message "Email address is already in use."

### Conclusion
This comprehensive user guide equips you with detailed instructions to use your API effectively and avoid common errors. Test your API with tools like Postman to ensure it functions as expected. Implement robust error handling in your application to gracefully handle API responses and errors.

For more advanced usage or integration into your application, refer to the API code and its respective files for detailed implementation.

Happy coding!
