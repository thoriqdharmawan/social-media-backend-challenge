# Social Media Backend Challenge

## Objective

To build a basic social media application backend using Golang, Fiber, and an ORM (preferably GORM) for database interaction. The application will focus on essential social media functionalities, such as user management, posts, comments, likes, and follows.

## Requirements

1. **Programming Language**: Golang
2. **Web Framework**: Fiber
3. **Database**: PostgreSQL (or MySQL if PostgreSQL is not available)
4. **ORM**: GORM
5. **Authentication**: JWT-based authentication for secure API access
6. **Environment Variables**: Store sensitive data (e.g., database credentials, JWT secret key, cloud API keys) in a .env file. This helps keep sensitive information out of your source code, following best security practices. Use a library like `godotenv` to load these environment variables in your application.
7. **Deployment**: Deploy the application to a cloud service (e.g., Heroku, AWS, GCP, or DigitalOcean)

## Features

### 1. **User Management**

- **Register**: Allow users to create an account with fields: `username`, `email`, `password`, and `bio`.
- **Login**: Allow users to log in and receive a JWT token.
- **Profile**: Enable users to view and update their profile.
- **Follow/Unfollow Users**: Users can follow/unfollow other users.

### 2. **Posts**

- **Create Post**: Users can create a new post with fields: `title`, `content`, and `imageURL` (optional).
- **Edit Post**: Allow users to edit their own posts.
- **Delete Post**: Users can delete their own posts.
- **View Post**: Any user can view posts made by others.

### 3. **Comments**

- **Add Comment**: Users can add comments to posts.
- **Edit Comment**: Users can edit their own comments.
- **Delete Comment**: Users can delete their own comments.

### 4. **Likes**

- **Like/Unlike a Post**: Users can like/unlike a post.
- **Like Count**: Each post should display the total number of likes.

### 5. **Feeds and Timeline**

- **User Feed**: Show a feed of posts from followed users, sorted by the most recent.
- **Explore Feed**: Display a feed of recent posts from all users, sorted by popularity or time.

### 6. **Notifications**

- **New Follower Notification**: Notify a user when another user starts following them.
- **Like Notification**: Notify the post creator when their post is liked.
- **Comment Notification**: Notify the post creator when a new comment is added to their post.
- **Mark as Read**: Allow users to mark notifications as read.
- **Delete Notifications**: Users can delete notifications.

## API Endpoints

Design RESTful endpoints for each feature. Here’s a suggested endpoint list:

- **User**:

  - `POST /api/v1/register` - Register a new user
  - `POST /api/v1/login` - Login and get JWT token
  - `GET /api/v1/users/:id` - Get user profile
  - `PUT /api/v1/users/:id` - Update user profile
  - `POST /api/v1/users/:id/follow` - Follow a user
  - `DELETE /api/v1/users/:id/unfollow` - Unfollow a user

- **Posts**:

  - `POST /api/v1/posts` - Create a new post
  - `GET /api/v1/posts/:id` - Get a post by ID
  - `PUT /api/v1/posts/:id` - Edit a post
  - `DELETE /api/v1/posts/:id` - Delete a post
  - `GET /api/v1/posts` - List all posts (with filters for timeline/explore)

- **Comments**:

  - `POST /api/v1/posts/:id/comments` - Add a comment to a post
  - `PUT /api/v1/comments/:id` - Edit a comment
  - `DELETE /api/v1/comments/:id` - Delete a comment

- **Likes**:

  - `POST /api/v1/posts/:id/like` - Like a post
  - `DELETE /api/v1/posts/:id/like` - Unlike a post

- **Notifications**:
  - `GET /api/v1/notifications` - Retrieve a list of notifications for the authenticated user
  - `PUT /api/v1/notifications/:id/read` - Mark a notification as read
  - `DELETE /api/v1/notifications/:id` - Delete a notification

## Requirements

1. **Authentication**: Secure all endpoints except registration, login, and public post view endpoints with JWT middleware.
2. **Validation**: Add validation for all inputs to ensure data integrity.
3. **Error Handling**: Return meaningful error messages for various error scenarios (e.g., unauthorized access, data not found, validation errors).
4. **Pagination**: Implement pagination for feeds and comments.
5. **Testing**: Write unit tests and integration tests to cover main functionalities.
6. **Notifications**: Send notifications when a user is followed, or a post is liked or commented on.
7. **Search**: Add search functionality for users and posts.
8. **Rate Limiting**: Implement rate limiting to prevent abuse.
9. **Media Upload**: Allow users to upload and manage images for their posts.

## Deployment

Deploy the application to a cloud provider of your choice. Provide the API documentation and endpoint URLs.

## Submission

- Provide a GitHub repository link with the source code.
- Include a README file with instructions on how to set up the project locally.
- Include the deployment URL in the README.
