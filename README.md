# Postman API Testing

Using [Postman](https://github.com/postmanlabs) for REST API testing.

## Software needed for script execution

* Operating System - **Microsoft Windows 10**
* API testing tool - **[Postman](https://www.postman.com/downloads/)**
* IDE - **[Microsoft Visual Studio Code](https://code.visualstudio.com/Download)**
* JavaScript runtime - **[Node.js](https://nodejs.org/en/download/)**

## Programming language used

* [JavaScript (JS)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

## Node package needed for script execution

* [Newman](https://www.npmjs.com/package/newman) - Install globally on your machine using the code
    ```
    npm install -g newman
    ```    
* [Newman Reporter HTML Extra](https://www.npmjs.com/package/newman-reporter-htmlextra) - This is for generating colorful HTML test execution reports. Install globally on your machine using the code below.
    ```
    npm install -g newman-reporter-htmlextra
    ```

## Check installed node packages

```
npm list -g --depth 0
```

## How to execute

* Type the following in your terminal if you are executing the code from the **folder in which the JSON file exists**
    ```
    newman run <postman-collection-json filename> -e <postman-environment-json filename> -r htmlextra
    ```
* Type the following in your terminal if you are executing the code from the **folder in which the JSON file doesn't exist**
    ```
    newman run <full file path with postman-collection-json filename> -e <full file path with postman-environment-json filename> -r htmlextra
    ```
## Postman Collection Public URL
```
https://www.getpostman.com/collections/76a08c2d66be3399fd7e
```

## Container execution
1. Pull the Newman docker image using the command
    ```
    docker pull postman/newman
    ```
    Sample output
    ```
    Using default tag: latest
    latest: Pulling from postman/newman
    c9b1b535fdd9: Pull complete 
    514d128a791d: Pull complete 
    ab9dddf2630f: Pull complete 
    acb767e231ef: Pull complete 
    52ffd3cd08f7: Pull complete 
    Digest: sha256:63fe4b48f62af150b5780890d8b853ccdaddca3316d87c5f1f01fb77ad5e2f6d
    Status: Downloaded newer image for postman/newman:latest
    docker.io/postman/newman:latest
    ```
1. Run Newman commands on the image
    ```
    docker run -t postman/newman run "https://www.getpostman.com/collections/76a08c2d66be3399fd7e"
    ```
    Sample output
    ```
    newman

    ReqRes

    → Registration - Unsuccessful
      ┌
      │ 'Hello World...'
      │ 'Value for url variable is : https://reqres.in'
      └
      POST https://reqres.in/api/register [400 Bad Request, 684B, 157ms]
      ┌
      │ 'Cookie value is: d6cfe14ac3c3276dc0e63dbaa6e75dfeb1595545481'
      └
      ✓  Response status code is 400
      ✓  Response time is less than 200ms
      ✓  Response is not empty
      ✓  Response error is not NULL
      ✓  Content-Type header is present
      ✓  Content-Type is JSON
      ✓  Registration schema is correct
      ✓  Response has property ERROR
      ✓  Response doesn't have property TOKEN
      ✓  Response has string Missing password

    Attempting to set next request to Registration - Successful

    → Registration - Successful
      ┌
      │ 'Hello World...'
      │ 'Value for url variable is : https://reqres.in'
      └
      POST https://reqres.in/api/register [200 OK, 521B, 49ms]
      ┌
      │ 'User ID is: 4'
      │ 'User ID is: 4'
      │ 'Cookie value is: d6cfe14ac3c3276dc0e63dbaa6e75dfeb1595545481'
      └
      ✓  Response status code is 200
      ✓  Response time is less than 200ms
      ✓  Response is not empty
      ✓  Response id is not NULL
      ✓  Content-Type header is present
      ✓  Content-Type is JSON
      ✓  Registration schema is correct
      ✓  User ID is greater than 0
      ✓  Response doesn't have property ERROR
      ✓  Response has property TOKEN
      ✓  Response doesn't have string Missing password

    Attempting to set next request to Single User

    → Single User
      ┌
      │ 'Hello World...'
      │ 'Value for url variable is : https://reqres.in'
      └
      GET https://reqres.in/api/users/4 [200 OK, 940B, 31ms]
      ┌
      │ 'Cookie value is: d6cfe14ac3c3276dc0e63dbaa6e75dfeb1595545481'
      └
      ✓  Response status code is 200
      ✓  Response time is less than 200ms
      ✓  Response is not empty
      ✓  Response data is not NULL
      ✓  Content-Type header is present
      ✓  Content-Type is JSON
      ✓  User schema is correct
      ✓  User ID is greater than 0
      ✓  Response data has property ID

    Attempting to set next request to Login - Unsuccessful

    → Login - Unsuccessful
      ┌
      │ 'Hello World...'
      │ 'Value for url variable is : https://reqres.in'
      └
      POST https://reqres.in/api/login [400 Bad Request, 522B, 62ms]
      ┌
      │ 'Cookie value is: d6cfe14ac3c3276dc0e63dbaa6e75dfeb1595545481'
      └
      ✓  Response status code is 400
      ✓  Response time is less than 200ms
      ✓  Response is not empty
      ✓  Response error is not NULL
      ✓  Content-Type header is present
      ✓  Content-Type is JSON
      ✓  Login schema is correct
      ✓  Response has property ERROR
      ✓  Response doesn't have property TOKEN
      ✓  Response has string Missing password

    Attempting to set next request to Login - Successful

    → Login - Successful
      ┌
      │ 'Hello World...'
      │ 'Value for url variable is : https://reqres.in'
      └
      POST https://reqres.in/api/login [200 OK, 514B, 58ms]
      ┌
      │ 'Cookie value is: d6cfe14ac3c3276dc0e63dbaa6e75dfeb1595545481'
      └
      ✓  Response status code is 200
      ✓  Response time is less than 200ms
      ✓  Response is not empty
      ✓  Response token is not NULL
      ✓  Content-Type header is present
      ✓  Content-Type is JSON
      ✓  Login schema is correct
      ✓  Response doesn't have property ERROR
      ✓  Response has property TOKEN
      ✓  Response doesn't have string Missing password

    Attempting to set next request to List Users

    → List Users
      ┌
      │ 'Hello World...'
      │ 'Value for url variable is : https://reqres.in'
      └
      GET https://reqres.in/api/users?page=all [200 OK, 1.75KB, 26ms]
      ┌
      │ 'Cookie value is: d6cfe14ac3c3276dc0e63dbaa6e75dfeb1595545481'
      └
      ✓  Response status code is 200
      ✓  Response time is less than 200ms
      ✓  Response is not empty
      ✓  Response data is not NULL
      ✓  Content-Type header is present
      ✓  Content-Type is JSON
      ✓  There are 6 results per page
      ✓  User schema is correct

    Attempting to set next request to Update

    → Update
      ┌
      │ 'Hello World...'
      │ 'Value for url variable is : https://reqres.in'
      └
      PUT https://reqres.in/api/users/4 [200 OK, 618B, 49ms]
      ┌
      │ 'Cookie value is: d6cfe14ac3c3276dc0e63dbaa6e75dfeb1595545481'
      └
      ✓  Response status code is 200
      ✓  Response time is less than 200ms
      ✓  Response is not empty
      ✓  Response is not NULL
      ✓  Content-Type header is present
      ✓  Content-Type is JSON
      ✓  Update schema is correct
      ✓  Response has property UPDATED AT
      ✓  Status code is 200
      ✓  Response time is less than 200ms
      ✓  Response time is acceptable
      ✓  Body is not empty

    Attempting to set next request to Delete

    → Delete
      ┌
      │ 'Hello World...'
      │ 'Value for url variable is : https://reqres.in'
      └
      DELETE https://reqres.in/api/users/4 [204 No Content, 444B, 47ms]
      ┌
      │ 'Cookie value is: d6cfe14ac3c3276dc0e63dbaa6e75dfeb1595545481'
      └
      ✓  Content-Type header is not present
      ✓  Content-Type is not JSON
      ✓  Status code is 204
      ✓  Response time is less than 200ms
      ✓  Response time is acceptable

    ┌─────────────────────────┬───────────────────┬───────────────────┐
    │                         │          executed │            failed │
    ├─────────────────────────┼───────────────────┼───────────────────┤
    │              iterations │                 1 │                 0 │
    ├─────────────────────────┼───────────────────┼───────────────────┤
    │                requests │                 8 │                 0 │
    ├─────────────────────────┼───────────────────┼───────────────────┤
    │            test-scripts │                16 │                 0 │
    ├─────────────────────────┼───────────────────┼───────────────────┤
    │      prerequest-scripts │                 8 │                 0 │
    ├─────────────────────────┼───────────────────┼───────────────────┤
    │              assertions │                75 │                 0 │
    ├─────────────────────────┴───────────────────┴───────────────────┤
    │ total run duration: 1183ms                                      │
    ├─────────────────────────────────────────────────────────────────┤
    │ total data received: 1.74KB (approx)                            │
    ├─────────────────────────────────────────────────────────────────┤
    │ average response time: 59ms [min: 26ms, max: 157ms, s.d.: 38ms] │
    └─────────────────────────────────────────────────────────────────┘
    ```

## Remove all docker resources

Clean all docker images/containers/volumes using this [bash script](https://gist.github.com/rafaelaazevedo/bec6cf339888bbac60336d01193ae923) by [Rafaela Azevedo](https://github.com/rafaelaazevedo)

## References
* [Postman documentation](https://learning.postman.com/)
* [JSON Schema](https://jsonschema.net/home)