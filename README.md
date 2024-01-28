## API Blueprint Notation (ABN)

API Blueprint Notation (ABN) is a new, structured, and intuitive approach for describing and testing web APIs. ABN is designed to offer clear and concise documentation of API endpoints, their behavior, and expected responses. The notation focuses on readability and ease of understanding, making it accessible for both developers and non-technical stakeholders.

### Request Block:
Detailed Description:

HTTP Verb and URL:

Clearly states the endpoint and the method (GET, POST, etc.).
Example: GET /posts

Fields and Parameters:

Enclosed in {} immediately following the URL and verb.
Include query parameters, request body fields, or path variables.
Example: {userId, postTitle}
HTTP Response Code:

Indicates the expected response status for the given request.
Example: 200 for a successful request.
Headers:

Follows the response code, enclosed in {}.
Details relevant response headers.
Example: {Content-Type: application/json}
Response Body:

Outlines the expected structure of the response data.
Includes key data fields or an error message.
Example: {id, username, token}

First Line: The first line of the block contains the URL, HTTP verb, and any fields or parameters enclosed in braces {}.
Example: POST /users {username, password}
Response Block:

Subsequent Lines: These lines detail the expected HTTP response. Each line includes the HTTP response code, followed by any relevant headers and the body of the response, each enclosed in braces {}. 

Outlines the expected structure of the response data.
Includes key data fields or an error message.
Example: {id, username, token}

````
GET /posts/${postId} [Content-Type: application/json]
200 [Content-Type: application/json] {id, title, content, author}
404 [Content-Type: application/json] {error_message}

POST /users [Content-Type: application/json] {username, email, password, number=/\d/}
201 [Content-Type: application/json] {id, username}
400 [Content-Type: application/json] {error_message}
````

**Request for POST /users:**

    /users [POST] [Content-Type: application/json] {username, email, password}

Describes a POST request to `/users` with JSON content type. The request expects `username`, `email`, and `password` in the body.

**Responses for POST /users:**

    201 {Content-Type: application/json} {id, username}
    400 {Content-Type: application/json} {error_message}

- 201 response with JSON content, including `id` and `username`.
- 400 response for errors, with a JSON formatted error message.

**Request for GET /posts/{postId}:**

    /posts/{postId} [GET]

Specifies a GET request to retrieve a post by `postId`. No specific headers or fields are indicated.

**Responses for GET /posts/{postId}:**

    200 {Content-Type: application/json} {id, title, content, author}
    404 {Content-Type: application/json} {error_message}

- 200 response indicating successful retrieval with post details in JSON.
- 404 response for not found posts, with an error message in JSON format.
