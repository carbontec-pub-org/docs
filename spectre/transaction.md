Transactions
=====================================

Get transaction info
-------------

Returns transaction info of a given transaction hash.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=transaction
   &action=gettxinfo
   &txhash=0x6be5e364f9da15389d9754033deddb66aba8efe9dc7290fccc31c1947e0e5a90
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| txhash | hash of contents of the transaction |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": {
        "revertReason": "No credit of that type",
        "blockNumber": "3",
        "confirmations": "0",
        "from": "0x000000000000000000000000000000000000000c",
        "gasLimit": "91966",
        "gasPrice": "100000",
        "gasUsed": "95123",
        "hash": "0x0000000000000000000000000000000000000000000000000000000000000004",
        "input": "0x04",
        "logs": [
            {
                "address": "0x000000000000000000000000000000000000000e",
                "data": "0x00",
                "topics": [
                    "First Topic",
                    "Second Topic",
                    "Third Topic",
                    "Fourth Topic"
                ]
            }
        ],
        "success": true,
        "timeStamp": "1541018182",
        "to": "0x000000000000000000000000000000000000000d",
        "value": "67612"
    }
}
```

Get transaction receipt status
-------------

Returns transaction receipt status of a given transaction hash.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=transaction
   &action=gettxreceiptstatus
   &txhash=0x6be5e364f9da15389d9754033deddb66aba8efe9dc7290fccc31c1947e0e5a90
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| txhash | hash of contents of the transaction |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": {
        "status": "1"
    }
}
```

Get error status and error message
-------------

Returns transaction error status and error message of a given transaction hash.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=transaction
   &action=getstatus
   &txhash=0x6be5e364f9da15389d9754033deddb66aba8efe9dc7290fccc31c1947e0e5a90
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| txhash | hash of contents of the transaction |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": {
        "errDescription": "Out of gas",
        "isError": "1"
    }
}
```
