
### <span id="26">Request - 24 Market Data on Home Page-</span>

* Request mode:
```json
{"event":"req","params":{"channel":"review"}}
```
* Return an example of data:
```json
{
   event_rep: "rep",
   channel: "review",
   data: {
          bchbtc:  {amount: "115.968833484"close: "0.07956"high: "0.086323"low: "0.079251"open: "0.086323"rose: "-0.07834528"vol: "1393.247"}
          bchusdt: {amount: "416316.164145661", close: "513.56", high: "556.42", low: "510.85", open: "555.71", …}
          btcusdt: {amount: "999341.34124", close: "6450.18", high: "6486.39", low: "6359.63", open: "6435.79", …}
   }
}
```