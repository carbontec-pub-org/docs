Blocks
=====================================

Get the most recent block number
-------------

Returns the number of the most recent block.

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

| **Parameter** | **Description** |
| --------- | ----------- |
| blockno* | Nonnegative integer that defines the block number |

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

Get block header by block hash
-------------

Returns block header (including hashes of the transactions) by block hash.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=block
   &action=getblockbyno
   &blockhash=0xf1f033be1630208234c62a34e29c70d94dac4e5470aa13659e8033ea61cad04d
   &apikey=YourApiKeyToken
```

#### Request query parameters

| **Parameter** | **Description** |
| --------- | ----------- |
| blockhash* | Block content hash |

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

Get an array of block headers by block number range
-------------

Returns an array of block headers by block number range (maximum of 20 blocks per call).

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=block
   &action=getblockrange
   &startblock=32
   &endblock=33
   &sort=asc
   &apikey=YourApiKeyToken
```

#### Request query parameters

| **Parameter** | **Description** |
| --------- | ----------- |
| startblock* | Integer block number that defines the first number of range |
| endblock* | Integer block number that defines the last number of range |
| sort* | Sorting preference, use `asc` to sort by ascending and `desc` to sort by descending |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": [
        {
            "difficulty": "0x01",
            "extraData": "0xd883010101846765746888676f312e31382e32856c696e757800000000000000000000000000000001002817cc25419648d1e49c753138ef6d4e67db506d4626accfb83a14a929f529161158182dbe1209c8aba1e7929e09c08c594eb273ad4d4212cb1ecace66292f9501",
            "gasLimit": "0x21ad8ff",
            "gasUsed": "0x1b228",
            "hash": "0xe12c3f908d1745c383c3f70ba87bdf5c17ac9942818d2d7978b73226de4409dd",
            "logsBloom": "0x00000004000000001000000000400000000000000000000000000000000000000000000002000000000000000000000000080000400080000008000000000000000000400000000000001000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001000010000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000001000000000000000000000000000000000000000000000000000000000000100000000000004000000000000000000000000000000000000000000000000000000000000000000",
            "miner": "0xeba8ddf0ab5dc9320c8ce4a14750293ee4f9b7b9",
            "mixHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
            "nonce": "0x",
            "number": "0x20",
            "parentHash": "0x548a6e00111ac0695739c664da6b40b7d448901626019749835443cad57bd3ca",
            "receiptsRoot": "0x87b2712fcff4c8fdb04ad800a4e9687e21773350bf7045938314f64a431b805c",
            "size": "0x31b",
            "stateRoot": "0xebdd7d4ee81fd4850aaf0e7012095324857985e066238595312ff00ee1d030f7",
            "timestamp": "0x62d047b5",
            "totalDifficulty": "0x21",
            "transactions": [
                "0x2bc38001d2bc5477980e02034ddafb1780022a1d1dd27a735dead9a552b4eead"
            ],
            "transactionsRoot": "0x821fad531e0735fe9bd2829d4b848b49017fbbbd798923ee9c199e46f48f9a95"
        },
        {
            "difficulty": "0x01",
            "extraData": "0xd883010101846765746888676f312e31382e32856c696e757800000000000000000000000000000001083f3f2f20e1ae171dfea4a4d0c0b94c88d150d09d95380dd23e5b9f7d5a873d8e5f17dbf6da2169abf4b054cd86145ebc41f21fa3d535ea37ab9b3fc8d67f1c9500",
            "gasLimit": "0x218c0b3",
            "gasUsed": "0x6079",
            "hash": "0xdef139f93c797aa55da19e754b705b21b21df3f3f57812028ad1c35d8bb8f1ec",
            "logsBloom": "0x00000000000000001000000000400000000000000000000000000000000000000000000002000000000000000000000000280000400080000008000000000000000000400000000000000000000000000000000000000000000000000000000040000000000000000000000000000000000000000000000000000000000000000000000040010000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
            "miner": "0xeba8ddf0ab5dc9320c8ce4a14750293ee4f9b7b9",
            "mixHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
            "nonce": "0x",
            "number": "0x21",
            "parentHash": "0xe12c3f908d1745c383c3f70ba87bdf5c17ac9942818d2d7978b73226de4409dd",
            "receiptsRoot": "0xb4bbc360704afa56678d4d25e4280cd448bd166242c0722e79dd80de843acad4",
            "size": "0x31a",
            "stateRoot": "0xf326e7a19a4fa308c5394b1dd1a06431b04ccb4e758f5ac593ab6671a0fe83fd",
            "timestamp": "0x62d047bb",
            "totalDifficulty": "0x22",
            "transactions": [
                "0x62a2f031893eae0fde3658a19ddd8ad47c806602fbf5bb5283b3f2181e5d7464"
            ],
            "transactionsRoot": "0x747ce12f2c5292cc82580477ec543caf4ee4d3155c44b5c8300f0ff4ac348112"
        }
    ]
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

| **Parameter** | **Description** |
| --------- | ----------- |
| timestamp* | Nonnegative integer that defines the block timestamp (Unix timestamp in seconds) |
| closest* | Direction to find the closest block number to a given timestamp. Available values: `before` and `after` |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": "0x26a8c"
}
```
