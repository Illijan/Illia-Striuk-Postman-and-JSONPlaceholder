# QA API Testing Portfolio - JSONPlaceholder

## Project Overview
This repository contains a Postman collection designed to demonstrate my skills in REST API testing. The tests are executed against the public [JSONPlaceholder API](https://jsonplaceholder.typicode.com/), a free fake API for testing and prototyping.

The primary goal of this project is to showcase API testing capabilities, including endpoint validation, HTTP status code verification, and JSON data structure assertions.

## Tools & Technologies Used
* **Postman:** For creating requests, organizing collections, and writing test assertions.
* **REST API:** Understanding of HTTP methods and RESTful architecture.
* **JSON:** Working with request payloads and parsing response data.
* **JavaScript:** Used within Postman's "Tests" tab for writing assertions.

## Testing Scope & Scenarios
This collection covers CRUD operations (Create, Read, Update, Delete) and includes tests for required fields and negative scenarios:

* **GET Requests:** Verifying data retrieval, checking `HTTP 200 OK` status, and asserting JSON response structure (e.g., verifying that specific keys exist and data types are correct).
* **POST Requests:** Simulating resource creation, validating `HTTP 201 Created` status, and checking if the response matches the sent payload.
* **PUT Requests:** Testing resource updates and validating data changes.
* **DELETE Requests:** Verifying successful resource deletion and checking for appropriate status codes (like `HTTP 200 OK` or `204 No Content`).
* **Negative Testing:** Sending requests with invalid data or to incorrect endpoints to verify proper error handling (e.g., `400 Bad Request`, `404 Not Found`).

## How to Run the Tests
To review and execute these tests locally, follow these steps:
1. Download and install [Postman](https://www.postman.com/downloads/).
2. Clone this repository or download the `QA_API_Collection.postman_collection.json` file.
3. Open Postman, click on **Import** (top left corner), and select the downloaded JSON file.
4. Open the imported collection, click on the **Run** button to open the Collection Runner.
5. Execute the tests and review the "Passed" and "Failed" results.

## Example Assertions (Postman Snippets)
Here are some examples of the test scripts included in this collection:

**Checking Status Code:**
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
Verifying JSON Structure & Data Types:

```javascript
pm.test("Response contains 'userId' and it is a number", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property("userId");
    pm.expect(jsonData.userId).to.be.a("number");
});
```
<img width="1540" height="722" alt="postman_results" src="https://github.com/user-attachments/assets/88dd0dbf-4b41-4eb4-9f25-5b72ad5dcb94" />
