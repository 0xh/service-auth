# service-auth

> An authentication back-end with local authentication using SQLite.

## About

This project uses [Feathers](http://feathersjs.com). An open source web framework for building modern real-time applications.

## Usage

The [HTTPie](https://httpie.org/) is recommended to easily test RESTful APIs.

### Register a new user
```bash
http POST localhost:3030/users email=example@example.com password=secret
```
Response:
```javascript
{
    "id": 1,
    "email": "example@example.com",
    // password is removed by an after-hook!
    "createdAt": "2018-10-16T17:00:27.292Z",
    "updatedAt": "2018-10-16T17:00:27.292Z"
}
```

### Get an access token
```bash
http POST localhost:3030/authentication strategy=local email=example@example.com password=secret 
```
Response
```javascript
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6ImFjY2VzcyJ9.eyJ1c2VySWQiOjEsImlhdCI6MTUzOTcxMTQyMSwiZXhwIjoxNTM5Nzk3ODIxLCJhdWQiOiJodHRwczovL3lvdXJkb21haW4uY29tIiwiaXNzIjoiZmVhdGhlcnMiLCJzdWIiOiJhbm9ueW1vdXMiLCJqdGkiOiIzN2NmN2EwNC1mMzI5LTQxN2QtODA4ZC0zNzBmYTA4YjUyNDYifQ.stSz89kTfHZDNwsRor4QPPTFUuM3JA-kvgScSep5_yc"
}
```

## License

Copyright (c) 2018

Licensed under the [MIT license](LICENSE).
