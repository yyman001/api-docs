###  <span id="5">Cancellation of all orders of attorney according to currency pair</span>

1. Interface address:/open/api/cancel_order_all
2. Interface specification:(postrequest)Cancellation of all orders of attorney according to currency pair（Up to 2,000 cancellations, more than 2,000 please revoke）

| parameter | Fill in type | Explain                                    |
| --------- | ------------ | ------------------------------------------ |
| api_key   | Must fill    | api_key                                    |
| sign      | Must fill    | autograph                                  |
| symbol    | Must fill    | Market mark，ethbtc，See below for details |
| time      | Must fill    | time stamp                                 |

Return value:

| field | Example | explain    |
| ----- | ------- | ---------- |
| code  | 0       |            |
| data  | “”      |            |
| msg   | "suc"   | code>0fail |

 
| Virtual Currency Number | xxx-cny（xxx101） | xxx-btc（xxx201） |
| ----------------------- | ----------------- | ----------------- |
| bcc                     | bcccny            | bccbtc            |
| btc                     | btccny            | -                 |
| etc                     | etccny            | etcbtc            |
| eth                     | ethcny            | ethbtc            |
| ltc                     | ltccny            | ltcbtc            |

---