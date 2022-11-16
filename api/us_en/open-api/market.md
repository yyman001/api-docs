###  <span id="11">Get the latest transaction price of each pair of currencies</span>


1. Interface address:/open/api/market
2. Interface specification:(getRequest) Get the latest transaction price of each pair of currencies

| parameter | Fill in type | Explain    |
| --------- | ------------ | ---------- |
| api_key   | Must fill    | api_key    |
| sign      | Must fill    | autograph  |
| time      | Must fill    | time stamp |

Return value:

| field | Example                         | explain    |
| ----- | ------------------------------- | ---------- |
| code  | 0                               |
| data  | {"btcusdt":15000,"ethusdt":800} |
| msg   | "suc"                           | code>0fail |

| Virtual Currency Number | xxx-cny | xxx-btc | xxx-usdt |
| ----------------------- | ------- | ------- | -------- |
| bcc                     | bcccny  | bccbtc  | bccusdt  |
| btc                     | btccny  | -       | btcusdt  |
| etc                     | etccny  | etcbtc  | etcusdt  |
| eth                     | ethcny  | ethbtc  | ethusdt  |
| ltc                     | ltccny  | ltcbtc  | ltcusdt  |


---