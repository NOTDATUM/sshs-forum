# SSHS Forum Backend

[The app](http://localhost:3000) runs on port 3000 on localhost.

## API docs

### `/token`
- POST
    - register a push notification token for a student
    - parameters:

    ```
    kyoId: 등록한 학생 교번
    token: 푸시알림 발송용 토큰

    example:
    {
        "kyoId": "20049"
        "token": "ExponentPushToken[YmRoMDLTwvSTovg7NLgzQV]"
    }
    ```

    - returns:
    ```
    {
        "status": "success" | false
    }
    ```

- GET
    - gets the push notification token of all student

    - parameters: none

    - returns:
    ```
    [
        {
            "kyoId": "교번"
            "token": "푸시알림 토큰"
        },
    ]
    ```

- PUT
    - register/edit the push token for a student

    - parameters: kyoId
    ```
    kyoId: 학생 교번
    token: 수정할 푸시알림 토큰

    example:
    {
        "kyoId": "20049"
        "token": "ExponentPushToken[YmRoMDLTwvSTovg7NLgzQV]"
    }
    ```

    - returns:
    ```
    {
        "status": "success" | false 
    }
    ```

- DELETE
    - delete the push notification token data of all student

    - parameters: none

    - returns:
    ```
    {
        "status": "success" | false
    }
    ```

### `/token/:kyoId`
- GET
    - gets the push notification token of student with kyoId

    - parameters: none

    - returns:
    ```
    {
        "kyoId": "교번"
        "token": "푸시알림 토큰"
    }
    ```

- PUT
    - register/edit the push token for a student with kyoId

    - parameters: token
    ```
    token: 수정할 푸시알림 토큰

    example:
    {
        "token": "ExponentPushToken[YmRoMDLTwvSTovg7NLgzQV]"
    }
    ```

    - returns:
    ```
    {
        "status": "success" | false 
    }
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
    - sends a push notification to a student with kyoId

    - parameters: kyoId, title, body
    ```
    kyoId: 푸시알림을 전송할 학생 교번 또는 교번 리스트
    title: 푸시알림 title
    body: 푸시알림 body

    example:
    {
        "kyoId": "20049"
        "title": "피카츄 마법!"
        "body": "피카츄 마법을 받아라ㅏㅏ"
    }
    ```

    - returns:
    ```
    [
        {
            "kyoId": "교번",
            "status": "ok"
        }, // for successful push notifications
        {
            "kyoId": "교번",
            "status": "error",
            "error"?: "InvalidCredentials" | "MessageTooBig" | "MessageRateExceeded" | "DeviceNotRegistered" | "NoTokenInDB";
            "message": "오류 상세 원인"
        }, // for failed push notifications
    ]
    ```
