###  <span id="9">Get the current market quotations</span>


1. Interface address:/open/api/get_ticker
2. Interface specification:(get Request) to get the current market quotations 

* This interface does not perform signature verification

| parameter | Fill in type | Explain                                     |
| --------- | ------------ | ------------------------------------------- |
| symbol    | Must fill    | Market mark，btcusdt，See below for details |

Return value:

| field | Example      | explain    |
| ----- | ------------ | ---------- |
| code  | 0            |
| data  | as follows： |
| msg   | "suc"        | code>0fail |
```json
{
    "high": 1,//Maximum value
    "vol": 10232.26315789,//Trading volume
    "last": 173.60263169,//Latest Transaction Price
    "low": 0.01,//Minimum value
    "buy": "0.01000000",//Buy one price
    "sell": "1.12345680",//Selling price
    "rose": -0.44564773,//Ups and downs
    "time": 1514448473626
}
```
| Virtual Currency Number | xxx-cny | xxx-btc | xxx-usdt |
| ----------------------- | ------- | ------- | -------- |
| bcc                     | bcccny  | bccbtc  | bccusdt  |
| btc                     | btccny  | -       | btcusdt  |
| etc                     | etccny  | etcbtc  | etcusdt  |
| eth                     | ethcny  | ethbtc  | ethusdt  |
| ltc                     | ltccny  | ltcbtc  | ltcusdt  |





---