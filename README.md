## API Blueprint Notation (ABN) - Enhanced Format

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
