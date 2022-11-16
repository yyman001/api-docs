### <span id="6">Create order</span>


1. Interface address:/open/api/create_order
2. Interface specification:(post Request) Create an order

|parameter|	Fill in type|	Explain|
|------------|--------|-----------------------------|
|side|	Must fill|	Direction of businessBUY、SELL|
|type|	Must fill|	Type of list，1:limit order、2:market order|
|volume| 	Must fill|	Purchase quantity（Polysemy, multiplexing fields）<br>type=1:Represents the quantity of sales and purchases<br>type=2:Buy means the total price，Selling represents the total number<br>Trading restrictions user/me-User information|
|price|	Selective filling|	Authorized unit price：type=2：No need for this parameter|
|symbol|	Must fill|	Market mark，ethbtc|
|fee_is_user_exchange_coin|	Selective filling|	（Redundant fields, ignored）0，When the exchange has the platform currency, this parameter indicates whether to use the platform currency to pay the handling fee, 0 no, 1 yes.|
|api_key|	Must fill|	api_key|
|time|	Must fill|	time stamp|
|sign|	Must fill|	autograph|

Return value:

| field | Example            | explain                                |
| ----- | ------------------ | -------------------------------------- |
| code  | 0                  |                                        |
| data  | {"order_id":34343} | Successful return to the transactionID |
| msg   | "suc"              | code>0fail                             |

| Virtual Currency Number | xxx-cny（xxx101） | xxx-btc（xxx201） |
| ----------------------- | ----------------- | ----------------- |
| bcc                     | bcccny            | bccbtc            |
| btc                     | btccny            | -                 |
| etc                     | etccny            | etcbtc            |
| eth                     | ethcny            | ethbtc            |
| ltc                     | ltccny            | ltcbtc            |

---s