###  Subscription - Deep Port

* request:
```json
{"event":"sub","params":{"channel":"market_$base$quote_depth_step[0-2]","cb_id":"custom","asks":150,"bids":150}}
```
* Return to subscription status once:
```json
{"event_rep":"subed","channel":"market_$base$quote_depth_step[0-2]","cb_id":"Please Return by the Way You Came","asks":150,"bids":150,"ts":1506584998239,"status":"ok"}
```
* Continue to return subscription messages:
```json
{
    "channel":"market_$base$quote_depth_step[0-2]",//$base$quoteRepresents btckrw, etc.,Depth has 3 dimensions，0、1、2
    "ts":1506584998239,//Request time
    "tick":{
        "asks":[//Selling
            [22112.22,0.9332],
            [22112.21,0.2]
        ],
        "buys":[//Bid
            [22111.22,0.9332],
            [22111.21,0.2]
        ]
    }
}
```