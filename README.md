Here’s a structured of To-Do application. This document outlines the application features, authentication, CRUD operations, and RESTful API usage.

---

# To-Do Application

**Members:**  
- 13283475 Kaur Sandeep
- 13384981 Chu Cheuk Sang
- 13226493 Yau Wa Kin 
- 13345250 Ng Tsz Kin
- 12531103 LIN JUNSHAN

**Application Link:**  
- [To-Do App](http://localhost:8099)

********************************************

## Login

Through the login interface, each user can access the To-Do application by entering their Facebook credentials.

Each user is authenticated via Facebook, which provides a user ID and basic profile information.

After successful login, the user ID is stored in the session.

********************************************

## Logout

Users can log out of their accounts by clicking the logout button on the home page.

********************************************

## CRUD Service

### Create

- A task document may contain the following attributes with an example:
  1. **Task Name** (Buy groceries)
  2. **Task ID** (Auto-generated)
  3. **User ID** (122098074998635674)
  4. **Due Date** (2023-12-01)

POST Request: Used for creating tasks with information sent in the request body.


********************************************
## Task Attributes

A task document in this application may contain the following attributes:

1. **Task Name**: Represents the name or description of the task.
2. **Due Date**: Indicates the deadline by which the task should be completed.


### Read

 **List All Tasks**: 
  - Task Listing: The list.ejs page displays all tasks associated with the logged-in user. Tasks are presented in a clean and organized manner, showing the task name and due date.
  - Task Details: Users can click on a task to view its details, providing more information about the task.
  - Task Editing: Users have the option to edit tasks by clicking on the edit icon (🖋️) next to each task. This functionality allows users to make changes to task details.
  - Task Deletion: Tasks can be deleted by clicking on the "Delete" link associated with each task. A confirmation prompt ensures that the user intends to delete the task.
  - Task Creation: Users can easily add new tasks by clicking the "Add a New Task" link, which directs them to the task creation page.
  - User Authentication: The application supports user authentication, displaying the user's name and type upon login.

********************************************

### Update

Users can update their tasks by following these steps:

1. Navigate to the details interface for the task you want to update.
2. Edit the task name and due date as needed.
3. Save the changes by clicking the "Update" button.
- A task document may contain the following attributes with an example:
  1. **Task Name** (Submit report)
  2. **Due Date** (2023-12-05)

In this example, we updated the task name and due date.

********************************************

### Delete

Users can delete tasks by following these steps:

1. Navigate to the task you want to delete.
2. Click on the "Delete" link associated with the task.
3. Confirm the deletion when prompted.

********************************************

## RESTful API

In this project, there are 4 HTTP request types: GET, POST, PUT, DELETE.

### POST

The POST request is used to insert a new task record.  
**Path URL:** `/api/tasks`  
**Test:** 
```bash
curl -X POST http://localhost:8099/api/record \
  -H "Content-Type: application/json" \
  -d '{"task": "Your Task Name", "date": "Task Date"}'
```

### GET

The GET request is used to retrieve task information.  
**Path URL:** `/api/tasks/:taskID`  
**Test:**
```bash
curl http://localhost:8099/api/record
```


### PUT

The PUT request is used to update task information.  
**Path URL:** `/api/tasks/:taskID`  
**Test:**
```bash
curl -X PUT http://localhost:8099/api/record \
  -H "Content-Type: application/json" \
  -d '{"task": "Updated Task Name", "date": "Updated Task Date"}'
```

### DELETE

The DELETE request is used to delete a task record.  
**Path URL:** `/api/tasks/:taskID`  
**Test:**
```bash
curl -X DELETE http://localhost:8099/api/record/TaskNameToDelete
```


