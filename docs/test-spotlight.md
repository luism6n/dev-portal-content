
---
title: "Test!"
slug: "test-spotlight"
hidden: false
createdAt: "2022-10-20T17:08:52.219Z"
updatedAt: "2022-10-21T14:33:45.242Z"
excerpt: "Insert a synopsis of your article here"
---

<CH.Spotlight>

## Step 1 - Simulate a cart

The very first thing that you should do is to check if your store is able to fulfill the cart. A simulation request is how your system will know which delivery and payment options are available for a given combination of items in a cart.

In order to do so, use the [Cart simulation](https://developers.vtex.com/docs/api-reference/checkout-api#post-/api/checkout/pub/orderForms/simulation) API request.

From the response content, you will be mostly using the information in `items`, `logisticsInfo` and `paymentData`. More information about each of them will be provided in the next steps.

<CH.Code>

```shell Shell
curl --request post \
 --url 'https://{accountname}.{environment}.com.br/api/checkout/pub/orderForms/simulation?RnbBehavior=0' \
 --header 'Accept: application/json' \
 --header 'Content-Type: application/json' \
 --header 'X-VTEX-API-AppKey: ' \
 --header 'X-VTEX-API-AppToken: ' \
 --data '{"items":[{"id":"1","quantity":1,"seller":"1"}],"country":"BRA","postalCode":"12345-000","geoCoordinates":[-47.924747467041016]}'
```

```python Python
import http.client

conn = http.client.HTTPSConnection("%7Baccountname%7D.%7Benvironment%7D.com.br")

payload = "{\"items\":[{\"id\":\"1\",\"quantity\":1,\"seller\":\"1\"}],\"country\":\"BRA\",\"postalCode\":\"12345-000\",\"geoCoordinates\":[-47.924747467041016]}"

headers = {
    'Accept': "application/json",
    'Content-Type': "application/json",
    'X-VTEX-API-AppKey': "",
    'X-VTEX-API-AppToken': ""
    }

conn.request("post", "/api/checkout/pub/orderForms/simulation?RnbBehavior=0", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```js Node.js
const http = require("https");

const options = {
 "method": "post",
 "hostname": "%7Baccountname%7D.%7Benvironment%7D.com.br",
 "port": null,
 "path": "/api/checkout/pub/orderForms/simulation?RnbBehavior=0",
 "headers": {
  "Accept": "application/json",
  "Content-Type": "application/json",
  "X-VTEX-API-AppKey": "",
  "X-VTEX-API-AppToken": ""
 }
};

const req = http.request(options, function (res) {
 const chunks = [];

 res.on("data", function (chunk) {
  chunks.push(chunk);
 });

 res.on("end", function () {
  const body = Buffer.concat(chunks);
  console.log(body.toString());
 });
});

req.write(JSON.stringify({
  items: [{id: '1', quantity: 1, seller: '1'}],
  country: 'BRA',
  postalCode: '12345-000',
  geoCoordinates: [-47.924747467041016]
}));
req.end();
```

</CH.Code>

---

## Step 2 - Check if a customer already exists in your database

Whenever you attempt to place an order, you must provide an email address to identify the shopper. Typically, once an order gets successfully placed, the provided email address is assigned to a client profile on your store.

Therefore, it is a good idea to verify if a given email address is already linked to a customer of yours, so you can avoid any permission issues and retrieve any stored information.

To check an email address for existing profiles, just send use the [Get client by email](https://developers.vtex.com/docs/api-reference/checkout-api#get-/api/checkout/pub/profiles) API request.

If the response to this request returns any content, it means that you already have this customer’s information on your store’s data base. In this case, you can use that information in the next steps without having to ask the shopper to provide it to you again.

<CH.Code>

```shell Shell
curl --request get \
 --url 'https://{accountname}.{environment}.com.br/api/checkout/pub/profiles?ensureComplete=true' \
 --header 'Accept: application/json' \
 --header 'Content-Type: application/json' \
 --header 'X-VTEX-API-AppKey: ' \
 --header 'X-VTEX-API-AppToken: '
```

```python Python
import http.client

conn = http.client.HTTPSConnection("%7Baccountname%7D.%7Benvironment%7D.com.br")

headers = {
    'Accept': "application/json",
    'Content-Type': "application/json",
    'X-VTEX-API-AppKey': "",
    'X-VTEX-API-AppToken': ""
    }

conn.request("get", "/api/checkout/pub/profiles?ensureComplete=true", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```js Node.js
const http = require("https");

const options = {
 "method": "get",
 "hostname": "%7Baccountname%7D.%7Benvironment%7D.com.br",
 "port": null,
 "path": "/api/checkout/pub/profiles?ensureComplete=true",
 "headers": {
  "Accept": "application/json",
  "Content-Type": "application/json",
  "X-VTEX-API-AppKey": "",
  "X-VTEX-API-AppToken": ""
 }
};

const req = http.request(options, function (res) {
 const chunks = [];

 res.on("data", function (chunk) {
  chunks.push(chunk);
 });

 res.on("end", function () {
  const body = Buffer.concat(chunks);
  console.log(body.toString());
 });
});

req.end();
```

</CH.Code>

</CH.Spotlight>

## Checking the result

You should be able to verify your order was in fact placed in the [Order management module](https://help.vtex.com/en/tutorial/orders-list--tutorials_200#) in VTEX Admin.

You can also use the API requests [Get order](https://developers.vtex.com/docs/api-reference/orders-api#get-/api/oms/pvt/orders/-orderId-) and [List orders](https://developers.vtex.com/docs/api-reference/orders-api#get-/api/oms/pvt/orders) for this purpose.
