## 接口地址:/api/order_list_v2

## 接口说明:(post请求)获取订单详情

| 参数       | 填写类型 | 说明                                 |
| ---------- | -------- | ------------------------------------ |
| api_key    | 必填     | api_key                              |
| contractId | 必填     | 合约 Id                              |
| order_type | 必填     | 1:活动委托 2：已成交委托 3：历史委托 |
| pageNo     | 必填     | 页码                                 |
| pageSize   | 必填     | 每页数量（默认 5，最大 200）         |
| sign       | 必填     | 签名                                 |
| time       | 必填     | 时间戳                               |

返回值:
```json
	{
    "code":"0",
    "data":{
        "count":1, //订单数量
        "orderList":[
            {
                "orderId":26824, //订单id
                "contractId":1, //合约Id
                "side":"SELL", //订单方向
                "type":1,
                "volume":2, //订单数量
                "dealVolume":0, //已成交数量
                "price":3918.07, //订单价格
                "status":0, //可参考order_info下的订单状态解释
                "positionId":13, //多仓模式下关联的仓位Id
                "level":3 //杠杆倍数
            }
        ]
    },
    "msg":""
}
```