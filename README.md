### API Blueprint Notation (ABN)

#### Summary:

API Blueprint Notation (ABN) is a structured, easy-to-read format designed for defining and testing web APIs. Each API request is described in a block of lines, with the first line detailing the request and subsequent lines indicating possible responses.

#### Format:

1. **Request Line Format:**
   - **URL:** The endpoint of the API.
   - **HTTP Verb:** Enclosed in square brackets `[GET]`, `[POST]`, `[PUT]`, `[DELETE]`, etc.
   - **HTTP Headers:** Optional, enclosed in square brackets `[Content-Type: application/json]`.
   - **Fields:** Request body or parameters, enclosed in braces `{username, password}`.

2. **Response Lines Format:**
- **HTTP Response Status Code:** Such as `200`, `404`, `500`.
- **Headers:** Optional, enclosed in braces `{Content-Type: application/json}`.
- **Response Object Fields:** Enclosed in quotes, with optional regex for value formats `"id": "\d+", "name": ".+"`.


#### Complete Example:
````
## Get a user
/user/${id} [GET]
200 [] {id=/\d+/, name=/.+/}
404 [] {"error": "User not found"}
500 [] {"error": "Internal Server Error"}

## Add a new user
/user [POST] [Authorization: Bearer ${token}] {username, email, password}
200 [Content-Type=/application\/json/] {id=/\d+/, name, email=/.+/}
400 [] {"error": "Invalid request data"}
404 [] {"error": "User not found"}
500 [] {"error": "Internal Server Error"}
````

#### Use Case:

- **API Developers:** To define and share API specifications.
- **Testers:** For creating test cases and automating API testing.
- **Documentation:** As a part of API documentation for clear understanding of API behavior.

#### Benefits:

- **Clarity:** Clear and concise format for understanding API requests and responses.
- **Versatility:** Supports various HTTP methods, headers, and response formats.
- **Validation:** Regex support allows for precise field value validation.
- **Ease of Use:** Simple to learn and apply, enhancing communication between developers and stakeholders.

