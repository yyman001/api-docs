### <span id="17">All Transaction Pairs and Accuracy Supported by Query System</span>


1. Interface address:/open/api/common/symbols
2. Interface specification:(get request) query all transaction pairs and accuracy supported by the system

* Parameter: None

Return value:

|field|	Example|	explain|
|------------|--------|---------------|
|code|	0|	 |
|msg|	"suc"|	code>0fail|
|data|	as follows：|symbol Transaction pairs<br>base_coin Base currency<br>count_coin Money of Account<br>price_precision Price Precision Number（0 is a single digit）<br>amount_precision Quantitative precision digits (0 is a single digit)|
```json
{
    "code": "0",
    "msg": "suc",
    "data": [
        {
            "symbol": "ethbtc",
            "count_coin": "btc",
            "amount_precision": 3,
            "base_coin": "eth",
            "price_precision": 8
        },
        {
            "symbol": "ltcbtc",
            "count_coin": "btc",
            "amount_precision": 2,
            "base_coin": "ltc",
            "price_precision": 8
        },
        {
            "symbol": "bchbtc",
            "count_coin": "btc",
            "amount_precision": 3,
            "base_coin": "bch",
            "price_precision": 8
        },
        {
            "symbol": "etcbtc",
            "count_coin": "btc",
            "amount_precision": 2,
            "base_coin": "etc",
            "price_precision": 8
        },
        {
            "symbol": "ltceth",
            "count_coin": "eth",
            "amount_precision": 2,
            "base_coin": "ltc",
            "price_precision": 8
        },
        {
            "symbol": "etceth",
            "count_coin": "eth",
            "amount_precision": 2,
            "base_coin": "etc",
            "price_precision": 8
        }
    ]
}
```
