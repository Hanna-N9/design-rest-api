For the overall API, specify the following information:

- `Title` - Designing the REST API for a Task Management Application
- `Contact Email` - apiteam@swagger.io
- `Host` - api.tasks.testsite01.com
- `Schemes` - https

# **Path**: _/users_

- ## Create (`POST`)

  - Yes
  - Input (in: Body): JSON describing user
  - Output
    - 200 OK (Returns records & identifier in the body of response)
    - 400 Bad Request (Missing required information)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 409 Conflict (An error of trying to duplicate records)
    - 500 Internal Server Error (Something is wrong on the server side)

- ## Read (`GET`)

  - Yes
  - Input (none)
  - Output
    - 200 OK (Returns array of the list of the users in the JSON format)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 404 Not Found (“users” request does not exist)
    - 500 Internal Server Error (Something is wrong on the server side)

- ## Update (`PUT`)

  - Output
    - 405 Method Not Allowed (Can’t update a user without knowing their identifier)

- ## Delete (`DELETE`)
  - Output
    - 405 Method Not Allowed (Can’t delete a user without knowing their identifier)

# **Path**: _/users/{userid}_

- ## Create (`POST`)

  - Input: Path: userid (int)
  - Output
    - 405 Method Not Allowed (Can't recreate user again as identifier exists)

- ## Read (`GET`)

  - Yes
  - Input: Path: userid (int)
  - Output
    - 200 OK (JSON for a single user)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 404 Not Found (Valid user id does not exist)
    - 500 Internal Server Error (Something is wrong on the server side)

- ## Update (`PUT`)

  - Yes
  - Input
    - (in: Body): JSON with user data
    - Path: userid (int)
  - Output
    - 200 OK (JSON for a single user)
    - 400 Bad Request (User id must be an integer)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 404 Not Found (Valid user id does not exist)
    - 500 Internal Server Error (Something is wrong on the server side)

- ## Delete (`DELETE`)
  - Yes
  - Input: Path: userid (int)
  - Output
    - 200 OK (Returns empty)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 404 Not Found (Valid user id does not exist)
    - 500 Internal Server Error (Something is wrong on the server side)

# **Path**: _/users/{userid}/tasks/_

- ## Create (`POST`)

  - Yes
  - Input (in: Body): JSON describing task
  - Input: Path: userid (int)
  - Output
    - 200 OK (Returns records & identifier in the body of response)
    - 400 Bad Request (Missing required information)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 409 Conflict (An error of trying to duplicate records)
    - 500 Internal Server Error (Something is wrong on the server side)

- ## Read (`GET`)

  - Yes
  - Input: Path: userid (int)
  - Output
    - 200 OK (Returns array of the list of the tasks in the JSON format)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 404 Not Found ("tasks" request does not exist)
    - 500 Internal Server Error (Something is wrong on the server side)

- ## Update (`PUT`)

  - Input: Path: userid (int)
  - Output
    - 405 Method Not Allowed (Can’t update a task without knowing their identifier)

- ## Delete (`DELETE`)
  - Input: Path: userid (int)
  - Output
    - 405 Method Not Allowed (Can’t delete a task without knowing their identifier)

# **Path**: _/users/{userid}/tasks/{taskid}_

- ## Create (`POST`)

  - Input: Path: taskid (int)
  - Output
    - 405 Method Not Allowed (Can't recreate task again as identifier exists)

- ## Read (`GET`)

  - Yes
  - Input: Path: taskid (int)
  - Input: Path: userid (int)
  - Output
    - 200 OK (JSON for a single task)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 404 Not Found (Valid task id does not exist)
    - 500 Internal Server Error (Something is wrong on the server side)

- ## Update (`PUT`)

  - Yes
  - Input
    - (in: Body): JSON with task data
    - Path: taskid (int)
    - Path: userid (int)
  - Output
    - 200 OK (JSON for a single task)
    - 400 Bad Request (Task id must be an integer)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 404 Not Found (Valid task id does not exist)
    - 500 Internal Server Error (Something is wrong on the server side)

- ## Delete (`DELETE`)
  - Yes
  - Input: Path: taskid (int)
  - Input: Path: userid (int)
  - Output
    - 200 OK (Returns empty)
    - 401 Unauthorized (User must be authenticated)
    - 403 Forbidden (User does not have access/authorize rights to this operation)
    - 404 Not Found (Valid task id does not exist)
    - 500 Internal Server Error (Something is wrong on the server side)
