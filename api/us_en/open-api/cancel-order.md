###  <span id="4">Cancellation of the order</span>

1. Interface address:/open/api/cancel_order
2. Interface specification:(post Request) Cancellation of the Power of Attorney

|parameter|	Fill in type|	Explain|
|------------|--------|-----------------------------|
|order_id|	Must fill|	OrderID|
|symbol|	Must fill|	Market mark，ethbtc，See below for details|
|api_key|	Must fill|	api_key|
|time|	Must fill|	time stamp|
|sign|	Must fill|	autograph|

Return value:

|field|	Example|	explain|
|------------|--------|------------------|
|code	|0	 |
|msg|	"suc"|	code>0fail|
|data|	“”|

|Virtual Currency Number|xxx-cny（xxx101）|xxx-btc（xxx201）|
|------------|--------|----------|
|btc|	btccny|	-|
|eth|	ethcny|	ethbtc|
|ltc|	ltccny|	ltcbtc|
|bcc|	bcccny|	bccbtc|
|etc|	etccny|	etcbtc|
