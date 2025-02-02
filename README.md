Reqres API Testing using Postman
This repository contains the manual API testing for the Reqres API (User Management) using Postman. The purpose of this project is to demonstrate API testing skills, covering common HTTP methods and response validation.

Table of Contents
1)Project Overview
2)API Endpoints Tested
3)Test Cases
4)How to Run the Tests
5)Technologies Used
6)Results
7)Contributing
8)Project Overview

In this project, I have created a set of test cases for validating the GET, POST, PUT, and DELETE API endpoints of the Reqres API using Postman. The tests cover various scenarios, including:

Valid responses
Invalid inputs
Boundary conditions
Response time validation
The goal of the project is to ensure that the API behaves as expected under different conditions and to showcase API testing skills.

API Endpoints Tested
Here are the API endpoints tested in this project:

GET /users?page=2
Fetch a list of users.

GET /users/2
Fetch details of a single user by ID.

POST /users
Create a new user with name and job.

PUT /users/2
Update details of an existing user by ID.

DELETE /users/2
Delete an existing user by ID.

Test Cases
1️⃣ GET: Fetch List of Users
Valid request: /users?page=2 → Response: 200 OK
Invalid page number: /users?page=999 → Response: 200 OK, empty list
Invalid characters in the page number: /users?page=$% → Response: handle gracefully
2️⃣ GET: Fetch a Single User
Valid user: /users/2 → Response: 200 OK
Non-existent user: /users/999 → Response: 404 Not Found
3️⃣ POST: Create a New User
Valid input: /users with {"name": "John", "job": "Engineer"} → Response: 201 Created
Missing name: /users with {"job": "Engineer"} → Response: validation error
Extra fields: /users with {"name": "John", "job": "Engineer", "age": 30} → Response: ignore extra fields
4️⃣ PUT: Update a User
Update existing user: /users/2 with {"name": "John", "job": "Senior Engineer"} → Response: 200 OK
Update non-existent user: /users/999 → Response: handle gracefully
5️⃣ DELETE: Remove a User
Delete existing user: /users/2 → Response: 204 No Content
Delete non-existent user: /users/999 → Response: handle gracefully
How to Run the Tests
1)Clone the repository to your local machine:
git clone https://github.com/HarshadNikate/reqres-api-testing.git
2)Import the Postman collection file (Reqres-API-Testing.postman_collection.json) into Postman.
3)Open the collection and run individual API requests or run all tests in the Collection Runner.
4)You will see the pass/fail results in the "Test Results" section.

Technologies Used
Postman: API testing tool to send requests and validate responses.
JavaScript: Writing test scripts in Postman.
GitHub: Version control and repository hosting.

Results
All test cases were executed successfully for positive scenarios.
Edge and negative cases were handled gracefully by the API.
Performance testing (response time) showed that the API responded in under 200ms for all requests.

Contributing
If you’d like to contribute to this project, feel free to fork the repository, create a branch, and submit a pull request.

License
This project is licensed under the MIT License - see the LICENSE file for details.

