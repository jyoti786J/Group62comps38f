Here’s a structured document similar to your example, tailored for your To-Do application. This document outlines the application features, authentication, CRUD operations, and RESTful API usage.

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

On the home page, each user can log out of their account by clicking the logout button.

********************************************

## CRUD Service

### Create

- A task document may contain the following attributes with an example:
  1. **Task Name** (Buy groceries)
  2. **Task ID** (Auto-generated)
  3. **User ID** (user123)
  4. **Due Date** (2023-12-01)


Task Name and User ID are mandatory, while other attributes are optional.

The create operation is a POST request, and all information is sent in the request body.

********************************************

### Read

 **List All Tasks**: 
   The `content.ejs` page will show all tasks associated with the logged-in user. By clicking on a task name, the details will be shown.

********************************************

### Update

- Users can update their task information through the details interface.
- Among the attributes shown above, the Task ID cannot be changed. Since the Task ID is fixed, it is used as a search criterion for updating information.

- A task document may contain the following attributes with an example:
  1. **Task Name** (Submit report)
  2. **Due Date** (2023-12-05)

In this example, we updated the task name and due date.

********************************************

### Delete

- Users can delete tasks they no longer need through the delete interface.

********************************************

## RESTful API

In this project, there are 4 HTTP request types: GET, POST, PUT, DELETE.

### POST

The POST request is used to insert a new task record.  
**Path URL:** `/api/tasks`  
**Test:** 
```bash
curl -X POST -H "Content-Type: application/json" --data '{"task": "Finish assignment", "date": "2023-11-30"}' http://localhost:8099/api/tasks
```

### GET

The GET request is used to retrieve task information.  
**Path URL:** `/api/tasks/:taskID`  
**Test:**
```bash
curl -X GET http://localhost:8099/api/tasks/123456
```

### PUT

The PUT request is used to update task information.  
**Path URL:** `/api/tasks/:taskID`  
**Test:**
```bash
curl -X PUT -H "Content-Type: application/json" --data '{"dueDate": "2023-12-10", "description": "Complete with additional notes."}' http://localhost:8099/api/tasks/123456
```

### DELETE

The DELETE request is used to delete a task record.  
**Path URL:** `/api/tasks/:taskID`  
**Test:**
```bash
curl -X DELETE http://localhost:8099/api/tasks/123456
```

Please note that for all RESTful CRUD services, proper authentication and authorization should be implemented.

To perform the operations, you can use the following curl commands:

- Create a new task record:
```bash
curl -X POST -H "Content-Type: application/json" --data '{"taskName": "Finish assignment", "dueDate": "2023-11-30"}' http://localhost:8099/api/tasks
```

- Retrieve task information:
```bash
curl -X GET http://localhost:8099/api/tasks/123456
```

- Update task information:
```bash
curl -X PUT -H "Content-Type: application/json" --data '{"dueDate": "2023-12-10"}' http://localhost:8099/api/tasks/123456
```

- Delete a task record:
```bash
curl -X DELETE http://localhost:8099/api/tasks/123456
```

---

