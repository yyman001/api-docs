###  <span id="12">Search the depth of buying and selling</span>


1. Interface address:/open/api/market_dept
2. Interface specification:(getrequest)Search the depth of buying and selling

* This interface does not perform signature verification

| parameter | Fill in type | Explain                                                                             |
| --------- | ------------ | ----------------------------------------------------------------------------------- |
| symbol    | Must fill    | Market mark，ethbtc，See below for details                                          |
| type      | Must fill    | Depth type，step0, step1, step2（Merger depth0-2）；step0time，The highest accuracy |

Return value:

| field | Example      | explain    |
| ----- | ------------ | ---------- |
| code  | 0            |            |
| data  | as follows： |            |
| msg   | "suc"        | code>0fail |
```json
{  
    "tick":{
        "asks":[//Selling
            {22112.22,0.9332},
            {22112.21,0.2},
            {22112.21,0.2},
            {22112.21,0.2},
            {22112.21,0.2},
        ],
        "bids":[//Bid
            {22111.22,0.9332},
            {22111.21,0.2},
            {22112.21,0.2},
            {22112.21,0.2},
            {22112.21,0.2},
        ]
    }
}
```
