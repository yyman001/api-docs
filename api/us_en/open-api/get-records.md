### <span id="8">Getting K-line data</span>


1. Interface address:/open/api/get_records
2. Interface specification:(get request)Getting K-line data

* This interface does not perform signature verification

| parameter | Fill in type | Explain                                                  |
| --------- | ------------ | -------------------------------------------------------- |
| period    | Must fill    | In minutes，The analogy is 1 in a minute，One day is1440 |
| symbol    | Must fill    | Market mark，bchbtc，See below for details               |

| Virtual Currency Number | xxx-cny | xxx-btc | xxx-usdt |
| ----------------------- | ------- | ------- | -------- |
| bch                     | bcccny  | bchbtc  | bchusdt  |
| btc                     | btccny  | -       | btcusdt  |
| etc                     | etccny  | etcbtc  | etcusdt  |
| eth                     | ethcny  | ethbtc  | ethusdt  |
| ltc                     | ltccny  | ltcbtc  | ltcusdt  |

Return value:

| field | Example      | explain    |
| ----- | ------------ | ---------- |
| code  | 0            |
| data  | as follows： |
| msg   | "suc"        | code>0fail |

```json
[
        [
            1514445780,  //time stamp
            1.12,        //Opening price
            1.12,        //Highest
            1.12,        //minimum
            1.12,        //Closing price
            0            //volume

        ],
        [
            1514445840,
            1.12,
            1.12,
            1.12,
            1.12,
            0
        ],
        [
            1514445900,
            1.12,
            1.12,
            1.12,
            1.12,
            0
        ]
]
```
