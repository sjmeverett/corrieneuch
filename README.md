# Corrieneuch

A protocol not unlike [JSON API](https://jsonapi.org).

It is intended to be more opinionated than the latter, so as to leave less up to the implementer.

## Usage

Install:

```
$ npm install --save corrieneuch
```

## The underlying protocol

### Overview

To give you a broad overview, here is an example of a possible response from a blog system.

```json
{
  "links": {
    "$next": "https://blog/api/posts?page[number]=2"
  },
  "elements": [
    {
      "links": {
        "$self": "https://blog/api/posts/1",
        "author": "https://blog/api/users/1",
        "comments": "https://blog/api/posts/1/comments"
      },
      "attributes": {
        "title": "Hello, world!",
        "content": "This is a test post."
      }
    },
    {
      "links": {
        "$self": "https://blog/api/posts/2",
        "author": "https://blog/api/users/1",
        "comments": "https://blog/api/posts/2/comments"
      },
      "attributes": {
        "title": "Test post 2",
        "content": "This is second test post."
      }
    }
  ],
  "meta": {
    "count": 8
  },
  "includes": [
    {
      "links": {
        "$self": "https://blog/api/users/1"
      },
      "attributes": {
        "name": "Fred Flintstone",
        "email": "fred@example.com"
      }
    },
    {
      "links": {
        "$self": "https://blog/api/posts/1/comments"
      },
      "elements": [
        {
          "links": {
            "$self": "https://blog/api/comments/1"
          },
          "attributes": {
            "content": "This is a comment!"
          }
        }
      ]
    },
    {
      "links": {
        "$self": "https://blog/api/posts/2/comments"
      },
      "elements": []
    }
  ]
}
```

This example demonstrates embedding multiple resources (including collections of resources) into the response body.  

## Todo...

This library is currently beta-quality, the most notable defects being abject lack of documentation.  It'll come shortly.
