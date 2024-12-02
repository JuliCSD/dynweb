## Lulea Newspaper API

------------------------------------------------------------------------------------------
# Documentation

## Overview

This API provides endpoints for managing articles, tags, users, user groups, user group members, and settings. It uses Express for routing and Prisma for database interactions.

## Endpoints

### Article Tags

<details>
 <summary><code>GET</code> <code><b>/article_tag</b></code> <code> (gets all article tags)</code></summary>

##### Parameters

> None

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns list of article tags                                                |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

</details>

<details>
 <summary><code>GET</code> <code><b>/article_tag/:articleId/:tagId</b></code> <code> (gets a specific article tag by article ID and tag ID)</code></summary>

##### Parameters

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `articleId`       |  required | int            | returns specific article id         |
> | `tagId`           |  required | int            | returns specific tagId id           |

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the specific article tag                                    |
> | `400`         | `application/json`                | returns { message: "Invalid request" }                              |

</details>


<details>
 <summary><code>POST</code> <code><b>/article_tag</b></code> <code> (creates a new article tag)</code></summary>

##### Request Body

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `article_id`      |  required | int            | specific article id                 |
> | `tag_id`          |  required | int            | specific tagId id                   |


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the created article tag                                     |
> | `400`         | `application/json`                | returns { message: "Invalid request" }                              |


 **Authorization**: Requires `author` role. 

</details>  

<details>
 <summary><code>DELETE</code> <code><b>/article_tag/:articleId/:tagId</b></code> <code> (deletes an article tag)</code></summary>

##### Parameters

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `article_id`      |  required | int            | specific article id                 |
> | `tag_id`          |  required | int            | specific tagId id                   |


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the deleted article tag                                     |
> | `400`         | `application/json`                | returns { message: "Invalid request" }                              |


 **Authorization**: Requires `author` role. 

</details>    


### Articles

<details>
 <summary><code>GET</code> <code><b>/article</b></code> <code> (gets all articles)</code></summary>

##### Parameters

> None

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns list of articles                                            |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

</details>

 <details>
 <summary><code>GET</code> <code><b>/article/:id</b></code> <code> (gets a specific article by ID)</code></summary>

##### Parameters

> None

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the article                                                 |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

</details> 

<details>
 <summary><code>POST</code> <code><b>/article</b></code> <code> (creates a new article)</code></summary>

##### Body

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `title`           |  required | String         | article title                       |
> | `content`         |  required | String         | article body                        |
> | `image_url`       |  required | String         | article image link                  |
> | `user_id`         |  required | Int            | author's user ID                    |


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the created article                                         |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `author` role. 
</details>      

<details>
 <summary><code>PUT</code> <code><b>/article/:id</b></code> <code> (updates an existing article)</code></summary>

##### Request Body

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `title`           |  required | String         | article title                       |
> | `content`         |  required | String         | article body                        |
> | `image_url`       |  required | String         | article image link                  |
> | `user_id`         |  required | Int            | author's user ID                    |


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the updated article                                         |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `author` role. 
</details>    

<details>
 <summary><code>DELETE</code> <code><b>/article/:id</b></code> <code> (deletes an article using ID)</code></summary>

##### Request Body

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `title`           |  required | String         | article title                       |
> | `content`         |  required | String         | article body                        |
> | `image_url`       |  required | String         | article image link                  |
> | `user_id`         |  required | Int            | author's user ID                    |


##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the deleted article                                         |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `author` role. 
</details>   


### Settings

<details>
 <summary><code>GET</code> <code><b>/setting</b></code> <code> (gets all settings)</code></summary>

##### Parameters

> None

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns a list of settings                                          |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `admin` role. 
</details> 
 
 
<details>
 <summary><code>GET</code> <code><b>/setting/:userid</b></code> <code> (gets a specific setting by user ID)</code></summary>

##### Parameters

> None

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the setting                                                 |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `admin` role. 
</details> 
   

<details>
 <summary><code>POST</code> <code><b>/setting</b></code> <code> (creates a new setting)</code></summary>

##### Request Body

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `load_images`     |  required | Boolean        | setting to display thumbnails       |
> | `user_id`         |  required | Int            | user ID                             |

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the created setting                                                 |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `admin` role. 
</details> 
 
<details>
 <summary><code>PUT</code> <code><b>/setting/:userid</b></code> <code> (updates an existing setting)</code></summary>

##### Request Body

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `load_images`     |  required | Boolean        | setting to display thumbnails       |

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the updated setting                                         |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `admin` role. 
</details>    

<details>
 <summary><code>DELETE</code> <code><b>/setting/:userid</b></code> <code> (deletes a specific setting using user ID)</code></summary>

##### Parameters

> None

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the deleted setting                                                 |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `admin` role. 
</details>    

### Tags

<details>
 <summary><code>GET</code> <code><b>/tag</b></code> <code> (gets all tags)</code></summary>

##### Parameters

> None

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns a list of tags                                              |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `admin` role. 
</details>    

<details>
 <summary><code>GET</code> <code><b>/tag/:id</b></code> <code> (gets a specific tag by ID)</code></summary>

##### Parameters

> None

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the tag                                                     |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `admin` role. 
</details>    

<details>
 <summary><code>POST</code> <code><b>/tag</b></code> <code> (creates a new tag)</code></summary>

##### Request Body

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `name`            |  required | String         | tag name                            |
> | `color`           |  required | String         | tag color                           |

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the created tag                                             |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `author` role. 
</details>     

<details>
 <summary><code>PUT</code> <code><b>/tag/:id</b></code> <code> (updates an existing tag)</code></summary>

##### Request Body

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `name`            |  required | String         | tag name                            |
> | `color`           |  required | String         | tag color                           |

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the updated tag                                             |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `author` role. 
</details>        

<details>
 <summary><code>DELETE</code> <code><b>/tag/:id</b></code> <code> (deletes a tag)</code></summary>

##### Request Body

> | name              |  type     | data type      | description                         |
> |-------------------|-----------|----------------|-------------------------------------|
> | `name`            |  required | String         | tag name                            |
> | `color`           |  required | String         | tag color                           |

##### Responses

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | returns the deleted tag                                             |
> | `400`         | `application/json`                | { message: "Invalid request" }                                      |

 **Authorization**: Requires `author` role. 
</details>      


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
