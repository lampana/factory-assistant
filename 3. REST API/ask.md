# Ask API Reference

## Description

Takes text as input (for example, "show me the number of employees"), and responds with the results of running the generated SQL, the generated SQL, and a summary of the results.

```text
GET /api/ask?text=STRING&code=STRING
```

## Request parameters

| Name | Required | Type | Default | Description |
| --- | --- | --- | --- | --- |
| text | true | string | None | the text to send to the assistant. |
| code | true | string | None | the authorization code. |
| include_data | false | true, false | true | include the results of running the generated SQL in the response. |
| include_sql | false | true, false | true | include the generated SQL in the response. |
| include_summary | false | true, false | false | include a summary of the results in the response. |
| format | false | json, html | json | the global response format. |
| data_format | false | json, html, markdown | the value of 'format' | the data response format (overrides 'format'). |
| pretty | false | true, false | false | whether to newline and indent the response JSON. |

## Example Request

```text
GET https://APPNAME.azurewebsites.net/api/ask?include_summary=true&text=How many employees are there?&code=CODE
```

## Example Response

```json
{
    "data": [
        {
            "EmployeeCount": 8
        }
    ],
    "sql": "SELECT COUNT(*) AS EmployeeCount FROM Employee;",
    "summary": "The data indicates that there are a total of 8 employees."
}
```
