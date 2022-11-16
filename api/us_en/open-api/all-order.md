### <span id="2">Acquire full delegation</span>

1. Interface address:/open/api/v2/all_order
2. Interface specification:(getrequest)Acquire full delegation
3. startDate，endDate interval cannot exceed ten minutes
4. No startDate, endDate, default first 10 minutes

* Old interface/open/api/all_order It is still reserved, but not recommended

* v2Version change: Remove from the result return value tradeListTransaction record,Enhance efficiency;If transaction information for a single order is required

,you can use /open/api/order_info interface and check it

| parameter | Fill in type      | Explain                                                       |
| --------- | ----------------- | ------------------------------------------------------------- |
| api_key   | Must fill         | api_key                                                       |
| endDate   | Selective filling | （Added) End time, accurate to seconds“yyyy-MM-dd mm:hh:ss”   |
| pageSize  | Selective filling | Page size                                                     |
| page      | Selective filling | Page number                                                   |
| sign      | Must fill         | autograph                                                     |
| startDate | Selective filling | （Added) Start time, accurate to seconds“yyyy-MM-dd mm:hh:ss” |
| symbol    | Must fill         | Market mark，btcusdt，See below for details                   |
| time      | Must fill         | time stamp                                                    |


Return value:

| field | Example     | explain    |
| ----- | ----------- | ---------- |
| code  | 0           |            |
| data  | as follows: |
| msg   | "suc"       | code>0fail |
```json
{
    "count":10,
    "orderList":[
        {
            "side":"BUY",
            "total_price":"0.10000000",
            "created_at":1510993841000,
            "avg_price":"0.10000000",
            "countCoin":"btc",
            "source":1,
            "type":1,
            "side_msg":"Purchase",
            "volume":"1.000",
            "price":"0.10000000",
            "source_msg":"WEB",
            "status_msg":"Full deal",
            "deal_volume":"1.00000000",
            "id":424,
            "remain_volume":"0.00000000",
            "baseCoin":"eth",
            "status":2
        },
        {
            "side":"SELL",
            "total_price":"0.09900000",
            "created_at":1510993715000,
            "avg_price":"0.10000000",
            "countCoin":"btc",
            "source":1,
            "type":1,
            "side_msg":"Sell out",
            "volume":"1.000",
            "price":"0.09900000",
            "source_msg":"WEB",
            "status_msg":"Full deal",
            "deal_volume":"1.00000000",
            "id":423,
            "remain_volume":"0.00000000",
            "baseCoin":"eth",
            "status":2
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
