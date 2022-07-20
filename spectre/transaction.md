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
        "blockHash": "0x8a6eaa648a9ee51dbbd804e617010d024dedb1e5aa1fdef1cb1c15ca0f8cabea",
        "blockNumber": "134805",
        "confirmations": "28998",
        "contractAddress": null,
        "cumulativeGasUsed": "21000",
        "from": "0x9b061003fcc032555268e598e126e1cbaa223748",
        "gas": "26000",
        "gasPrice": "18000000000",
        "gasUsed": "21000",
        "hash": "0x6be5e364f9da15389d9754033deddb66aba8efe9dc7290fccc31c1947e0e5a90",
        "input": "0x",
        "isError": "0",
        "logs": [],
        "nonce": "2589",
        "revertReason": null,
        "timeStamp": "1658221947",
        "to": "0x9dd5f099598b00d1b3ae3cc30fe0c5416da3683f",
        "transactionIndex": "0",
        "receiptStatus": "1",
        "value": "5123630808419852"
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
