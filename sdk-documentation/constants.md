# Types

Below is an exhaustive list of all external constants used in the SDK.

[Actual file](https://github.com/Uniswap/uniswap-sdk/blob/master/src/constants/index.ts).

```typescript
import BigNumber from 'bignumber.js'

import ERC20 from './abis/ERC20.json'
import FACTORY from './abis/FACTORY.json'
import EXCHANGE from './abis/EXCHANGE.json'

export const ETH = 'ETH'

export enum SUPPORTED_CHAIN_ID {
  Mainnet = 1,
  Ropsten = 3,
  Rinkeby = 4,
  Kovan = 42
}

export const FACTORY_ADDRESS: { [key: number]: string } = {
  [SUPPORTED_CHAIN_ID.Mainnet]: '0xc0a47dFe034B400B47bDaD5FecDa2621de6c4d95',
  [SUPPORTED_CHAIN_ID.Ropsten]: '0x9c83dCE8CA20E9aAF9D3efc003b2ea62aBC08351',
  [SUPPORTED_CHAIN_ID.Rinkeby]: '0xf5D915570BC477f9B8D6C0E980aA81757A3AaC36',
  [SUPPORTED_CHAIN_ID.Kovan]: '0xD3E51Ef092B2845f10401a0159B2B96e8B6c3D30'
}

export const FACTORY_ABI: string = JSON.stringify(FACTORY)
export const EXCHANGE_ABI: string = JSON.stringify(EXCHANGE)

export enum TRADE_TYPE {
  ETH_TO_TOKEN = 'ETH_TO_TOKEN',
  TOKEN_TO_ETH = 'TOKEN_TO_ETH',
  TOKEN_TO_TOKEN = 'TOKEN_TO_TOKEN'
}

export enum TRADE_EXACT {
  INPUT = 'INPUT',
  OUTPUT = 'OUTPUT'
}

export enum TRADE_METHODS {
  ethToTokenSwapInput = 'ethToTokenSwapInput',
  ethToTokenTransferInput = 'ethToTokenTransferInput',
  ethToTokenSwapOutput = 'ethToTokenSwapOutput',
  ethToTokenTransferOutput = 'ethToTokenTransferOutput',
  tokenToEthSwapInput = 'tokenToEthSwapInput',
  tokenToEthTransferInput = 'tokenToEthTransferInput',
  tokenToEthSwapOutput = 'tokenToEthSwapOutput',
  tokenToEthTransferOutput = 'tokenToEthTransferOutput',
  tokenToTokenSwapInput = 'tokenToTokenSwapInput',
  tokenToTokenTransferInput = 'tokenToTokenTransferInput',
  tokenToTokenSwapOutput = 'tokenToTokenSwapOutput',
  tokenToTokenTransferOutput = 'tokenToTokenTransferOutput'
}

export const TRADE_METHOD_IDS: { [key: string]: string } = {
  [TRADE_METHODS.ethToTokenSwapInput]: '0xf39b5b9b',
  [TRADE_METHODS.ethToTokenTransferInput]: '0xad65d76d',
  [TRADE_METHODS.ethToTokenSwapOutput]: '0x6b1d4db7',
  [TRADE_METHODS.ethToTokenTransferOutput]: '0x0b573638',
  [TRADE_METHODS.tokenToEthSwapInput]: '0x95e3c50b',
  [TRADE_METHODS.tokenToEthTransferInput]: '0x7237e031',
  [TRADE_METHODS.tokenToEthSwapOutput]: '0x013efd8b',
  [TRADE_METHODS.tokenToEthTransferOutput]: '0xd4e4841d',
  [TRADE_METHODS.tokenToTokenSwapInput]: '0xddf7e1a7',
  [TRADE_METHODS.tokenToTokenTransferInput]: '0xf552d91b',
  [TRADE_METHODS.tokenToTokenSwapOutput]: '0xb040d545',
  [TRADE_METHODS.tokenToTokenTransferOutput]: '0xf3c0efe9'
}

export enum FIXED_UNDERFLOW_BEHAVIOR {
  ZERO = 'ZERO',
  LESS_THAN = 'LESS_THAN',
  ONE_DIGIT = 'ONE_DIGIT'
}
```
