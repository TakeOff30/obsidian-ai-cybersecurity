
An [[HTTP]] request is composed of several key parts:

*   **Request Line:** Contains the HTTP method, the requested URI (Uniform Resource Identifier), and the HTTP version.
    *   **Method:** The action to be performed on the resource.
        *   Examples: `GET`, `POST`, `PUT`, `DELETE`, `PATCH`, `OPTIONS`, `HEAD`
        *   `GET`: Retrieves a resource.
        *   `POST`: Submits data to be processed.
        *   `PUT`: Updates a resource.
        *   `DELETE`: Deletes a resource.
    *   **URI (Uniform Resource Identifier):** Identifies the resource being requested.
        *   Can be an absolute URL or a relative path.
        *   Example: `/index.html`, `/products/123`
    *   **HTTP Version:** The version of the HTTP protocol being used.
        *   Example: `HTTP/1.1`, `HTTP/2`

*   **Headers:** Provide additional information about the request, the client, and the desired format of the response.
    *   Consist of key-value pairs, separated by a colon.
    *   Examples:
        *   `Host`: Specifies the domain name of the server. (Required in HTTP/1.1)
        *   `User-Agent`: Identifies the client making the request.
        *   `Accept`: Lists the content types the client can handle. (e.g., `text/html, application/json`)
        *   `Accept-Language`: Specifies the preferred languages for the response. (e.g., `en-US,fr-CA`)
        *   `Content-Type`: Indicates the media type of the request body (if present). (e.g., `application/json`, `application/x-www-form-urlencoded`)
        *   `Content-Length`: The size of the request body in bytes (if present).
        *   `Authorization`: Contains credentials for authentication. (e.g., `Basic dXNlcm5hbWU6cGFzc3dvcmQ=`)
        *   `Cookie`: Contains cookies associated with the domain.

*   **Message Body (Optional):** Contains data being sent to the server (e.g., form data, JSON payload).
    *   Used with methods like `POST`, `PUT`, and `PATCH`.
    *   The format of the message body is specified by the `Content-Type` header.
