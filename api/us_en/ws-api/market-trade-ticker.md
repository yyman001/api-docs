### <span id="23">Subscription-Real-time Transaction Information </span>

* request:
```json
{"event":"sub","params":{"channel":"market_$base$quote_trade_ticker","cb_id":"custom"}}
```
* Return to subscription status once:
```json
{"event_rep":"subed","channel":"market_$base$quote_trade_ticker","cb_id":"Please Return by the Way You Came","ts":1506584998239,"status":"ok"}
```
* Continue to return subscription messages:
```json
{
    "channel":"market_$base$quote_trade_ticker",//Subscription transactions versus market$base$quoteExpressbtckrwetc.
    "ts":1506584998239,//Request time
    "tick":{
        "id":12121,//dataThe biggest deal ID
        "ts":1506584998239,//dataThe biggest deal
        "data":[
            {
                "id":12121,//transaction ID
                "side":"buy",//Direction of business buy,sell
                "price":32.233,//Unit Price
                "vol":232,//Number
                "amount":323,//Total
                "ts":1506584998239,//Data generation time
                "ds":'2017-09-10 23:12:21'
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
}
```