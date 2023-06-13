# Spot Price Feeds

## Query Name

- `SpotPrice`

## Query Description

This query returns the spot price of an asset in a specified currency.

## Query Parameters

The `SpotPrice` query has two parameters, which specify the pricing pair.

1. **asset**
    - description: Asset ID (e.g. PLS)
    - value type: `string`
2. **currency**
    - description: Selected currency (e.g. USD)
    - value type: `string`

To request new spot price pair, please reach out to the Fetch team or make an issue/PR in this repository

## Response Type

The query response will consist of a single 256-bit value in the following format:

- `abi_type`: ufixed256x18 (18 decimals of precision)
- `packed`: false

## Examples

### PLS/USD Spot Price

*Query Descriptor:*

```json
{"type":"SpotPrice","asset":"pls","currency":"usd"}
```

*queryData:*

```s
abi.encode("SpotPrice", abi.encode("pls", "usd"))
```

`0x00000000000000000000000000000000000000000000000000000000000000400000000000000000000000000000000000000000000000000000000000000080000000000000000000000000000000000000000000000000000000000000000953706f745072696365000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000c0000000000000000000000000000000000000000000000000000000000000004000000000000000000000000000000000000000000000000000000000000000800000000000000000000000000000000000000000000000000000000000000003706c73000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000037573640000000000000000000000000000000000000000000000000000000000`

*queryID:*

```s
keccak256(queryData)
```

`0x83245f6a6a2f6458558a706270fbcc35ac3a81917602c1313d3bfa998dcc2d4b`

### FETCH/USD Spot Price

*Query Descriptor:*

```json
{"type":"SpotPrice","asset":"fetch","currency":"usd"}
```

*queryData:*

```s
abi.encode("SpotPrice", abi.encode("fetch", "usd"))
```

`0x00000000000000000000000000000000000000000000000000000000000000400000000000000000000000000000000000000000000000000000000000000080000000000000000000000000000000000000000000000000000000000000000953706f745072696365000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000c0000000000000000000000000000000000000000000000000000000000000004000000000000000000000000000000000000000000000000000000000000000800000000000000000000000000000000000000000000000000000000000000003747262000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000037573640000000000000000000000000000000000000000000000000000000000`

*queryID:*

```s
keccak256(queryData)
```

`0x88e6984af423a49262b7d87ef9bc8746ef10def1a819961984e15372b6e1e4ad`
     

### Encoding/Decoding

A value of 99.9 would be submitted on-chain using the following bytes:

`0x0000000000000000000000000000000000000000000000056a6418b505860000`


## Dispute Considerations

Reporters should use care in selecting data sources and choosing the algorithm to combine them.

- Multiple sources should be used whenever possible.
- When retrieving data directly from exchanges, feed users might expect that exchanges with lower volumes
have their prices weighted accordingly to avoid erratic results.
- Care should also be used when retrieving data from aggregators.  
- It is the reporters responsibility to ensure that the feed result is *reasonable* enough for a community consensus, otherwise it may be subject to dispute.
- If a *reasonable* value cannot be determined, a value should not be submitted
