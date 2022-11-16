###  <span id="15">Obtain order details</span>

1. Interface address:/open/api/order_info
2. Interface specification:(getrequest)Obtain order details

| parameter | Fill in type | Explain                                    |
| --------- | ------------ | ------------------------------------------ |
| api_key   | Must fill    | api_key                                    |
| order_id  | Must fill    | Order ID                                   |
| sign      | Must fill    | autograph                                  |
| symbol    | Must fill    | Market mark，ethbtc，See below for details |
| time      | Must fill    | time stamp                                 |

Return value:

| field | Example     | explain    |
| ----- | ----------- | ---------- |
| code  | 0           |            |
| data  | as follows: |            |
| msg   | "suc"       | code>0fail |
```json
{
    "order_info":{
        "id":343,
        "side":"sell",
        "side_msg":"Sell out",
        "created_at":"09-22 12:22",
        "price":222.33,
        "volume":222.33,
        "deal_volume":222.33,
        "total_price":222.33,
        "fee":222.33,
        "avg_price":222.33
        }
    }
    "trade_list":[
        {
            "id":343,
            "created_at":"09-22 12:22",
            "price":222.33,
            "volume":222.33,
            "deal_price":222.33,
            "fee":222.33
        },
        {
            "id":345,
            "created_at":"09-22 12:22",
            "price":222.33,
            "volume":222.33,
            "deal_price":222.33,
            "fee":222.33
        }
    ]
}
```
