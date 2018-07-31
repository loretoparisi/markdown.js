# Examples
This page contains additional examples of how to apply various parts of the specification.

## Basic request:
__GET__ /articles?include=author HTTP/1.1

## cURL example

    curl 'localhost:3000/articles?include=author'

## JavaScript example

    $.ajax({
        type: 'GET',
        url: 'localhost:3000/articles?include=author',
        contentType: "application/json"
    })
    .done(function (data) {
        console.log( JSON.stringify(data) );
    })
    .fail(function (error) {
        console.error(error);
    });

### Response Body
    {
        "data": [{
            "type": "articles",
            "id": "1",
            "attributes": {
            "title": "JSON API paints my bikeshed!",
            "body": "The shortest article. Ever.",
            "created": "2015-05-22T14:56:29.000Z",
            "updated": "2015-05-22T14:56:28.000Z"
            },
            "relationships": {
            "author": {
                "data": {"id": "42", "type": "people"}
            }
            }
        }],
        "included": [
            {
            "type": "people",
            "id": "42",
            "attributes": {
                "name": "John",
                "age": 80,
                "gender": "male"
            }
            }
        ]
    }
## Request with fields parameter:
__GET__ /articles?include=author&fields[articles]=title,body,author&fields[people]=name 

## cURL example

    curl 'localhost:3000/articles?include=author&fields[articles]=title,body,author&fields[people]=name'

## JavaScript example

    $.ajax({
        type: 'GET',
        url: 'localhost:3000/articles?include=author&fields[articles]=title,body,author&fields[people]=name',
        contentType: "application/json"
    })
    .done(function (data) {
        console.log( JSON.stringify(data) );
    })
    .fail(function (error) {
        console.error(error);
    });

### Response Body
    {
    "data": [{
        "type": "articles",
        "id": "1",
        "attributes": {
        "title": "JSON API paints my bikeshed!",
        "body": "The shortest article. Ever."
        },
        "relationships": {
        "author": {
            "data": {"id": "42", "type": "people"}
        }
        }
    }],
    "included": [
        {
        "type": "people",
        "id": "42",
        "attributes": {
            "name": "John"
        }
        }
    ]
    }