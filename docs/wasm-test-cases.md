# EWASM Test Cases:

## {interface method}
 - [x] _{test name}_ - {test description}

## getAddress
 - [x] _getAddress_ - Transaction to account with code which calls `getAddress` and stores the result to storage

## getBlockHash (should this be a Blockchain test?)
 - [x] _getBlockHash_ - Transaction to account with code which calls `getBlockHash` with a value of 0 and stores the result to storage

## getCaller
 - [x] _getCaller_ - Transaction to account with code which calls `getBlockHash` with a value of 0 and stores the result to storage.  Expect the result to be Genesis block hash

## getCodeSize
 - [x] _getCodeSize_ - Transaction to account with code which calls `getCodeSize` and stores the result to storage.  Expect the result to be the length of the account's code

## getBlockDifficulty
 - [x] _getBlockDifficulty_ - Transaction to account with code which calls `getBlockDifficulty` and stores the result to storage.  Expect the result to be predefined difficulty

## getGasLeft
 - [x] _getGasLeft_ - Transaction to account with code which calls `useGas(1000000)`, then `getGasLeft` and stores the result to storage.  Expect `resulting_gas = gasLimit - 1000000 - base_tx_cost`

## getBlockNumber (should this be a Blockchain test?)
 - [x] _getBlockNumber_ - Transaction to account with code which calls `getBlockNumber`, and stores the result to storage.  Expect predefined block number `1` to be stored in storage.

## selfDestruct
 - [x] _selfDestruct_ - Transaction to account which `selfDestruct`s to the transaction originator.  Expect that the transaction originator receives the funds from the self-destructed account and the self-destructed account doesn't exist after the transaction is complete.

## callDelegate

## callStatic

## useGas
 - [x] _useGas_ - Transaction to account which calls `useGas(1000)`.  Expect that the account which received the transaction has `balance=balance-(1000+metered_code_cost)` 

## getCallDataSize
 - [x] _getCallDataSize_ - Transaction (containing large amount of data) to an account with code that calls `getCallDataSize` and stores the result to storage.  Expect that the value stored is equal to the size of the call data passed with the transaction. 

## getBalance:
 - [x] _getBalanceExt_ - Transaction to an account with code which calls `getBalance` on an account other than itself
 - [x] _getBalance_ - Transaction to an account with code which calls `getBalance` on itself

## call
 - [x] _call_ - Transaction to an account which calls another account which stores a value to storage
 - [x] _callNoDataNoValue_ - Transaction to an account which makes a call providing no data and no value: https://github.com/ewasm/tests/pull/6

## storageLoad
 - [x] _storageLoad_ - Transaction to an account with code that loads a value already stored in storage and stores it in another storage location.

## codeCopy
 - [x] _codeCopy_ - Transaction to an account with code which copies 10 bytes from the account's code and stores them in storage.

## externalCodeCopy
 - [x] _extCodeCopy_ - Transaction to an account with code which copies 10 bytes from the code of another account and stores them in storage.

## getBlockGasLimit
 - [x] _getBlockGasLimit_ - Transaction to an account with code which calls `getBlockGasLimit` and stores the result to storage.

## getTxGasPrice (should this be a Blockchain test?)
 - [x] _getTxGasPrice_ - Transaction to an account with code which calls `getTxGasPrice` and stores the result to storage.

## getTxOrigin (should this be a Blockchain test?)
 - [x] _getTxOrigin_ - Transaction to an account with code which calls `getTxOrigin` and stores the result to storage.

## getBlockTimestamp (should this be a Blockchain test?)
 - [x] _getBlockTimestamp_ - Transaction to an account with code which calls `getTxOrigin` and stores the result to storage.

## return

## create

## callDataCopy
 - [x] _callDataCopy_ - Transaction with data to an account with code which calls `callDataCopy` and stores the result to storage.

## callCode
 - [x] _callCode_ - Transaction with data to an account with code which calls `callCode` with the code of another account.  The code stores a value to storage.  The contract which invoked the `callCode` also stores the return value from `callCode` in storage to ensure the call is successful.

## storageStore

## getCallValue
 - [x] _getCallValue_ - Transaction with value to an account which calls `getCallValue` and stores the value passed to storage.

## getBlockCoinbase
 - [x] _getBlockCoinbase_ - Transaction with value to an account which calls `getBlockCoinbase` and stores the value passed to storage.

## getExternalCodeSize 
 - [x] _getBlockCoinbase_ - Transaction to account which calls `getExternalCodeSize` with its own address, stores the result to storage, then calls `getExternalCodeSize` with another account's address and stores the result to another storage location.

## revert

## getReturnDataSize

## returnDataCopy

## createFromTransaction

## log
