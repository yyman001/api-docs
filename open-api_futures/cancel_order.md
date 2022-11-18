## 接口地址:api/cancel_order

## 接口说明:(post请求)取消委托单

| 参数       | 填写类型 | 说明    |
| ---------- | -------- | ------- |
| api_key    | 必填     | api_key |
| contractId | 必填     | 合约 ID |
| orderId    | 必填     | 订单 ID |
| sign       | 必填     | 签名    |
| time       | 必填     | 时间戳  |

返回值:
```json
    {
	    "code":"0",
	    "data":null,
	    "msg":""
    }
```