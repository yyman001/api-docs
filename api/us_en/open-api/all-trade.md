### <span id="3">Obtain all transaction records</span>

1. Interface address:/open/api/all_trade
2. Interface Description: (get request) Get all transaction records

| parameter | Fill in type      | Explain                                                      |
| --------- | ----------------- | ------------------------------------------------------------ |
| api_key   | Must fill         | api_key                                                      |
| endDate   | Selective filling | (Added) End time, accurate to seconds“yyyy-MM-dd HH:mm:ss”   |
| pageSize  | Selective filling | Page size                                                    |
| page      | Selective filling | Page number                                                  |
| sign      | Must fill         | autograph                                                    |
| sort      | Selective filling | 1Representing reverse order                                  |
| startDate | Selective filling | (Added) Start time, accurate to seconds“yyyy-MM-dd HH:mm:ss” |
| symbol    | Must fill         | Market mark，btcusdt，See below for details                  |
| time      | Must fill         | time stamp                                                   |

Return value:

| field | Example     | explain    |
| ----- | ----------- | ---------- |
| data  | as follows: |
| code  | 0           |            |
| msg   | "suc"       | code>0fail |
```json
{
    "count":22,
    "resultList":[
        {
            "volume":"1.000",
            "side":"BUY",
            "feeCoin":"YLB",
            "price":"0.10000000",
            "fee":"0.16431104",
            "ctime":1510996571195,
            "deal_price":"0.10000000",
            "id":306,
            "type":"Purchase",
            "bid_id":1001,
            "ask_id":1002,
            "bid_user_id":10001,
            "ask_user_id":10001
 
        },
        {
            "volume":"0.850",
            "side":"BUY",
            "feeCoin":"YLB",
            "price":"0.10000000",
            "fee":"0.13966438",
            "ctime":1510996571190,
            "deal_price":"0.08500000",
            "id":305,
            "type":"Purchase",
            "bid_id":1001,
            "ask_id":1002,
            "bid_user_id":10001,
            "ask_user_id":10001
        },
        {
            "volume":"0.010",
            "side":"BUY",
            "feeCoin":"YLB",
            "price":"0.10000000",
            "fee":"0.00164311",
            "ctime":1510995560344,
            "deal_price":"0.00100000",
            "id":291,
            "type":"Purchase",
            "bid_id":1001,
            "ask_id":1002,
            "bid_user_id":10001,
            "ask_user_id":10001
        }
    ]
}
```
| Virtual Currency Number | xxx-cny | xxx-btc | xxx-usdt |
| ----------------------- | ------- | ------- | -------- |
| bcc                     | bcccny  | bccbtc  | bccusdt  |
| btc                     | btccny  | -       | btcusdt  |
| etc                     | etccny  | etcbtc  | etcusdt  |
| eth                     | ethcny  | ethbtc  | ethusdt  |
| ltc                     | ltccny  | ltcbtc  | ltcusdt  |
| usdt                    | usdtcny | -       | -        |


---