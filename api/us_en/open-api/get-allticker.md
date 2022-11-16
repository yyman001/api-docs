###  <span id="7">Get all trading pairs quotations on the market</span>
1. Interface address:/open/api/get_allticker
2. Interface specification:(get Request) Get all trading pairs quotations on the market 

* This interface does not perform signature verification
* Parameter: None

|field|	Example|	explain|
|------------|--------|-----------------------------|
|code|	0|	 
|msg|	"suc"|	code>0fail|
|data|	as follows：|Return Value Description<br>date: Server time when data is returned <br>symbol: Transaction pairs（Transaction pairs1(base)Abbreviation_Transaction pairs2(quote)Abbreviation） <br>buy: Buy one price <br>high: Highest price <br>last: Latest Transaction Price <br>low: Minimum price <br>sell: Selling price <br>vol: Volume (latest 24 hours)<br>rose:Ups and downs|
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

---