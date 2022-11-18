## 接口地址:/api/order_list（不建议使用,后续会不定期下掉，建议使用order_list_v2)

## 接口说明:(post请求)获取订单详情

| 参数       | 填写类型 | 说明                                 |
| ---------- | -------- | ------------------------------------ |
| api_key    | 必填     | api_key                              |
| order_type | 必填     | 1:活动委托 2：已成交委托 3：历史委托 |
| sign       | 必填     | 签名                                 |
| time       | 必填     | 时间戳                               |

返回值:
```json
	{
    "code":"0",
    "data":{
        "positionCount":1, //仓位数量
        "orderCount":1, //订单数量
        "orderList":[
            {
                "symbol":"E_BTCUSD",
                "pricePrecision":2,
                "orderPriceValue":0.00051045, //价值
                "side":"SELL", //订单方向
                "orderId":26824, //订单id
                "avgPrice":0, //成交均价
                "type":1,
                "volume":2, //订单数量
                "dealVolume":0, //已成交数量
                "price":3918.07, //订单价格
                "baseSymbol":"BTC",
                "undealVolume":2, //剩余数量
                "contractId":19, //合约ID
                "contractName":"BitCoin", //合约名称
                "status":0, //可参考order_info下的订单状态解释
                "quoteSymbol":"USD"
            }
        ],
        "order_type":1
    },
    "msg":""
}
```