


## Problem Statement

As a backend developer, your task is to enhance the database functionality for user management in the application. This involves user registration, login, logout, and password updates. The goal is to ensure smooth database operations and effective validation of user data.

## Objective

Create a user registration schema in `src/features/user/user.schema.js`  with the following validations:

-   `name`: A required string with a minimum length of 3 characters.
-   `email`: A unique, required string with a valid email format.
-   `mobile`: A unique, required string.
-   `age`: A required number between 0 and 100.
-   `password`: A required string.
-   `type`: A required string and can be either 'student,' 'fresher,' or 'experienced'.

Implement the `userRegistration` controller and its corresponding `userRegistrationRepo` function in the user repository to handle user registration. If any field is found to be invalid during the registration process, ensure that the user receives an appropriate error message along with a 400 Bad Request status code.

Additionally, ensure that the `userRegistrationRepo` function returns the following:

For a valid request body:


```json
{
  "success": true,
  "res": userdocument
}
``` 

For errors or an invalid request body:

```json
{
  "success": false,
  "error": {
    "statusCode": statuscode,
    "msg": "error message"
  }
}
```
Maintain the specified return types, as the 'userRegistrationRepo' function is used by the 'userRegistration' controller to provide the user with the appropriate response based on the response received from it.

For further details, please refer to the provided video link under 'Expected Output'.

Implement the 'userLoginRepo' function within the user repository to manage user login operations. Ensure that it returns the following:

For valid credentials:

```json
{
  "success": true,
  "res": user_document
}
```
For errors or invalid credentials:


```json
{
  "success": false,
  "error": {
    "statusCode": status_code,
    "msg": "error message"
  }
}
``` 

Maintain these specified return types as the `userLoginRepo` function is utilized by the `userLogin` controller to provide users with appropriate responses based on the received output.

Implement the `updateUserPassword` controller and its corresponding `updateUserPasswordRepo` function in the user repository for updating user passwords.

The route for password updates is `/codingninjas/api/user/update/password` which is a POST request. Only the user's new password should be passed in the request body, and you can retrieve the `_id` of the logged-in user from `req._id` (refer `jwtAuth` middleware for the logic).



## Setup

1.  Clone the repository.
2.  Install dependencies using `npm install`.
3.  Run the application using `npm start`.

