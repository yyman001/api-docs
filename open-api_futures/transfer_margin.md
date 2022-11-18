## 接口地址:/api/transfer_margin

## 接口说明:(post请求)追加保证金

| 参数       | 填写类型 | 说明                   |
| ---------- | -------- | ---------------------- |
| amount     | 选填     | 追加数量（转出为负数） |
| api_key    | 必填     | api_key                |
| contactId  | 必填     | 合约 ID                |
| positionId | 必填     | 仓位 ID                |
| sign       | 必填     | 签名                   |
| time       | 必填     | 时间戳                 |

返回值:
```json
    {
	    "code":"0",
	    "data":null,
	    "msg":""
    }
```

