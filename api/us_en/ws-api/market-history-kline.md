### Request-K Line History Data

* Increase request parameters endIdx，pageSize（Up to 300, default 300 data）,If endIdx is empty, the last 300 historical data are returned

* request:
```json
{"event":"req","params":{"channel":"market_$base$quote_kline_[1min/5min/15min/30min/60min/1day/1week/1month]","cb_id":"custom","since":"1506602880"}}//since The default is to return the latest 300, a return value greater than since for up to 1 hours of data, since has strong check, not earlier than the current 1 hours to 59 since```
* Return a historical data:
```
```json
{
    "event_rep":"rep","channel":"market_$base$quote_kline_[1min/5min/15min/30min/60min/1day/1week/1month]","cb_id":"Please Return by the Way You Came",
    "since":"1506602880",//since Return the latest 300 items by default, return the maximum 1 hour data larger than since when it has value, and since has strong check, not earlier than the current 1 hour.
    "ts":1506584998239,//Request time
    "data":[//300 article
        {
            "id":1506602880,//Time scale starting value
            "amount":123.1221,//A turnover
            "vol":1212.12211,//Trading volume
            "open":2233.22,//Opening price
            "close":1221.11,//Closing price
            "high":22322.22,//Highest price
            "low":2321.22//Minimum price
        },
        {
            "id":1506602880,//Time scale starting value
            "amount":123.1221,//A turnover
            "vol":1212.12211,//Trading volume
            "open":2233.22,//Opening price
            "close":1221.11,//Closing price
            "high":22322.22,//Highest price
            "low":2321.22//Minimum price
        }
    ]
}
```