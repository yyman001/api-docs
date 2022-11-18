## 接口地址:/api/cancel_order_all

## 接口说明:(post请求)取消合约下所有委托单

| 参数       | 填写类型 | 说明    |
| ---------- | -------- | ------- |
| api_key    | 必填     | api_key |
| contractId | 必填     | 合约 ID |
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