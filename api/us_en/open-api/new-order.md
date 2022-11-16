### <span id="14">Get the current delegation</span>


1. Interface address:/open/api/v2/new_order
2. Interface specification:(getrequest)Get the current delegation（Including uncompleted and ongoing commissions）

* Old interface /open/api/new_order It is still reserved, but not recommended

* v2Version change: Remove the tradeList transaction record from the result return value to improve efficiency;If you need transaction information for a single order, you can use /open/api/order_info interface and check it

| parameter | Fill in type      | Explain                                     |
| --------- | ----------------- | ------------------------------------------- |
| api_key   | Must fill         | api_key                                     |
| pageSize  | Selective filling | Page size                                   |
| page      | Selective filling | Page number                                 |
| sign      | Must fill         | autograph                                   |
| symbo     | l Must fill       | Market mark，btcusdt，See below for details |
| time      | Must fill         | time stamp                                  |

Return value:

|field|	Example|	explain|
|------------|--------|---------------|
|code|	0    |	 
|msg|	"suc"|	code>0fail|
|data|	as follows:|Order status(status)Explain：<br>INIT(0,"Initial order，No deal has not entered the handicap"),<br>NEW_(1,"New order，Unfinished business enters the market"),<br>FILLED(2,"Full deal"),<br>PART_FILLED(3,"Partial transaction"),<br>CANCELED(4,"Withdrawal of documents"),<br>PENDING_CANCEL(5,"Withdrawal of order"),<br>EXPIRED(6,"Abnormal order");|

```json
{
    "count":10,
    "resultList":[
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
| Virtual Currency Number | xxx-cny | xxx-btc | xxx-usdt                                 |
| ----------------------- | ------- | ------- | ---------------------------------------- |
| bcc                     | bcccny  | bccbtc  | bccusdt                                  |
| btc                     | btccny  | -       | btcusdt                                  |
| etc                     | etccny  | etcbtc  | etcusdt                                  |
| eth                     | ethcny  | ethbtc  | ethusdt                                  |
| ltc                     | ltccny  | ltcbtc  | ltcusdt                                  |
| usdt                    | usdtcny | -       | -/web/new_order-Get the current delegate |


