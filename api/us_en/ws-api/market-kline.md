###  <span id="19">Subscription - K Line Market</span>

* request:
```json
{"event":"sub","params":{"channel":"market_$base$quote_kline_[1min/5min/15min/30min/60min/1day/1week/1month]","cb_id":"custom"}}
```
* Return to subscription status once:
```json
{"event_rep":"subed","channel":"market_$base$quote_kline_[1min/5min/15min/30min/60min/1day/1week/1month]","cb_id":"Please Return by the Way You Came","ts":1506584998239,"status":"ok"}
```
* Continue to return subscription messages:
```json
{
    "channel":"market_$base$quote_kline_[1min/5min/15min/30min/60min/1day/1week/1month]",//Subscription transactions versus market$base$quoteExpressbtckrwetc.

    "ts":1506584998239,//Request time
    "tick":{
        "id":1506602880,//Time scale starting value
        "amount":123.1221,//A turnover
        "vol":1212.12211,//Trading volume
        "open":2233.22,//Opening price
        "close":1221.11,//Closing price
        "high":22322.22,//Highest price
        "low":2321.22//Minimum price
    }
}
```