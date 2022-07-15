Accounts
=====================================

Get balance for a single address
-------------

Returns the balance of a given address.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=account
   &action=balance
   &address=0xde0b295669a9fd93d5f28d9ec85e40f4cb697bae
   &tag=latest
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| address | the string representing the address to check for balance |
| tag  | the string pre-defined block parameter, either `earliest`, `pending` or `latest` |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": "40891626854930000000000" 
}
```

Get balance for multiple addresses in a single call
-------------

Returns the balance of the accounts from a list of addresses.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=account
   &action=balancemulti
   &address=0xddbd2b932c763ba5b1b7ae3b362eac3e8d40121a,0x63a9975ba31b0b9626b34300f7f627147df1f526,0x198ef1ec325a96cc354c7266a038be8b5c558f67
   &tag=latest
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| address | the strings representing the addresses to check for balance, separated by `,` |
| tag  | the string pre-defined block parameter, either `earliest`, `pending` or `latest` |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": [
        {
            "account": "0xddbd2b932c763ba5b1b7ae3b362eac3e8d40121a",
            "balance": "40891626854930000000000"
        },
        {
            "account": "0x63a9975ba31b0b9626b34300f7f627147df1f526",
            "balance": "332567136222827062478"
        },
        {
            "account": "0x198ef1ec325a96cc354c7266a038be8b5c558f67",
            "balance": "0"
        }
    ]
}
```

Get a list of 'normal' transactions by address
-------------

Returns the list of transactions performed by an address.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=account
   &action=txlist
   &address=0xe6f0742f01fbab90d76e87ac291be94ff2103363
   &startblock=0
   &endblock=99999999
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| address | the string representing the address to check for normal transactions |
| startblock | the integer block number to start searching for transactions |
| endblock | the integer block number to stop searching for transactions |

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
            "nonce": "1",
            "timeStamp": "1656010239",
            "to": "0x7d42ced9fc90b2edc5dc19c7b704203bf506eb42",
            "transactionIndex": "0",
            "txreceipt_status": "1",
            "value": "0"
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
            "nonce": "2",
            "timeStamp": "1656010893",
            "to": "0x7d42ced9fc90b2edc5dc19c7b704203bf506eb42",
            "transactionIndex": "0",
            "txreceipt_status": "1",
            "value": "0"
        }
    ]
}
```

Get a list of 'internal' transactions by address
-------------

Returns the list of internal transactions performed by an address.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=account
   &action=txlistinternal
   &address=0xe6f0742f01fbab90d76e87ac291be94ff2103363
   &startblock=0
   &endblock=99999999
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| address | the string representing the address to check for internal transactions |
| startblock | the integer block number to start searching for transactions |
| endblock | the integer block number to stop searching for transactions |

#### Sample response

``` json
{
    "status":"1",
    "message":"OK",
    "result": [
        {
            "blockNumber": "2535368",
            "timeStamp": "1477837690",
            "hash": "0x8a1a9989bda84f80143181a68bc137ecefa64d0d4ebde45dd94fc0cf49e70cb6",
            "from": "0x20d42f2e99a421147acf198d775395cac2e8b03d",
            "to": "",
            "value": "0",
            "contractAddress": "0x2c1ba59d6f58433fb1eaee7d20b26ed83bda51a3",
            "input": "",
            "type": "create",
            "gas": "254791",
            "gasUsed": "46750",
            "traceId": "0",
            "isError": "0",
            "errCode": ""
        },
        {
            "blockNumber": "2535479",
            "timeStamp": "1477839134",
            "hash": "0x1a50f1dc0bc912745f7d09b988669f71d199719e2fb7592c2074ede9578032d0",
            "from": "0x2c1ba59d6f58433fb1eaee7d20b26ed83bda51a3",
            "to": "0x20d42f2e99a421147acf198d775395cac2e8b03d",
            "value": "100000000000000000",
            "contractAddress": "",
            "input": "",
            "type": "call",
            "gas": "235231",
            "gasUsed": "0",
            "traceId": "0",
            "isError": "0",
            "errCode": ""
        }
    ]
}
```

Get a list of 'internal' transactions by transaction hash
-------------

Returns the list of internal transactions performed within a transaction.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=account
   &action=txlistinternal
   &txhash=0x40eb908387324f2b575b4879cd9d7188f69c8fc9d87c901b9e2daaea4b442170
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| txhash | the string representing the transaction hash to check for internal transactions |

#### Sample response

``` json
{
    "status":"1",
    "message":"OK",
    "result": [
        {
            "blockNumber": "1743059",
            "timeStamp": "1466489498",
            "from": "0x2cac6e4b11d6b58f6d3c1c9d5fe8faa89f60e5a2",
            "to": "0x66a1c3eaf0f1ffc28d209c0763ed0ca614f3b002",
            "value": "7106740000000000",
            "contractAddress": "",
            "input": "",
            "type": "call",
            "gas": "2300",
            "gasUsed": "0",
            "isError": "0",
            "errCode": ""
        }
    ]
}
```

Get a list of 'internal' transactions by block range
-------------

Returns the list of internal transactions performed within a block range.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=account
   &action=txlistinternal
   &startblock=0
   &endblock=99999999
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| startblock | the integer block number to start searching for transactions |
| endblock | the integer block number to stop searching for transactions |

#### Sample response

``` json
{
    "status":"1",
    "message":"OK",
    "result": [
        {
            "blockNumber": "50107",
            "timeStamp": "1438984016",
            "hash": "0x3f97c969ddf71f515ce5373b1f8e76e9fd7016611d8ce455881009414301789e",
            "from": "0x109c4f2ccc82c4d77bde15f306707320294aea3f",
            "to": "0x881b0a4e9c55d08e31d8d3c022144d75a454211c",
            "value": "1000000000000000000",
            "contractAddress": "",
            "input": "",
            "type": "call",
            "gas": "2300",
            "gasUsed": "0",
            "traceId": "0",
            "isError": "1",
            "errCode": ""
        },
        {
            "blockNumber": "50111",
            "timeStamp": "1438984075",
            "hash": "0x893c428fed019404f704cf4d9be977ed9ca01050ed93dccdd6c169422155586f",
            "from": "0x109c4f2ccc82c4d77bde15f306707320294aea3f",
            "to": "0x881b0a4e9c55d08e31d8d3c022144d75a454211c",
            "value": "1000000000000000000",
            "contractAddress": "",
            "input": "",
            "type": "call",
            "gas": "2300",
            "gasUsed": "0",
            "traceId": "0",
            "isError": "0",
            "errCode": ""
        }
    ]
}
```

Get nonce for a single address
-------------

Returns the nonce of a given address.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=account
   &action=nonce
   &address=0xde0b295669a9fd93d5f28d9ec85e40f4cb697bae
   &pending=false
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| address | the string representing the address to get a nonce |
| pending | optional, the string either `true` or `false`, default value is `true` |

#### Sample response

``` json
{
   "status": "1",
   "message": "OK",
   "result": "56" 
}
```
