# SSHS Forum Backend

[The app](http://localhost:3000) runs on port 3000 on localhost.

## API docs

### `user`
- login
    - parameters:

    ```
    username
    password

    example:
    {
        "username": "1102"
        "password": "[bcrypt form]"
    }
    ```

- register
    - parameters:

    ```
    username
    password
    name: real name
    email(선택)

    example:
    {
        "username": "1102"
        "password": "[bcrypt form]"
        "name": "김선웅"
        "email": "notdatum@gamil.com"
    }
    ```

- edit
    - parameters:
    ```
    current_Password
    username
    email
    New_Password
    Password_Confirmation
    ```

- DELETE
    - parameters: none

### `post`
- post
    - parameters:
    ```
    title
    body
    author
    views
    numId
    attachment
    createdAt
    updatedAt
    ```

- comment
    - parameters:
    ```
    post
    author
    parentComment
    text
    isDeleted
    createdAt
    updatedAt
    ```

- count
    - parameters: 
    ```
    name
    count
    ```

- file
    - parameters:
    ``` 
    originalFileName
    serverFileId
    serverFileName
    size
    uploadedBy
    postId
    isDeleted
    ```