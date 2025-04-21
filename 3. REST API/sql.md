# SQL API Reference

## Description

Takes SQL as input (for example, "SELECT COUNT(*) AS EmployeeCount FROM Employee;"), and responds with the results of running the SQL and a summary of the results.

```text
GET /api/sql?input=STRING&code=STRING
```

## Request parameters

| Name | Required | Type | Default | Description |
| --- | --- | --- | --- | --- |
| input | true | string | None | the input to send to the assistant. |
| include_data | false | true, false | true | include the results of running the SQL in the response. |
| include_summary | false | true, false | false | include a summary of the results in the response. |
| format | false | json, html | json | the global response format. |
| data_format | false | json, html, markdown | the value of 'format' | the data response format (overrides 'format'). |
| pretty | false | true, false | false | whether to newline and indent response JSON. |

## Example Request

```text
GET https://APPNAME.azurewebsites.net/api/sql?include_summary=true&input=SELECT COUNT(*) AS EmployeeCount FROM Employee;&code=CODE
```

## Example Response

```json
{
    "data": [
        {
            "EmployeeCount": 8
        }
    ],
    "summary": "The data indicates that there are a total of 8 employees."
}
```
