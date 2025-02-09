# Custom Linking

The Uniswap front-end supports URL query parameters to allow for custom linking to the Uniswap exchange. Users and developers can use these query parameters to link to the Uniswap exchange with custom prefilled settings.

Each Page has specific available URL parameters that can be set. Global parameters can be used on all pages.

A parameter used on an incorrect page will have no effect on exchange settings. Parameters not set with a URL parameter will be set to standard exchange defaults.


| Parameter | Type     | Description                      |
| :-------- | :------- | :------------------------------- |
| theme     | `String` | Sets them to dark or light mode. |

#### Theme Options

Theme can be set as `light` or `dark`.

#### Example Usage

```typescript
https://uniswap.exchange/swap?theme=dark
```


## Swap Page

| Parameter      | Type      | Description                                                            |
| :------------- | :-------- | :--------------------------------------------------------------------- |
| inputCurrency  | `address` | Input currency that will be swapped for output currency.               |
| outputCurrency | `address` | Output currency that input currency will be swapped for.               |
| slippage       | `number`  | Max slippage to be used during transaction (in bips)               |
| exactAmount    | `number`  | The custom token amount to buy or sell.                                |
| exactField     | `string`  | The field to set custom token amount for. Must be `input` or `output`. |

#### Constraints

Addresses must be valid ERC20 addresses. Slippage and amount values must be valid numbers accepted by the exchange (or error will prevent from swapping). Slippage can 0, or within the range 10->9999 bips (which converts to 0%, 0.01%->99%)

#### Setting Amounts

Two parameters, exactField and exactAmount can be used to set specific token amounts to be sold or bought. Both fields must be set in the URL or there will be no effect on the settings.

#### Example Usage

```typescript
https://uniswap.exchange/swap?exactField=input?exactAmount=10?inputCurrency=0x0F5D2fB29fb7d3CFeE444a200298f468908cC942
```

## Send Page

The send page has the same options available as the Swap page, plus one additional paramter, `recipient`.

| Parameter | Type      | Description                                     |
| :-------- | :-------- | :---------------------------------------------- |
| recipient | `address` | Address of the recipient of a send transaction. |

#### Example Usage

```typescript
https://uniswap.exchange/send?recipient=0x74Aa01d162E6dC6A657caC857418C403D48E2D77
```

## Pool Page

The Pool page is made up of 3 subroutes: `add-liquidity`, `remove-liquidity`, `create-exchange`.

### Add Liquidity

| Parameter   | Type      | Description                                            |
| :---------- | :-------- | :----------------------------------------------------- |
| ethAmount   | `number`  | Amount of ETH to deposit into the pool.                |
| token       | `address` | ERC20 address of the pool to add liquidity to.         |
| tokenAmount | `number`  | Amount of the selected token to deposit into the pool. |

#### Example Usage

```typescript
https://uniswap.exchange/add-liquidity?ethAmount=2.34?token=0x42456D7084eacF4083f1140d3229471bbA2949A8?tokenAmount=300
```

### Remove Liquidity

| Parameter       | Type      | Description                                                                           |
| :-------------- | :-------- | :------------------------------------------------------------------------------------ |
| poolTokenAddress       | `address` | Pool to withdraw liquidity from. (Must be an ERC20 address with an existing exchange) |
| poolTokenAmount | `number`  | Amount of pool token to be withdrawn from liquidity pool.                             |

#### Example Usage

```typescript
https://uniswap.exchange/remove-liquidity?poolTokenAmount=1.23
```

### Create Exchange

| Parameter    | Type      | Description                                                                                                |
| :----------- | :-------- | :--------------------------------------------------------------------------------------------------------- |
| tokenAddress | `address` | ERC20 token to create the exchange for. Must be valid ERC20 token for which there is no existing exchange. |

#### Example Usage

```typescript
uniswap.exchange/create-exchange?tokenAddress=0x0F5D2fB29fb7d3CFeE444a200298f468908cC942
```

### Custom Routes

Custom token routes can still be used in combination with URL paramters. URL paramters are higher in the settings hierarchy than custom routes.

An example using custom token route and URL paramters.

```typescript
uniswap.exchange/swap/0x0F5D2fB29fb7d3CFeE444a200298f468908cC942?exactField=input?exactAmount=10
```
