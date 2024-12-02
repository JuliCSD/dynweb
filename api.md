## Lulea Newspaper API

------------------------------------------------------------------------------------------
# Documentation

## Overview

This API provides endpoints for managing articles, tags, users, user groups, user group members, and settings. It uses Express for routing and Prisma for database interactions.

## Endpoints

### Article Tags

#### Get All Article Tags

- **URL**: `/article_tag`
- **Method**: `GET`
- **Description**: Retrieves all article tags.
- **Response**:
  - `200 OK`: Returns a list of article tags.
  - `400 Bad Request`: Invalid request.

#### Get Specific Article Tag

- **URL**: `/article_tag/:articleId/:tagId`
- **Method**: `GET`
- **Description**: Retrieves a specific article tag by article ID and tag ID.
- **Response**:
  - `200 OK`: Returns the article tag.
  - `400 Bad Request`: Invalid request.

#### Create Article Tag

- **URL**: `/article_tag`
- **Method**: `POST`
- **Authorization**: Requires `author` role.
- **Description**: Creates a new article tag.
- **Request Body**:
  - `article_id`: Integer
  - `tag_id`: Integer
- **Response**:
  - `200 OK`: Returns the created article tag.
  - `400 Bad Request`: Invalid request.

#### Delete Article Tag

- **URL**: `/article_tag/:articleId/:tagId`
- **Method**: `DELETE`
- **Authorization**: Requires `author` role.
- **Description**: Deletes an article tag.
- **Response**:
  - `200 OK`: Returns the deleted article tag.
  - `400 Bad Request`: Invalid request.

### Articles

#### Get All Articles

- **URL**: `/article`
- **Method**: `GET`
- **Description**: Retrieves all articles.
- **Response**:
  - `200 OK`: Returns a list of articles.
  - `400 Bad Request`: Invalid request.

#### Get Specific Article

- **URL**: `/article/:id`
- **Method**: `GET`
- **Description**: Retrieves a specific article by ID.
- **Response**:
  - `200 OK`: Returns the article.
  - `400 Bad Request`: Invalid request.

#### Create Article

- **URL**: `/article`
- **Method**: `POST`
- **Authorization**: Requires `author` role.
- **Description**: Creates a new article.
- **Request Body**:
  - `title`: String
  - `content`: String
  - `image_url`: String
  - `user_id`: Integer
- **Response**:
  - `200 OK`: Returns the created article.
  - `400 Bad Request`: Invalid request.

#### Update Article

- **URL**: `/article/:id`
- **Method**: `PUT`
- **Authorization**: Requires `author` role.
- **Description**: Updates an existing article.
- **Request Body**:
  - `title`: String
  - `content`: String
  - `image_url`: String
  - `user_id`: Integer
- **Response**:
  - `200 OK`: Returns the updated article.
  - `400 Bad Request`: Invalid request.

#### Delete Article

- **URL**: `/article/:id`
- **Method**: `DELETE`
- **Authorization**: Requires `author` role.
- **Description**: Deletes an article.
- **Response**:
  - `200 OK`: Returns the deleted article.
  - `400 Bad Request`: Invalid request.

### Settings

#### Get All Settings

- **URL**: `/setting`
- **Method**: `GET`
- **Authorization**: Requires `admin` role.
- **Description**: Retrieves all settings.
- **Response**:
  - `200 OK`: Returns a list of settings.
  - `400 Bad Request`: Invalid request.

#### Get Specific Setting

- **URL**: `/setting/:userid`
- **Method**: `GET`
- **Authorization**: Requires `admin` role.
- **Description**: Retrieves a specific setting by user ID.
- **Response**:
  - `200 OK`: Returns the setting.
  - `400 Bad Request`: Invalid request.

#### Create Setting

- **URL**: `/setting`
- **Method**: `POST`
- **Authorization**: Requires `admin` role.
- **Description**: Creates a new setting.
- **Request Body**:
  - `load_images`: Boolean
  - `user_id`: Integer
- **Response**:
  - `200 OK`: Returns the created setting.
  - `400 Bad Request`: Invalid request.

#### Update Setting

- **URL**: `/setting/:userid`
- **Method**: `PUT`
- **Authorization**: Requires `admin` role.
- **Description**: Updates an existing setting.
- **Request Body**:
  - `load_images`: Boolean
- **Response**:
  - `200 OK`: Returns the updated setting.
  - `400 Bad Request`: Invalid request.

#### Delete Setting

- **URL**: `/setting/:userid`
- **Method**: `DELETE`
- **Authorization**: Requires `admin` role.
- **Description**: Deletes a setting.
- **Response**:
  - `200 OK`: Returns the deleted setting.
  - `400 Bad Request`: Invalid request.

### Tags

#### Get All Tags

- **URL**: `/tag`
- **Method**: `GET`
- **Description**: Retrieves all tags.
- **Response**:
  - `200 OK`: Returns a list of tags.
  - `400 Bad Request`: Invalid request.

#### Get Specific Tag

- **URL**: `/tag/:id`
- **Method**: `GET`
- **Description**: Retrieves a specific tag by ID.
- **Response**:
  - `200 OK`: Returns the tag.
  - `400 Bad Request`: Invalid request.

#### Create Tag

- **URL**: `/tag`
- **Method**: `POST`
- **Authorization**: Requires `author` role.
- **Description**: Creates a new tag.
- **Request Body**:
  - `name`: String
  - `color`: String
- **Response**:
  - `200 OK`: Returns the created tag.
  - `400 Bad Request`: Invalid request.

#### Update Tag

- **URL**: `/tag/:id`
- **Method**: `PUT`
- **Authorization**: Requires `author` role.
- **Description**: Updates an existing tag.
- **Request Body**:
  - `name`: String
  - `color`: String
- **Response**:
  - `200 OK`: Returns the updated tag.
  - `400 Bad Request`: Invalid request.

#### Delete Tag

- **URL**: `/tag/:id`
- **Method**: `DELETE`
- **Authorization**: Requires `author` role.
- **Description**: Deletes a tag.
- **Response**:
  - `200 OK`: Returns the deleted tag.
  - `400 Bad Request`: Invalid request.


### User Group Members

#### Get All User Group Members

- **URL**: `/user_group_member`
- **Method**: `GET`
- **Authorization**: Requires `admin` role.
- **Description**: Retrieves all user group members.
- **Response**:
  - `200 OK`: Returns a list of user group members.
  - `400 Bad Request`: Invalid request.

#### Get Specific User Group Member

- **URL**: `/user_group_member/:groupId/:userId`
- **Method**: `GET`
- **Authorization**: Requires `admin` role.
- **Description**: Retrieves a specific user group member by group ID and user ID.
- **Response**:
  - `200 OK`: Returns the user group member.
  - `400 Bad Request`: Invalid request.

#### Create User Group Member

- **URL**: `/user_group_member`
- **Method**: `POST`
- **Authorization**: Requires `admin` role.
- **Description**: Creates a new user group member.
- **Request Body**:
  - `group_id`: Integer
  - `user_id`: Integer
- **Response**:
  - `200 OK`: Returns the created user group member.
  - `400 Bad Request`: Invalid request.

#### Delete User Group Member

- **URL**: `/user_group_member/:groupId/:userId`
- **Method**: `DELETE`
- **Authorization**: Requires `admin` role.
- **Description**: Deletes a user group member.
- **Response**:
  - `200 OK`: Returns the deleted user group member.
  - `400 Bad Request`: Invalid request.

### User Groups

#### Get All User Groups

- **URL**: `/user_group`
- **Method**: `GET`
- **Authorization**: Requires `admin` role.
- **Description**: Retrieves all user groups.
- **Response**:
  - `200 OK`: Returns a list of user groups.
  - `400 Bad Request`: Invalid request.

#### Get Specific User Group

- **URL**: `/user_group/:id`
- **Method**: `GET`
- **Authorization**: Requires `admin` role.
- **Description**: Retrieves a specific user group by ID.
- **Response**:
  - `200 OK`: Returns the user group.
  - `400 Bad Request`: Invalid request.

#### Create User Group

- **URL**: `/user_group`
- **Method**: `POST`
- **Authorization**: Requires `admin` role.
- **Description**: Creates a new user group.
- **Request Body**:
  - `name`: String
- **Response**:
  - `200 OK`: Returns the created user group.
  - `400 Bad Request`: Invalid request.

#### Update User Group

- **URL**: `/user_group/:id`
- **Method**: `PUT`
- **Authorization**: Requires `admin` role.
- **Description**: Updates an existing user group.
- **Request Body**:
  - `name`: String
- **Response**:
  - `200 OK`: Returns the updated user group.
  - `400 Bad Request`: Invalid request.

#### Delete User Group

- **URL**: `/user_group/:id`
- **Method**: `DELETE`
- **Authorization**: Requires `admin` role.
- **Description**: Deletes a user group.
- **Response**:
  - `200 OK`: Returns the deleted user group.
  - `400 Bad Request`: Invalid request.

### Users

#### Get All Users

- **URL**: `/users`
- **Method**: `GET`
- **Authorization**: Requires `admin` role.
- **Description**: Retrieves all users.
- **Response**:
  - `200 OK`: Returns a list of users.
  - `400 Bad Request`: Invalid request.

#### Get Specific User

- **URL**: `/users/:id`
- **Method**: `GET`
- **Authorization**: Requires `admin` role.
- **Description**: Retrieves a specific user by ID.
- **Response**:
  - `200 OK`: Returns the user.
  - `400 Bad Request`: Invalid request.

#### Create User

- **URL**: `/users`
- **Method**: `POST`
- **Authorization**: Requires `admin` role.
- **Description**: Creates a new user.
- **Request Body**:
  - `name`: String
  - `email`: String
  - `password`: String
  - `totp_secret`: String
- **Response**:
  - `200 OK`: Returns the created user.
  - `400 Bad Request`: Invalid request.

#### Update User

- **URL**: `/users/:id`
- **Method**: `PUT`
- **Authorization**: Requires `admin` role.
- **Description**: Updates an existing user.
- **Request Body**:
  - `name`: String
  - `email`: String
  - `password`: String
  - `totp_secret`: String
- **Response**:
  - `200 OK`: Returns the updated user.
  - `400 Bad Request`: Invalid request.

#### Delete User

- **URL**: `/users/:id`
- **Method**: `DELETE`
- **Authorization**: Requires `admin` role.
- **Description**: Deletes a user.
- **Response**:
  - `200 OK`: Returns the deleted user.
  - `400 Bad Request`: Invalid request.

## Authorization

Certain endpoints require specific roles for access. The `groupAuthorization` middleware is used to enforce these role-based access controls.

- **`author`**: Required for creating, updating, and deleting articles and tags.
- **`admin`**: Required for managing users, user groups, user group members, and settings.

## Error Handling

All endpoints return a `400 Bad Request` status code with a message if the request is invalid or if an error occurs during the database operation.

------------------------------------------------------------------------------------------
