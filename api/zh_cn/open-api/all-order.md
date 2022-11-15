### 获取全部委托

1. 接口地址:/open/api/v2/all_order
2. 接口说明:(get请求)获取全部委托
3. 开始时间，结束时间不能相差`10分钟`，
4. 没有开始时间，结束时间时，默认前10分钟数据

* 旧接口 `/open/api/all_order` 仍保留,但已经不建议使用

* v2版本变化: 去掉了结果返回值中的tradeList成交记录,提升效率;如果需要单一订单的成交信息,可以使用 /open/api/order_info 接口单独去查

| 参数      | 填写类型 | 说明                                            |
| --------- | -------- | ----------------------------------------------- |
| api_key   | 必填     | api_key                                         |
| endDate   | 选填     | （新增）结束时间，精确到秒“yyyy-MM-dd mm:hh:ss” |
| page      | 选填     | 页码                                            |
| pageSize  | 选填     | 页面大小                                        |
| sign      | 必填     | 签名                                            |
| startDate | 选填     | （新增）开始时间，精确到秒“yyyy-MM-dd mm:hh:ss” |
| symbol    | 必填     | 市场标记，btcusdt，详情看下面                   |
| time      | 必填     | 时间戳                                          |

返回值:

| 字段 | 实例  | 解释        |
| ---- | ----- | ----------- |
| code | 0     |             |
| data | 如下: |             |
| msg  | "suc" | code>0 失败 |

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
            "side_msg":"买入",
            "volume":"1.000",
            "price":"0.10000000",
            "source_msg":"WEB",
            "status_msg":"完全成交",
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
            "side_msg":"卖出",
            "volume":"1.000",
            "price":"0.09900000",
            "source_msg":"WEB",
            "status_msg":"完全成交",
            "deal_volume":"1.00000000",
            "id":423,
            "remain_volume":"0.00000000",
            "baseCoin":"eth",
            "status":2
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

---