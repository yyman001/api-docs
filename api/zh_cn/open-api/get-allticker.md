###  获取所有交易对行情
1. 接口地址:/open/api/get_allticker
2. 接口说明:(get请求)获取所有交易对行情

* 该接口不进行签名校验
* 参数:无

|字段|    实例|    解释|
|------------|--------|-----------------------------|
|code|  0    |   |
|msg|   "suc"|  code>0失败|
|data|  如下：|返回值说明<br>date: 返回数据时服务器时间 <br>symbol: 交易对（交易对1(base)简称_交易对2(quote)简称） <br>buy: 买一价 <br>high: 最高价 <br>last: 最新成交价 <br>low: 最低价 <br>sell: 卖一价 <br>vol: 成交量(最近的24小时)<br>rose:涨跌幅|
```json
{
   "date": 1534335607859,
   "ticker": [
     {
       "symbol": "btcusdt",
       "high": 7408.35984546,
       "vol": 0.01,
       "last": 1,
       "low": 7408.35984546,
       "buy": "3700.00000000",
       "sell": "7408.35984546",
       "rose": 0
     },
     {
       "symbol": "ethusdt",
       "high": 535.96,
       "vol": 6366.8591,
       "last": 20,
       "low": 279.57,
       "rose": -0.44564773
     },
     {
       "symbol": "bchusdt",
       "high": 12,
       "vol": 100,
       "last": 1,
       "low": 12,
       "buy": "11.00",
       "sell": "9.00",
       "rose": 0
     },
     {
       "symbol": "ethbtc",
       "high": 1,
       "vol": 281261,
       "last": 0.1,
       "low": 0.044039,
       "buy": "0.044049",
       "sell": "0.044049",
       "rose": -0.00022701
     },
     {
       "symbol": "nobbtc",
       "high": 0.007419,
       "vol": 1998,
       "last": 1,
       "low": 0.007419,
       "sell": "0.00741900",
       "rose": 0
     },
     {
       "symbol": "ltceth",
       "last": 0.18519949,
       "buy": "1.00000000",
       "sell": "0.18328001"
     }
   ]
 }
```