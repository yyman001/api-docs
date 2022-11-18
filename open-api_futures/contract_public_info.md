## 接口地址:/api/contract_public_info

## 接口说明:(GET请求)公共接口

|参数|	无

返回值:
```json
	{
	    "code":"0",
	    "data":{
	        "market":{
	            "E_BTCUSD":{
	                "baseSymbol":"BTC", //基础币种
	                "contractName":"BitCoin", //合约名称
	                "contractType":0, //0：永续合约 1：定期合约
	                "feeRateMaker":-0.00025, //挂单手续费率
	                "feeRateTaker":0.00075, //吃单手续费率
	                "holdRate":0.005, //维持保证金比例
	                "id":1, //合约ID
	                "leverTypes":"1,2,3,5,10,25,50,100", //可选杠杆倍数
	                "maxLeverageLevel":100, //最大杠杆倍数
	                "maxOrderVolume":10000000, //最大下单张数
	                "minMargin":0.01, //最小资金变动额
	                "minOrderVolume":1, //最小下单张数
	                "pricePrecision":2, //价格精度
	                "quoteSymbol":"USD", //计价币种
	                "settleTime":"2093-02-05 00:00:00", //交割时间
	                "status":1, 1：可下单 2：待交割 3：交割中 4：已交割
	                "symbol":"E_BTCUSD"
	            }
	        },
	        "wsUrl":"wss://ws3.safe606.com/contract-kline-api/ws",
	        "marketSymbol":"E_BTCUSD",
	        "lan":{
	            "defLan":"zh_CN",
	            "lanList":[
	                {
	                    "name":"简体中文",
	                    "id":"zh_CN"
	                },
	                {
	                    "name":"English",
	                    "id":"en_US"
	                },
	                {
	                    "name":"한국어",
	                    "id":"ko_KR"
	                },
	                {
	                    "name":"繁体中文",
	                    "id":"el_GR"
	                },
	                {
	                    "name":"Монгол хэл",
	                    "id":"mn_MN"
	                },
	                {
	                    "name":"русский язык",
	                    "id":"ru_RU"
	                },
	                {
	                    "name":"わご",
	                    "id":"ja_JP"
	                }
	            ]
	        },
	        "coinList":{
	            "btc":{
	                "showPrecision":8
	            }
	        }
	    },
	    "msg":""
	}
```