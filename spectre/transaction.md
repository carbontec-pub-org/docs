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

| **Parameter** | **Description** |
| --------- | ----------- |
| txhash* | Hash of transaction content  |

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
        "type": "0",
        "value": "5123630808419852"
    }
}
```

Get info for multiple transactions in a single call
-------------

Returns transaction info from a list of transaction hashes (maximum of 20 transactions per call).

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=transaction
   &action=gettxinfomulti
   &txhash=0x2b0b11638d26d5efc9da15facc0b83702c98a2b84d07fd0aa6ea4e4d0d07a621,0x7b9ae4248a9bcfa076ad6e770de1a73d21097c622c132123c4b278ef8d556621
   &apikey=YourApiKeyToken
```

#### Request query parameters

| **Parameter** | **Description** |
| --------- | ----------- |
| txhash* | Strings define the hash to check for the balance, each separated by a comma (,) |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": [
        {
            "blockHash": "0x0ea829c8d3d46a2a2fc8e7b0df41fbc57fb791c3ac44b68bcd8b7bc23699cc8e",
            "blockNumber": "169830",
            "confirmations": "137195",
            "contractAddress": "0xe4ddc629f1730a0a40fec64a351f891cad8d8d21",
            "cumulativeGasUsed": "623178",
            "from": "0xac7d7cec199c935e5bff9b2c5b59aa0b160de76a",
            "gas": "623178",
            "gasPrice": "18000000000",
            "gasUsed": "623178",
            "hash": "0x2b0b11638d26d5efc9da15facc0b83702c98a2b84d07fd0aa6ea4e4d0d07a621",
            "input": "0x",
            "isError": "0",
            "logs": [
                {
                    "address": "0xe4ddc629f1730a0a40fec64a351f891cad8d8d21",
                    "blockHash": "0x0ea829c8d3d46a2a2fc8e7b0df41fbc57fb791c3ac44b68bcd8b7bc23699cc8e",
                    "blockNumber": "0x29766",
                    "data": "0x",
                    "logIndex": "0x0",
                    "removed": false,
                    "topics": [
                        "0x8be0079c531659141344cd1fd0a4f28419497f9722a3daafe3b4186f6b6457e0",
                        "0x0000000000000000000000000000000000000000000000000000000000000000",
                        "0x000000000000000000000000ac7d7cec199c935e5bff9b2c5b59aa0b160de76a"
                    ],
                    "transactionHash": "0x2b0b11638d26d5efc9da15facc0b83702c98a2b84d07fd0aa6ea4e4d0d07a621",
                    "transactionIndex": "0x0"
                }
            ],
            "nonce": "6",
            "receiptStatus": "1",
            "revertReason": null,
            "timeStamp": "1658327568",
            "to": null,
            "transactionIndex": "0",
            "type": "0",
            "value": "1000000"
        },
        {
            "blockHash": "0x652494c73913e344baca80799a3818c381e10f8079156ca211e92e40941eca3f",
            "blockNumber": "306985",
            "confirmations": "40",
            "contractAddress": null,
            "cumulativeGasUsed": "21000",
            "from": "0xdb8a3baa6d69a5fb89930b2650c2ef272198cc1d",
            "gas": "26000",
            "gasPrice": "18000000000",
            "gasUsed": "21000",
            "hash": "0x7b9ae4248a9bcfa076ad6e770de1a73d21097c622c132123c4b278ef8d556621",
            "input": "0x",
            "isError": "0",
            "logs": [],
            "nonce": "6004",
            "receiptStatus": "1",
            "revertReason": null,
            "timeStamp": "1658739717",
            "to": "0x0f2c50455dfc2970b46da2856ab1ccf8233cb0a0",
            "transactionIndex": "0",
            "type": "0",
            "value": "3816661250226488"
        }
    ]
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

| **Parameter** | **Description** |
| --------- | ----------- |
| txhash* | Hash of transaction content |

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

| **Parameter** | **Description** |
| --------- | ----------- |
| txhash* | Hash of transaction content |

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

Get the total number of confirmed transactions
-------------

Returns the total number of confirmed transactions.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=transaction
   &action=gettotaltxcount
   &apikey=YourApiKeyToken
```

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": "308227"
}
```

Get pending transactions
-------------

Returns a list of pending transactions.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=account
   &action=pendingtxlist
   &offset=10
   &limit=10
   &sort=asc
   &apikey=YourApiKeyToken
```

#### Request query parameters

| **Parameter** | **Description** |
| --------- | ----------- |
| offset | Skips the `offset` records when responding |
| limit | Number of records displayed per page |
| sort | Sorting preference, use `asc` to sort by ascending and `desc` to sort by descending |

#### Sample response

``` json
{
   "status": "1",
   "message": "OK",
   "result": "56" 
}
```

Get a list of 'normal' transactions
-------------

Returns the list of 'normal' transactions.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=transaction
   &action=txlist
   &offset=10
   &limit=10
   &sort=asc
   &apikey=YourApiKeyToken
```

#### Request query parameters

| **Parameter** | **Description** |
| --------- | ----------- |
| offset | Skips the `offset` records when responding |
| limit | Number of records displayed per page |
| sort | Sorting preference, use `asc` to sort by ascending and `desc` to sort by descending |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": [
        {
            "blockHash": "0x7c61ad3d0eea32c8fade634a611c0cd29079524c003c71f2e7bab04bf81759ce",
            "blockNumber": "2",
            "confirmations": "404762",
            "contractAddress": null,
            "cumulativeGasUsed": "21336",
            "from": "0xe6f0742f01fbab90d76e87ac291be94ff2103363",
            "gas": "26000",
            "gasPrice": "18000000000",
            "gasUsed": "21336",
            "hash": "0x0e63f1264a1e43eeb582de345694797487bae1b82a5cfaee57ce3966e159d5b2",
            "input": "0x7c3faaef29ba1203364ff8b41f1b0141a6ea2b3ecf",
            "isError": "0",
            "logs": [],
            "nonce": "1",
            "revertReason": null,
            "timeStamp": "1656010239",
            "to": "0x7d42ced9fc90b2edc5dc19c7b704203bf506eb42",
            "transactionIndex": "0",
            "receiptStatus": "1",
            "value": "0",
            "type": "0"
        },
        {
            "blockHash": "0xf6381f56d6caca17c4c4e336bd6e4171f284aa906a78b02580bea578fc4919d1",
            "blockNumber": "3",
            "confirmations": "404761",
            "contractAddress": null,
            "cumulativeGasUsed": "21000",
            "from": "0xe6f0742f01fbab90d76e87ac291be94ff2103363",
            "gas": "26000",
            "gasPrice": "18000000000",
            "gasUsed": "21000",
            "hash": "0x0359e85ce8d1de5179a65a979b87a66b76c8c1d28bdfac70b405dbbafdb7f427",
            "input": "0x",
            "isError": "0",
            "logs": [],
            "nonce": "2",
            "revertReason": null,
            "timeStamp": "1656010893",
            "to": "0x7d42ced9fc90b2edc5dc19c7b704203bf506eb42",
            "transactionIndex": "0",
            "receiptStatus": "1",
            "value": "0",
            "type": "0"
        }
    ]
}
```
