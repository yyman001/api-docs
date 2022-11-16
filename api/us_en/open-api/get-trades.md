
### <span id="10">Acquisition of Trading Records</span>

1. Interface address:/open/api/get_trades
2. Interface specification:(get Request) to obtain market transaction records

* This interface does not perform signature verification

| parameter | Fill in type | Explain                                    |
| --------- | ------------ | ------------------------------------------ |
| symbol    | Must fill    | Market mark，bchbtc，See below for details |

Return value:

| field | Example      | explain    |
| ----- | ------------ | ---------- |
| code  | 0            |            |
| data  | as follows： |            |
| msg   | "suc"        | code>0fail |
```json
[
        {
            "amount": 0.55,//volume
            "price": 0.18519949,//Transaction price
            "id": 447121,
            "type": "buy"//Businesstype，Buy asbuy，buysell
        },
        {
            "amount": 16.45,
            "price": 0.18335468,
            "id": 447120,
            "type": "buy"
        },
        {
            "amount": 2,
            "price": 0.18335468,
            "id": 447119,
            "type": "buy"
        },
        {
            "amount": 2.92,
            "price": 0.183324003,
            "id": 447118,
            "type": "sell"
        }
]
```
| Virtual Currency Number | xxx-cny | xxx-btc | xxx-usdt |
| ----------------------- | ------- | ------- | -------- |
| bch                     | bcccny  | bchbtc  | bchusdt  |
| btc                     | btccny  | -       | btcusdt  |
| etc                     | etccny  | etcbtc  | etcusdt  |
| eth                     | ethcny  | ethbtc  | ethusdt  |
| ltc                     | ltccny  | ltcbtc  | ltcusdt  |





