# API documentation - Matera

> For detailed information, refer to the [API Specification on Redoc](https://sharp-bat-92.redoc.ly/).*

*Available until May 25th. After that, it will only be visible with a Redoc user login, which is free.

## Overview

This is an account API, which allows users to create an **alias** in their registration.

In the US financial market, bank account numbers are considered sensitive information and cannot be shared publicly for security reasons. Instead, users can create an alias that represents their bank information. There are three options available for the user to choose from:
- email
- phone number
- randomly generated number

## Endpoints
`/alias` - single endpoint that allows you to perform three different actions: create, retrieve and delete an alias.


### Parameters

- `post` method is used to create an account alias. Contains the following parameter:

|PARAMETER|DESCRIPTION|REQUIRED|
|---|---|---|
|`type`|Property specifies the type of alias to create and must be one of the following three values: "email", "phone", or "random"|Yes|
|`valor`|Property specifies the value to use for the alias and must be a string| Yes|

- `get` method is used to retrieve an existing account alias. Contains the following parameter:

|PARAMETER|DESCRIPTION|REQUIRED|
|---|---|---|
|`type`| Which specifies the type of alias to retrieve. If this parameter is not provided, the API will return all aliases |Yes|
 > The response body will be in JSON format and will include two properties: "type" and "value".

- `delete` method is used to delete an existing account alias. Contains the following parameter:

|PARAMETER|DESCRIPTION|REQUIRED|
|---|---|---|
|`valor`| Which specifies the value of the alias to delete. If this parameter is not provided, the API will delete all aliases |Yes|

## Responses

Responses include a status number that shows what the outcome of that request was.

201 - alias was successfully created.

400 - the request body was invalid.

401 - the request was unauthorized.

404 - the alias was not found.

500 - there was an internal server error.

> DELETE operation does not have a response body. The API will return a status code of 204 if the deletion is successful.


















