### 获取全部成交记录

1. 接口地址:/open/api/all_trade
2. 接口说明:(get请求)获取全部成交记录

| 参数      | 填写类型 | 说明                                            |
| --------- | -------- | ----------------------------------------------- |
| api_key   | 必填     | api_key                                         |
| endDate   | 选填     | （新增）结束时间，精确到秒“yyyy-MM-dd HH:mm:ss” |
| page      | 选填     | 页码                                            |
| pageSize  | 选填     | 页面大小                                        |
| sign      | 必填     | 签名                                            |
| sort      | 选填     | 1 表示倒序                                      |
| startDate | 选填     | （新增）开始时间，精确到秒“yyyy-MM-dd HH:mm:ss” |
| symbol    | 必填     | 市场标记，btcusdt，详情看下面                   |
| time      | 必填     | 时间戳                                          |

返回值:

| 字段 | 实例  | 解释          |
| ---- | ----- | ------------- |
| code | 0     |               |
| data | 如下: |               |
| msg  | "suc" | code > 0 失败 |

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
            "type":"买入",
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
            "type":"买入",
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
            "type":"买入",
            "bid_id":1001,
            "ask_id":1002,
            "bid_user_id":10001,
            "ask_user_id":10001
        }
    ]
}
```

| 虚拟币编号 | xxx-cny | xxx-btc | xxx-usdt |
| ---------- | ------- | ------- | -------- |
| bcc        | bcccny  | bccbtc  | bccusdt  |
| btc        | btccny  | -       | btcusdt  |
| etc        | etccny  | etcbtc  | etcusdt  |
| eth        | ethcny  | ethbtc  | ethusdt  |
| ltc        | ltccny  | ltcbtc  | ltcusdt  |
| usdt       | usdtcny | -       | -        |
