## 接口地址:/api/change_level

## 接口说明:(post请求)调节杠杆倍数

| 参数          | 填写类型 | 说明     |
| ------------- | -------- | -------- |
| api_key       | 必填     | api_key  |
| contractId    | 必填     | 合约 ID  |
| leverageLevel | 必填     | 杠杆倍数 |
| positionId    | 必填     | 仓位 ID  |
| sign          | 必填     | 签名     |
| time          | 必填     | 时间戳   |

返回值:
```json
    {
	    "code":"0",
	    "data":null,
	    "msg":""
    }

```
