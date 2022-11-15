###  <span id="15">获取订单详情</span>

1. 接口地址: /open/api/order_info
2. 接口说明:(get请求)获取订单详情

| 参数     | 填写类型 | 说明                         |
| -------- | -------- | ---------------------------- |
| api_key  | 必填     | api_key                      |
| order_id | 必填     | 订单 ID                      |
| sign     | 必填     | 签名                         |
| symbol   | 必填     | 市场标记，ethbtc，详情看下面 |
| time     | 必填     | 时间戳                       |

返回值:

| 字段 | 实例  | 解释        |
| ---- | ----- | ----------- |
| code | 0     |             |
| data | 如下: |             |
| msg  | "suc" | code>0 失败 |

```json
{
    "order_info":{
        "id":343,
        "side":"sell",
        "side_msg":"卖出",
        "created_at":"09-22 12:22",
        "price":222.33,
        "volume":222.33,
        "deal_volume":222.33,
        "total_price":222.33,
        "fee":222.33,
        "avg_price":222.33}
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