# API documentation - Matera

> For detailed information, refer to the [API Specification on Redoc](https://sharp-bat-92.redoc.ly/).*

*Available until May 25th. After that, it will only be visible with a Redoc user login, which is free.

## Overview

This is an account API, which allows users to create an **alias** in their registration.

In the US financial market, bank account numbers are considered sensitive information and cannot be shared publicly for security reasons. Instead, users can create an alias that represents their bank information. There are three options available for the user to choose from:
- email
- phone number
- randomly generated number

## Parameters

The `put_account_id` method contains the following parameter:

|PARAMETER|DESCRIPTION|TYPE|REQUIRED|
|---|---|---|---|
|`accountId`|The ID of the bank account to update.|integer|yes|

## Endpoints
`/accounts/{account_id}/alias`  - single `put` operation.

It expects a request that specifies the type and value to be used by this alias.
the terminal updates the account alias with the given ID.

## Schemas

`AliasRequest` - defines the expected format of the request body. 
It requires the `alias_type` field to be present, with a value of either **email**,**phone** or **random**. 

> If `alias_type` is email or phone, then the alias_value field must also be present and contain a valid email address or phone number, respectively. If `alias_type` is random, then the `alias_value` field is ignored.

## Responses

The responses to the endpoint are either:

200 - successful update;

400 - invalid request body;

404 - bank account that is not found.


















