### Balance of assets

1. Interface address: /open/api/user/account
2. Interface specification: (get request)Balance of the assets


| parameter | Fill in type | Explain    |
| --------- | ------------ | ---------- |
| api_key   | Must fill    | api_key    |
| sign      | Must fill    | autograph  |
| time      | Must fill    | time stamp |

Return value:

| field | Example | explain    |
| ----- | ------- | ---------- |
| code  | 0       |            |
| data  |  {<br>"total_asset":432323.23,<br>"coin_list":[<br>{"coin":"btc","normal":32323.233,"locked":32323.233,"btcValuatin":112.33},<br>{"coin":"ltc","normal":32323.233,"locked":32323.233,"btcValuatin":112.33},<br>{"coin":"bch","normal":32323.233,"locked":32323.233,"btcValuatin":112.33},<br>]<br>}<br>|total_asset:total assets<br>normal:Balance account<br>locked：Frozen accounts<br>btcValuatin：BTCValuation       |            |
| msg   | "suc"   | code>0fail |
