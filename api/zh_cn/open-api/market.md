###  <span id="11">获取各个币对的最新成交价</span>


1. 接口地址:/open/api/market
2. 接口说明:(get请求)获取各个币对的最新成交价

| 参数    | 填写类型 | 说明    |
| ------- | -------- | ------- |
| api_key | 必填     | api_key |
| sign    | 必填     | 签名    |
| time    | 必填     | 时间戳  |

返回值:

| 字段 | 实例                            | 解释        |
| ---- | ------------------------------- | ----------- |
| code | 0                               | code>0 失败 |
| data | {"btcusdt":15000,"ethusdt":800} |             |
| msg  | "suc"                           |             |

| 虚拟币编号 | xxx-cny | xxx-btc | xxx-usdt |
| ---------- | ------- | ------- | -------- |
| bcc        | bcccny  | bccbtc  | bccusdt  |
| btc        | btccny  | -       | btcusdt  |
| etc        | etccny  | etcbtc  | etcusdt  |
| eth        | ethcny  | ethbtc  | ethusdt  |
| ltc        | ltccny  | ltcbtc  | ltcusdt  |
