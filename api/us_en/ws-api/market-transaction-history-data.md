### <span id="25">Request-transaction history data </span>

* request:
```json
{"event":"req","params":{"channel":"market_$base$quote_trade_ticker","cb_id":"custom","top":200}}
```
* Direct return of transaction information:
```json
{
    "event_rep":"rep","channel":"market_$base$quote_trade_ticker","cb_id":"Please Return by the Way You Came","ts":1506584998239,"status":"ok",
    "top":200,//Maximum support 200
    "data":[
        {
            "id":12121,//Transaction ID
            "side":"buy",//Direction of businessbuy,sell
            "price":32.233,//Unit Price
            "vol":232,//Number
            "amount":323,//Total
            "ts":1506584998239//Data generation time
        },
        {
            "id":12120,//Transaction ID
            "side":"buy",//Direction of business buy,sell
            "price":32.233,//Unit Price
            "vol":232,//Number
            "amount":323,//Total
            "ts":1506584998239,//Data generation time
            "ds":'2017-09-10 23:12:21'
        }
    ]
}
```