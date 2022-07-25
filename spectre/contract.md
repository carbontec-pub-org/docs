Contracts
=====================================

Get the total number of deployed smart contracts
-------------

Returns the total number of deployed smart contracts.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=contract
   &action=gettotalcontractcount
   &apikey=YourApiKeyToken
```

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": "9"
}
```
