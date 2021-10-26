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
- GET
    - parameters: none
    ```

    ```

- PUT
    - parameters: token
    ```
    token: 수정할 푸시알림 토큰
    ```

- DELETE
    - delete the push notification token data of student with kyoId

    - parameters: none

    - returns:
    ```
    {
        "status": "success" | false
    }
    ```

### `/push`
- POST 
    - parameters: kyoId, title, body
    ```
    kyoId: 푸시알림을 전송할 학생 교번 또는 교번 리스트
    title: 푸시알림 title
    body: 푸시알림 body
    ```
