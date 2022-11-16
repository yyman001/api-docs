###  <span id="18">Get user assets and recharge records</span>


1. Interface address:/open/api/user_balance_info
2. Interface Description:(postRequest) Get user assets and recharge records

| parameter     | Fill in type      | Explain                                                                  |
| ------------- | ----------------- | ------------------------------------------------------------------------ |
| api_key       | Must fill         | api_key                                                                  |
| email         | Selective filling | email                                                                    |
| mobile_number | Selective filling | Inquiry user number, mobile phone number or mailbox                      |
| sign          | Must fill         | autograph                                                                |
| time          | Must fill         | time stamp                                                               |
| uid           | Selective filling | useruid（useruid,mobile_number,emailOne of the three must be filled in） |

Return value:

|field|	Example|	explain|
|------------|--------|--------------------------------------------|
|code|	0|“0” - > Success<br>“100004” ->Illegal parameters<br>“100005” -> Signature error<br>“100007” -> illegalIP<br>"110032" -> Users do not have query privileges<br>“110020” -> The user to query does not exist|
|msg|	"suc"|	code>0fail|
|data|	as follows：|balance_info Asset information in various currencies<br>deposit_list Filling Pipeline Information|


```json
{
"balance_info":[
    {
        "symbol":"BTC",
        "balance":124.12
    },...
],
"deposit_list":[
    {
        "uid":17203,
        "symbol":"BTC",
        "fee":0.00005,
        "amount":12.02,
        "created_at":"2018-11-14 15:37:51"
    },...
]
}
```
