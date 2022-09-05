Common Error Messages 
=====================================

An API call that encounters an error will return 0 as its `status code` and display the cause of the error in the `result` field.

``` json
{
    "status": "0",
    "message": "NOTOK",
    "result": "Internal error"
}
```
