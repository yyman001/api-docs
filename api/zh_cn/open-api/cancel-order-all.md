### 根据币对取消全部委托单

1. 接口地址:/open/api/cancel_order_all
2. 接口说明:(post请求)根据币对取消全部委托单（最多取消两千条，多余两千请循环撤销）

| 参数    | 填写类型 | 说明                         |
| ------- | -------- | ---------------------------- |
| api_key | 必填     | api_key                      |
| sign    | 必填     | 签名                         |
| symbol  | 必填     | 市场标记，ethbtc，详情看下面 |
| time    | 必填     | 时间戳                       |

返回值:

| 字段 | 实例  | 解释        |
| ---- | ----- | ----------- |
| code | 0     |             |
| data | “”    |             |
| msg  | "suc" | code>0 失败 |

 
| 虚拟币编号 | xxx-cny（xxx101） | xxx-btc（xxx201） |
| ---------- | ----------------- | ----------------- |
| bcc        | bcccny            | bccbtc            |
| btc        | btccny            | -                 |
| etc        | etccny            | etcbtc            |
| eth        | ethcny            | ethbtc            |
| ltc        | ltccny            | ltcbtc            |
