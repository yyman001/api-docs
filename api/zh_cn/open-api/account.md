### 资产余额
1. 接口地址: /open/api/user/account
2. 接口说明: (get请求)资产余额

| 参数    | 填写类型 | 说明    |
| ------- | -------- | ------- |
| api_key | 必填     | api_key |
| sign    | 必填     | 签名    |
| time    | 必填     | 时间戳  |

返回值:

|字段    |    实例| 解释|
|--------|--------|--------|
|code    |  0     |        |
|msg     |   "suc"|  code>0失败 |
|data    |  如下  | total_asset:总资产<br>normal:余额账户<br>locked：冻结账户<br>btcValuatin：BTC估值|

```json
{
    "total_asset": 432323.23,
    "coin_list": [
        {
            "coin": "btc",
            "normal": 32323.233,
            "locked": 32323.233,
            "btcValuatin": 112.33
        },
        {
            "coin": "ltc",
            "normal": 32323.233,
            "locked": 32323.233,
            "btcValuatin": 112.33
        },
        {
            "coin": "bch",
            "normal": 32323.233,
            "locked": 32323.233,
            "btcValuatin": 112.33
        }
    ]
}
```