# Task Manager API

A simple task management API built with Node.js and Express. This API provides CRUD operations for managing tasks, using in-memory storage (an array) to store task data.

## Getting Started

Prerequisites
 [Node.js](https://nodejs.org/) installed on your machine.

### Installation

1. Clone the repository or create a project folder:
   mkdir task-manager
   cd task-manager
Initialize the project and install dependencies:

bash

npm init -y
npm install express uuid
Create an index.js file and add the API code (see instructions below).

Running the Server
Start the server by running:

node index.js
The server will be running athttp://localhost:3000.

API Endpoints

1. Create a Task
Endpoint: POST /tasks
Description: Adds a new task.
Request Body:
json

{
  "title": "Sample Task",
  "description": "This is a sample task description"
}
Response:
Status: 201 Created
Body:
json

{
  "id": "unique-task-id",
  "title": "Sample Task",
  "description": "This is a sample task description",
  "completed": false
}
2. Retrieve All Tasks
Endpoint: GET /tasks
Description: Retrieves a list of all tasks.
Response:
Status: 200 OK
Body:
json

[
  {
    "id": "unique-task-id",
    "title": "Sample Task",
    "description": "This is a sample task description",
    "completed": false
  }
]
3. Update a Task
Endpoint: PUT /tasks/:id
Description: Updates a task by ID.
Request Params:
id (string): The unique ID of the task to update.
Request Body (any combination of fields can be provided):
json

{
  "title": "Updated Task Title",
  "description": "Updated description",
  "completed": true
}
Response:
Status: 200 OK
Body:
json

{
  "id": "unique-task-id",
  "title": "Updated Task Title",
  "description": "Updated description",
  "completed": true
}
4. Delete a Task
Endpoint: DELETE /tasks/:id
Description: Deletes a task by ID.
Request Params:
id (string): The unique ID of the task to delete.
Response:
Status: 204 No Content
Testing the API
You can use Postman to test each endpoint.

Notes
This project uses in-memory storage (an array) to hold tasks, so data will be lost when the server restarts.
