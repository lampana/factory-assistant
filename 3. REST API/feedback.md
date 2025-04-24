# Feedback API Reference

## Description

Associates the given feedback with the given message id.

```text
POST /api/feedback?code=STRING
```

## Request parameters

| Name | Required | Type | Default | Description |
| --- | --- | --- | --- | --- |
| code | true | string | None | the authorization code. |

## Request body

{
    "text": STRING,
    "message_id": UUID
}

## Example Request

```text
POST https://APPNAME.azurewebsites.net/api/feedback?code=CODE
{
    "text": "good",
    "message_id": "UUID"
}
```
