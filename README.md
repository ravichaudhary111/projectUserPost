# Comment API with Express and MongoDB

This project implements a simple RESTful API using Node.js, Express.js, and MongoDB to store comments and their authors. It provides endpoints to manage comments and replies, along with basic CRUD operations.

## Prerequisites

Make sure you have the following installed on your system:

- Node.js
- npm (Node Package Manager)
- MongoDB

## Getting Started

1. **Clone the repository:**

   ```bash
   git clone https://github.com/ravichaudhary111/projectUserPost.git
   cd comment-api
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Set up MongoDB:**

   - Make sure MongoDB is running locally or update `mongoose.connect` in `server.js` with your MongoDB connection URI.

4. **Run the server:**

   ```bash
   node server.js
   ```

   The server will start running at `http://localhost:3000` (or another port if specified).

## API Endpoints

### Comments

- **POST /comments**
  - Create a new comment.
  - Example using `curl`:
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{ "text": "Comment text", "authorId": "user_id" }' http://localhost:3000/comments
    ```

- **POST /comments/:parentId/replies**
  - Reply to a comment or reply.
  - Example using `curl`:
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{ "text": "Reply text", "authorId": "user_id" }' http://localhost:3000/comments/:parentId/replies
    ```

- **GET /comments/by-user/:userId**
  - Get all comments by a specific user.
  - Example using `curl`:
    ```bash
    curl http://localhost:3000/comments/by-user/:userId
    ```

- **GET /comments/:commentId/replies**
  - Get all replies of a comment or reply.
  - Example using `curl`:
    ```bash
    curl http://localhost:3000/comments/:commentId/replies
    ```

- **PATCH /comments/:id**
  - Update a comment or reply.
  - Example using `curl`:
    ```bash
    curl -X PATCH -H "Content-Type: application/json" -d '{ "text": "Updated text" }' http://localhost:3000/comments/:id
    ```

- **DELETE /comments/:id**
  - Delete a comment or reply.
  - Example using `curl`:
    ```bash
    curl -X DELETE http://localhost:3000/comments/:id
    ```

### Users

- **POST /users**
  - Create a new user.
  - Example using `curl`:
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{ "name": "User Name", "email": "user@example.com", "gender": "Male/Female/Other" }' http://localhost:3000/users
    ```

### Error Handling

- The API handles common errors such as invalid requests, missing parameters, and database errors, returning appropriate HTTP status codes and error messages.

## Example Usage

Here's an example of creating a comment using `curl`:

```bash
curl -X POST -H "Content-Type: application/json" -d '{ "text": "Hello World!", "authorId": "user_id" }' http://localhost:3000/comments
```

## Contributing

Feel free to fork the repository and contribute to it. Pull requests are welcome.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

### Notes:
- Replace `<repository_url>` in step 1 with the actual URL of your Git repository.
- Update the `server.js` file with appropriate error handling and validation based on your project's requirements.
- The `curl` examples provided assume you have `curl` installed and configured on your system. Adjust the examples according to your specific environment or use a tool like Postman for testing if `curl` is not available.
- This README.md file is structured to help users understand how to set up, use, and interact with your API using command-line tools like `curl`. Adjust it further based on your specific project requirements and conventions.
