#DAY 5 ASSIGNMENTS
##PART A: USER MANUAL PROCEDURE

Prerequisites
You need a Windows computer, Python, Visual Studio Code, the Python extension for VS Code and internet.

Procedure
1) Create a project folder.
Action: Make folder: python_project.
Expected result: Folder python_project exists.

2) Open the project folder in VS Code.
Action: python_project in Visual Studio Code.
Expected result: Folder appears in the VS Code Explorer.

3) Open the VS Code terminal.
Action: Open an integrated terminal in VS Code.
Expected result: Terminal appears at the bottom of VS Code.

4) Create the environment.
Action: Run:
python -m venv venv
Expected result: Folder venv is created.

5)Activate the environment.
Action: Run:
Venv\scripts\activate
Expected result: (venv) appears in the terminal.

6) Install the requests package.
Action: Run:
pip install requests
Expected result: Package is installed.

7) Verify the installation.
Action: Run:
pip show requests
Expected result: Requests package info appears.

8) Select the environment, in VS Code.
Action: Select the Python interpreter belonging to venv.
Expected result: VS Code shows the venv interpreter.

Troubleshooting

Problem: The terminal says that python is not recognized.
Solution: Install python. Make sure that the option Add python, to PATH is selected during installation. Then restart VS Code. Try again.
 
### Screenshot Description
A screenshot should be included showing Visual Studio Code with the project folder open. The terminal should show the activated Python environment, with "(venv)" at the beginning of the command line and the successful installation of the requests package.

##PART B: API REFERENCE ENTRY

STEP 1: Write the endpoint
Endpoint: POST/api/v1/projects/42/tasks
This means: 
•Post = we are creating something
•/api/v1/ = the API version/path
•Projects = the project section of the application
•{project_id} = the specific project number like 42
•Tasks = the thing we are creating

The Description
This endpoint adds a task to a specific project. Only an authenticated user can make this request. The task must include a title, an assignee, a due date and a priority level. The description is not required. If the task is created successfully the API sends back the task details along, with its unique ID.

Request Parameters
Parameter	Location	Data Type	Required	Description
Project_id	Path	Integer 	Yes	The unique id of the project where the task is developed
Title 	Body	String	Yes	The name of the task
Description 	Body	String	No	Contains more information about the task
Assignee_id	Body	Integer 	Yes	Users id
Due_date	Body	String (Date)	Yes	Date of task completion
Priority 	Body	String	Yes	The priority of the task
      
Request Headers
Header 	Required	Description 
Authorization	Yes	Contains users authentication access token
Content-Type	Yes	Specifies that the request body is JSON format
Headers explanation:
 Authorization: Bearer your access token (“this requests is coming from an authenticated user.”)
Content-Type:  application/json (“the information I am sending is formatted as JSON”)
Example Request Body
             {
                  “title”: “complete project documentation”,
                  “description”: “write and review the technical documentation for the project.”,
                  “assignee_id”:  42,
                  “due_date”:  “2026-10-28”,
                  “priority”: “high”
              }

HTTP Response Codes

Status Code	Name	Description
201	Created	The task was successfully created
400	Bad request	The request contains incorrect data
401	Unauthorized	The authentication token is missing
403	Forbidden	The user is authenticated but does not have permission to create a task in the project
404	Not found	The specified project could not be found
409	Conflict	The request conflict with the currents with the current state of the project 
422	Unprocessable Entity	The submitted data failed validation
500	Internal Server Error	An unexpected error occurred on the server

Successful response
When the task is created successfully the API sends back a 201 Created status code along with the information about the task. The response shows that the task was made. The details of the task are included in the response. The user gets all the information they need. The system confirms that the task is ready. The response is clear and helpful. The user knows the task is done. The system works as expected. The response is correct. The task is now available. The user can see the result. Everything is in order. The process is complete. The response is accurate. The user gets the data. 

Example Response
{
“id”:  7842
“project_id”: 42,
“title”: “complete project documentation”,
“description”: “write and review the technical documentation for the project.”,
“assignee_id”: 105,
“due_date”: “2026-10-28”,
“priority”: “high”,
“status”: “pending”,
“created_at”: “2026-10-01T02:30:00Z”
}

##PART C — TECHNICAL REPORT EXECUTIVE SUMMARY

Executive Summary
This review looked at MySQL, PostgreSQL and MongoDB for an university student records management system. The system must securely manage organized student data, enrollment data and grades while supporting up to 200 staff users and keeping data accurate and safe. The review also considered how practical each option would be for an IT team with limited database expertise.
PostgreSQL is the chosen database for the university. PostgreSQL gives support for organized data and reliable transactions making it well suited to keep accurate student and academic records. PostgreSQL also offers the flexibility needed as the system grows while remaining a choice for a small IT team.
The two important factors driving this recommendation are data integrity and maintainability. Keeping student records is essential while the database must also be manageable by the universitys existing IT staff. PostgreSQL gives the balance of reliability, capability and long-term practicality for this system.

Why we chose PostgreSQL
The assignment does not require us to install or test these databases. We are making a recommendation based on the requirements.

The two key factors are:
1. Data integrity. Student grades and records must remain accurate.
2. Maintainability. The university has an IT team, with limited database expertise.

##PART D — STRUCTURED PEER CRITIQUE
Note: I am studying from home so I have no classmate assigned for me this part D assignment for peer exchange I can’t manage to do it the way it is supposed since I have no classmate.
