#  Exchange-official-API-docs

#### Official Documentation for the Exchange APIs and Streams([简体中文版文档](https://github.com/CoinUpGlobal/api-docs/blob/master/api/zh_cn/api_doc_cn.md))
- [Introduction](#Introduction)
- [Getting Started](#startToUse)
- [Encrypted Verification of API](#a1)
    - [Generate an API Key](#a2)
    - [Initiate a Request](#a3)
    - [Signature](#a4)
    - Select timestamp
    - [Request Process](#a6)
        - [Request](#a7)
        - [Pagination](#a8)
    - [Standards and Specification](#a9)
        - [Timestamp](#b1)
        - [For example](#b2)
        - [Numbers](#b3)
        - [Rate Limits REST API](#b4)
- [Spot API Reference](#b5)
  - [open-api]
    - [Api Demo](./open-api/demo.md)
    - [Balance of the assets](./open-api/account.md)
    -	[Acquire full delegation](./open-api/all-order.md)
    -	[Obtain all transaction records](./open-api/all-trade.md)
    -	[Cancellation of the order](./open-api/cancel-order.md)
    -	[Cancellation of all orders of attorney according to currency pair](./open-api/cancel-order-all.md)
    -	[Create order](./open-api/create-order.md)
    -	[Get all trading pairs quotations on the market](./open-api/get-allticker.md)
    -	[Getting K-line data](./open-api/get-records.md)
    -	[Get the current market quotations](./open-api/get-ticker.md)
    -	[Acquisition of Trading Records](./open-api/get-trades.md)
    -	[Get the latest transaction price of each pair of currencies](./open-api/market.md)
    -	[Search the depth of buying and selling](./open-api/market-dept.md)
    -	[Place orders in batches and withdraw designated orders in batches(No recommendation, recommend v2)](./open-api/mass-replace.md)
    -	[Place orders in batches and withdraw designated orders in batches - V2](./open-api/mass-replaceV2.md)
    -	[Get the current delegation](./open-api/new-order.md)
    -	[Obtain order details](./open-api/order-info.md)
    -	[All Transaction Pairs and Accuracy Supported by Query System](./open-api/symbols.md)
    -	[Get user assets and recharge records](./open-api/user-balance-info.md)
  - [ws-api]
    -   [Java-Demo](./ws-api/demo.md)
    -   [Subscription - K Line Market](./ws-api/market-kline.md)
    -   [Subscription - market quotations in the last 24 hours](./ws-api/market-ticker.md)
    -   [Subscription - Deep Port (High Frequency)](./ws-api/market-depth-port-high.md)
    -   [Subscription - Deep Port](./ws-api/market-depth-port.md)
    -   [Subscription-Real-time Transaction Information](./ws-api/market-trade-ticker.md)
    -   [Request-K Line History Data](./ws-api/market-history-kline.md)
    -   [Request-transaction history data](./ws-api/market-transaction-history-data.md)
    -   [Request - 24 Market Data on Home Page](./ws-api/market-data-24-hours-on-home-page.md)
---


# <span id="Introduction">Introduction</span>

Welcome to [Exchange](https://www.Exchange.com/index) API document for developers.

This file provides the related API application introduction. Open-API includes the port to acquire balance, all orders ,and all transaction record. Ws-API response for the port of K line functions.

---

# <span id="startToUse">Getting Started</span>
REST, a.k.a Respresntational State Transfer, is an architectural style that defines a set of constraints and properties based on HTTP. REST is known for its clear structure, readability, standardization and scalability. Its advantages are as follows:

- Each URL represents one web resource in RESTful architecture.
- Acting as a representation of resources between client and server.
- Client is enabled to operate server-side resources with 4 HTTP requests - representational state transfer.

Developers are recommended to use REST API to proceed spot trading and withdrawals.

---


# <span id="a1">Encrypted Verification of API</span>

## <span id="a2">Generate an API Key</span>

Before signing any request, you must generate an API key via [Exchange’s official website ](https://www.Exchange.com/index)【User Center】-【API】. After generating the key, there are three things you must bear in mind:

- API Key
 
- Secret Key
 

API Key and Secret are randomly generated and provided, Passphrase is set by user.
## <span id="a3">Initiate a Request</span>
All REST requests must include the following headings:

- ACCESS-KEY API Key as a string.
- ACCESS-SIGN uses base64-encoded signatures (see Signed Messages).
- ACCESS-TIMESTAMP is the timestamp of your request.header MUST be number of seconds since Unix Epoch in UTC. Decimal values are allowed.
- All requests should contain content like application/x-www-form-urlencoded and be valid JSON.

## <span id="a4">Signature</span>
Generate a string to be signed
    -   [open-api Demo](https://github.com/CoinUpGlobal/api-docs/blob/master/demo/demo.java)
    
1、Sort the parameters in ascending order of their parameter names in lexicographic order

2、Traversing the sorted dictionary, splicing all parameters together in "keyvalue" format (non-null parameters)

3、Use MD5 to treat signature strings

**For example:**

api_key = 1234567

time = 12312312312137

secret_key = 789654

sign=md5(api_key1234567time12312312312137789654)


## <span id="a6">Request Process</span>

The root URL for REST access：``` https://api.Exchange.com ```

###  <span id="a7">Request</span>
All requests are based on Https protocol, contentType in the request header must be uniformly set as: ‘application/x-www-form-urlencoded’.

**Request Process Descriptions**

1、Request parameter: parameter encapsulation based on the port request.

2、Submitting request parameter: submit the encapsulated parameter request to the server via POST/GET/PUT/DELETE or other methods.

3、Server response: the server will first perform a security validation, then send back the requested data to the client in JSON format.

4、Data processing: processing server response data.

**Success**

HTTP status code 200 indicates a successful response and may contain content. If the response contains content, it will appear in the corresponding returned content.

**Common Error Code**

- 400 Bad Request – Invalid request format

- 401 Unauthorized – Invalid API Key

- 403 Forbidden – You do not have access to the requested resource

- 404 Not Found

- 429 Too Many Requests

- 500 Internal Server Error

We had a problem with our server

###  <span  id="a8">Pagination</span>

All REST requests that return datasets use cursor-based pagination.

Cursor-based pagination allows results to be obtained before and after the current page of the result and is well suited for real-time data. The subsequent requests can specify the direction of the requested data based on the current returned results, before and/or after it. The before and after cursors can be used by the response headers CB-BEFORE and CB-AFTER.

**For example:**

```GET /orders?before=2&limit=30```


## <span id="a9">Standards and Specification</span>

### <span id="b1">Timestamp</span> 
Unless otherwise specified, all timestamps in APIs are returned in microseconds.

The ACCESS-TIMESTAMP header must be the number of seconds since UTC's time Unix Epoch. Decimal values are allowed. Your timestamp must be within 30 seconds of the API service time, otherwise your request will be considered expired and rejected. If you think there is a large time difference between your server and the API server, then we recommend that you use the time point to check the API server time.

###  <span id="b2">For example</span> 
1524801032573

###  <span id="b3">Numbers</span> 
In order to maintain the accuracy of cross-platform, decimal numbers are returned as strings. We suggest that you might be better to convert the number to string when issuing the request to avoid truncation and precision errors. Integers (such as transaction number and sequence) do not need quotation marks.

###  <span id="b4">Rate Limits</span>  
When a rate limit is exceeded, a status of 429 Too Many Requests will be returned.

REST API

- Public interface: We limit the invocation of public interface via IP: up to 6 requests every 2s.

- Private interface: We limit the invocation of private interface via user ID: up to 6 requests every 2s.

- Special restrictions on specified interfaces are specified.

---

# <span id="b5"> API Reference</span>
