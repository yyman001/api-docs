### <span id="27">Place orders in batches and withdraw designated orders in batches - V2</span>

1. Interface address:/open/api/mass_replaceV2
2. Interface specification:(postrequest)Place orders in batches and withdraw designated orders in batches

* mass_placeIt's a batch of limited price orders that need to be sent to the system, up to 1000 at a time
* mass_cancelIt's a batch of orders that need to be withdrawn, up to 1000 at a time

|parameter|	Fill in type|	Explain|
|------------|--------|--------------------------------------|
|api_key|	Must fill|	api_key|
|time|	Must fill|	time stamp|
|sign|	Must fill|	autograph|
|symbol|	Must fill|	currency ，example btcusdt|
|mass_cancel|	Selective filling|	[1234,234....] Withdrawal parameters，Orderid|
|mass_place|	Selective filling|	[{side:"BUY",type:"1",volume:"0.01",price:"6400",fee_is_user_exchange_coin:"0"}, {}, …]<br>Meaning：<br>symbol:currency，example btcusdt<br>mass_place:Order parameter。side：direction（Direction of businessBUY、SELL），<br>--------------------------------type：type（1:limit order、2:market order）<br>--------------------------------volume：Purchase quantity（Polysemy，Multiplex field） type=1:Represents the quantity of sales and purchasestype=2:Buy means the total price，Selling represents the total number<br>--------------------------------price：Authorized unit price：type=2：No need for this parameter<br>--------------------------------fee_is_user_exchange_coin：(Redundant fields) When the exchange has a platform currency，This parameter indicates whether to use platform currency to pay handling fee, 0 no, 1 yes.|

Return value:

|field|	Example|	explain|
|------------|--------|---------------|
|code|	0|	 |
|msg|	"suc"|	code>0fail|
|data|	"mass_place": [{"msg": "Success","code": "0","order_id": [504,505]},{"msg": "Order cancellation failed","code": "8","order_id": [504,505]}]<br>"mass_cancel": [{"msg": "Success","code": "0","order_id": [572,573,574,626,629]}]|Order return：Orderid，Status code，Success or Failure Information。<br>Withdrawal of returns：Orderid，Status code，c<br>0Express success。|
