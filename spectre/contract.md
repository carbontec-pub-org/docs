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

Get ABI for verified contract
-------------

Returns the ABI for verified contract.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=contract
   &action=getabi
   &address=0x0000000000000000000000000000000000001000
   &apikey=YourApiKeyToken
```

#### Request query parameters

| **Parameter** | **Description** |
| --------- | ----------- |
| address* | Hex-string address is used to identify a contract |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": "[{\"constant\":false,\"inputs\":[{\"name\":\"voucher_token\",\"type\":\"bytes32\"}],\"name\":\"burn\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"payable\":false,\"stateMutability\":\"nonpayable\",\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"voucher_token\",\"type\":\"bytes32\"}],\"name\":\"is_expired\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"payable\":false,\"stateMutability\":\"view\",\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"voucher_token\",\"type\":\"bytes32\"}],\"name\":\"is_burnt\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"payable\":false,\"stateMutability\":\"nonpayable\",\"type\":\"function\"},{\"inputs\":[{\"name\":\"voucher_token\",\"type\":\"bytes32\"},{\"name\":\"_lifetime\",\"type\":\"uint256\"}],\"payable\":false,\"stateMutability\":\"nonpayable\",\"type\":\"constructor\"}]"
}
```

Get contract source code for verified contract
-------------

Returns source code for a verified contract.

#### Sample request

```
http://spectre.devgraphite.com/api
   ?module=contract
   &action=getsourcecode
   &address=0x0000000000000000000000000000000000001000
   &apikey=YourApiKeyToken
```

#### Request query parameters

| **Parameter** | **Description** |
| --------- | ----------- |
| address* | Hex-string address is used to identify a contract |

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": {
        "abi": "[{\n\"type\":\"event\",\n\"inputs\": [{\"name\":\"a\",\"type\":\"uint256\",\"indexed\":true},{\"name\":\"b\",\"type\":\"bytes32\",\"indexed\":false}],\n\"name\":\"Event\"\n}, {\n\"type\":\"event\",\n\"inputs\": [{\"name\":\"a\",\"type\":\"uint256\",\"indexed\":true},{\"name\":\"b\",\"type\":\"bytes32\",\"indexed\":false}],\n\"name\":\"Event2\"\n}, {\n\"type\":\"function\",\n\"inputs\": [{\"name\":\"a\",\"type\":\"uint256\"}],\n\"name\":\"foo\",\n\"outputs\": []\n}]\n",
        "compilerVersion": "v0.2.1-2016-01-30-91a6b35",
        "contractName": "Test",
        "optimizationUsed": "1",
        "sourceCode": "pragma solidity >0.4.24;\n\ncontract Test {\nconstructor() public { b = hex\"12345678901234567890123456789012\"; }\nevent Event(uint indexed a, bytes32 b);\nevent Event2(uint indexed a, bytes32 b);\nfunction foo(uint a) public { emit Event(a, b); }\nbytes32 b;\n}\n"
    }
}
```

Verify a contract with its source code and contract creation information
-------------

Verifies a contract with its source code.

#### Sample request (HTTP POST)

```
http://spectre.devgraphite.com/api
   ?module=contract
   &action=verifysourcecode
   &apikey=YourApiKeyToken
```

Body (json):

``` json
{
    "addressHash": "0x9271602210f21ab82999dd43792a12e63c6e3269",
    "name": "test_contract",
    "compilerVersion": "v0.2.1-2016-01-30-91a6b35",
    "optimization": false,
    "contractSourceCode": "// SPDX-License-Identifier: MIT\npragma solidity ^0.8.13; contract Counter { uint public count; function get() public view returns (uint) { return count; } function inc() public { count += 1; } function dec() public { count -= 1; }}"
}
```

#### Sample response

``` json
{
    "status": "1",
    "message": "OK",
    "result": {
        "abi": "[{\n\"type\":\"event\",\n\"inputs\": [{\"name\":\"a\",\"type\":\"uint256\",\"indexed\":true},{\"name\":\"b\",\"type\":\"bytes32\",\"indexed\":false}],\n\"name\":\"Event\"\n}, {\n\"type\":\"event\",\n\"inputs\": [{\"name\":\"a\",\"type\":\"uint256\",\"indexed\":true},{\"name\":\"b\",\"type\":\"bytes32\",\"indexed\":false}],\n\"name\":\"Event2\"\n}, {\n\"type\":\"function\",\n\"inputs\": [{\"name\":\"a\",\"type\":\"uint256\"}],\n\"name\":\"foo\",\n\"outputs\": []\n}]\n",
        "compilerVersion": "v0.2.1-2016-01-30-91a6b35",
        "contractName": "test_contract",
        "optimizationUsed": "0",
        "sourceCode": "// SPDX-License-Identifier: MIT\npragma solidity ^0.8.13; contract Counter { uint public count; function get() public view returns (uint) { return count; } function inc() public { count += 1; } function dec() public { count -= 1; }}"
    }
}
```
