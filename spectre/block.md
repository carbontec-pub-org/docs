Blocks
=====================================

Get the most recent block number
-------------

Returns number of the most recent block.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=block
   &action=getlatestblockno
   &apikey=YourApiKeyToken
```

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": "0x26a8c"
}
```

Get block header by block number
-------------

Returns block header (including hashes of the transactions) by block number.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=block
   &action=getblockbyno
   &blockno=32
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| blockno | a nonnegative integer that represents the block number |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": {
        "difficulty": "0x01",
        "extraData": "0xd883010101846765746888676f312e31382e32856c696e7578000000000000000000000000000000000884ee2bdad3b44ec393540ccb65ac85f90b4b675b1cf6977509ab93fb4f42a40d760c3d2646fdd42079e5317d856349c22135c11c8e9a428def17b2f5ca5d33a001",
        "gasLimit": "0x25ff7a7",
        "gasUsed": "0xae7a",
        "hash": "0xf1f033be1630208234c62a34e29c70d94dac4e5470aa13659e8033ea61cad04d",
        "logsBloom": "0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
        "miner": "0x357148d40c2a0be7ddac76fe062d867a519bfc80",
        "mixHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
        "nonce": "0x",
        "number": "0x1",
        "parentHash": "0x8236eff1cf16b322c5345f0cbbf9810bcf8cbf755cb38ffa514a2644f9647a35",
        "receiptsRoot": "0x762b13a51005a52f11ae102307d36cae4318256c38b97183e1081a48a9b27815",
        "size": "0x2df",
        "stateRoot": "0x1159e7b38973d10bec71010a3e4d2036023dc58e66d23c3cf54205cf379bdf5c",
        "timestamp": "0x62d0465c",
        "totalDifficulty": "0x02",
        "transactions": [
            "0xc7322cc5839c34e65f2b2f4e6f7e9c938aacbd3ffe520315b63f3c3af4b62139"
        ],
        "transactionsRoot": "0x445a71cdfcf217c1295a3a1a190c986ee5d6334990f13c56b6f0d149effb1413"
    }
}
```

Get block number by block timestamp
-------------

Returns block number by the closest timestamp.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=block
   &action=getblocknobytimestamp
   &timestamp=1658293068
   &closest=after
   &apikey=YourApiKeyToken
```

#### Request query parameters

| Parameter | Description |
| --------- | ----------- |
| timestamp | a nonnegative integer that represents the block timestamp (Unix timestamp in seconds) |
| closest | direction to find the closest block number to given timestamp. Available values: `before` and `after` |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": "0x26a8c"
}
```
