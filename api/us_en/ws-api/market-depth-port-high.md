###  Subscription - Deep Port (High Frequency)


* request:
```json
{"event":"sub","params":{"channel":"market_$base$quote_depth_step[0-2]","cb_id":"custom","asks":150,"bids":150}}
```
* Return to subscription status once:
```json
{"event_rep":"subed","channel":"market_$base$quote_depth_step[0-2]","cb_id":"Please Return by the Way You Came","asks":150,"bids":150,"ts":1506584998239,"status":"ok"}
```

* Note: The first successful subscription will immediately return a full amount of data, and the server will regularly push a full amount of data to the front-end to avoid data problems

* Full quantity: the front end directly replaces the original disk outlet
```json
{
    "channel":"market_$base$quote_depth_step[0-2]",//$base$quoteExpressbtckrwetc.,Depth has three dimensions，0、1、2
    "ts":1506584998239,//Request time
    "tick":{
        "asks":[//Selling
            [22112.22,0.9332],
            [22112.21,0.2],
        ],
        "buys":[//Bid
            [22111.22,0.9332],
            [22111.21,0.2],
        ]
    }
}
```

* Note: The front end of incremental inventory information only needs to replace the quantity corresponding to the price， volume=Delete at 0 o'clock， priceWith the original opening of a price segment price Equal-time updatevolume,  Direct addition of new price

* Direct addition of new price
```json
{
    "channel":"market_$base$quote_depth_step[0-2]",//$base$quoteExpressbtckrwetc.,Depth has 3 dimensions，0、1、2
    "ts":1506584998239,//Request time
    "tick":{
        "side": "asks", Trading Direction  asks：Selling  buys: Bid  
        "price" : 133.55,  A price segment corresponding to the opening
        "volume" : 44.22   Quantity corresponding to price segment
    }
}
```