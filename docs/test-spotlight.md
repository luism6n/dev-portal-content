---
title: "Test!"
slug: "test-spotlight"
hidden: false
createdAt: "2022-10-20T17:08:52.219Z"
updatedAt: "2022-10-21T14:33:45.242Z"
excerpt: "Insert a synopsis of your article here"
---

<CH.Spotlight>

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

## Step 1 - Simulate a cart

The very first thing that you should do is to check if your store is able to fulfill the cart. A simulation request is how your system will know which delivery and payment options are available for a given combination of items in a cart.

In order to do so, use the [Cart simulation](https://developers.vtex.com/docs/api-reference/checkout-api#post-/api/checkout/pub/orderForms/simulation) API request.

From the response content, you will be mostly using the information in `items`, `logisticsInfo` and `paymentData`. More information about each of them will be provided in the next steps.

<CH.Code>

```shell Shell
```

```python Python
```

```js Node.js
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

---

## Step 3 - Assemble a cart

Assembling a cart from an API point of view means getting all order information into the appropriate data structure, the [orderForm](https://developers.vtex.com/docs/guides/orderform-fields).

An [orderForm](https://developers.vtex.com/docs/guides/orderform-fields) may include many elements, but for a simple order, we can focus on the main five.

> ℹ️️ Note that we are assembling this data structure to be sent as the request body in the next step. Below, we discuss these sections briefly, but you can learn more about each field in the [Place order API request documentation.](https://developers.vtex.com/docs/api-reference/checkout-api#put-/api/checkout/pub/orders)

```json Response
"items": [],
"clientProfileData": {},
"shippingData": {
    "address": {},
    "logisticsInfo": []
},
"paymentData": {}
```

---

### items

This is the core of your order, an array that contains all data pertinent to the SKUs being purchased.

Obtain the necessary information from the `items` array in the cart simulation response from the first step of this tutorial.

Then, build a block with the following structure.

> ℹ️️ For this example, we are considering a single item in the cart. To learn more and explore more complex examples see the [Place order API request documentation.](https://developers.vtex.com/docs/api-reference/checkout-api#put-/api/checkout/pub/orders)

```json Response focus=1:8
"items": [
    {
        "id": "1",
        "quantity": 1,
        "seller": "1",
        "price": 10000
    }
],
"clientProfileData": {},
"shippingData": {
    "address": {},
    "logisticsInfo": []
},
"paymentData": {}
```

---

### clientProfileData: New clients

This object contains information about the shopper. Consider this format for new customers willing to create an account.

```json Response focus=2:15
"items": [],
"clientProfileData": {
    "email": "email@domain.com",
    "firstName": "Testing",
    "lastName": "VTEX",
    "document": "078051120",
    "documentType": "ssn",
    "phone": "1234567890",
    "corporateName": null,
    "tradeName": null,
    "corporateDocument": null,
    "stateInscription": null,
    "corporatePhone": null,
    "isCorporate": false
},
"shippingData": {
    "address": {},
    "logisticsInfo": []
},
"paymentData": {}
```

---

### clientProfileData: Existing clients

For [customers already in your database](https://developers.vtex.com/docs/guides/create-a-regular-order-using-the-checkout-api#2-check-if-a-customer-already-exists-in-your-database), sending only the email address is enough to register the order to the shopper’s existing account.

>❗ If the shopper exists in you database but is not logged in, sending other profile information along with the email will cause the platform to fail placing the order. This happens because this action is interpreted as an attempt to edit profile data, which is not possible unless the customer is logged in to the store.

```json Response focus=2:4
"items": [],
"clientProfileData": {
    "email": "email@domain.com"
},
"shippingData": {
    "address": {},
    "logisticsInfo": []
},
"paymentData": {}
```

---

### shippingData.address

This object contains shipping address information.

```json Response focus=3:18
"items": [],
"clientProfileData": {},
"shippingData": {
    "address": {
        "addressType": "residential",
        "receiverName": "Testing VTEX",
        "postalCode": "33301",
        "city": "Fort Lauderdale",
        "state": "FL",
        "country": "USA",
        "street": "110 East Broward Blvd",
        "number": null,
        "neighborhood": null,
        "complement": "Suite 1700",
        "reference": null,
        "geoCoordinates": []
    }
},
"paymentData": {}
```

---

### shippingData.address: Existing clients

For [customers already in your data base](https://developers.vtex.com/docs/guides/create-a-regular-order-using-the-checkout-api#2-check-if-a-customer-already-exists-in-your-database), it is enough to send this object only with an `addressId`, which you may get from [step two](https://developers.vtex.com/docs/guides/create-a-regular-order-using-the-checkout-api#2-check-if-a-customer-already-exists-in-your-database).

```json Response focus=3:7
"items": [],
"clientProfileData": {},
"shippingAddress": {
    "address": {
        "addressId": "666c2e830bd9474ab6f6cc53fb6dd2d2"
    }
},
"paymentData": {}
```

---

### shippingData.logisticsInfo

This is an array that contains logistics information for each item in the `items` array, including the selected delivery option and freight cost.

The `selectedSla` field indicates the selected delivery option. You can choose an `id` value, from among the options in the `slas` array obtained in the [Cart simulation step](https://developers.vtex.com/docs/guides/create-a-regular-order-using-the-checkout-api#1-simulate-a-cart). The corresponding `price` can also be found in the simulation response data, in the same object.

The `logisticsInfo` array should contain a number of objects equal to the number of objects in the `items` array. The `itemIndex` of a `logisticsInfo` object indicates to which item of the array `items` that information is referring. The object referring to the first item in `items` will contain an `itemIndex` of `0` and so on.

> ℹ️️ For this example, we are considering a single item in the cart. To learn more and explore more complex examples see the [Place order API request documentation.](https://developers.vtex.com/docs/api-reference/checkout-api#put-/api/checkout/pub/orders)

```json Response focus=3:11
"items": [],
"clientProfileData": {},
"shippingData": {
    "address": {},
    "logisticsInfo": [
        {
        "itemIndex": 0,
        "selectedSla": "Regular",
        "price": 100
        }
    ]
},
"paymentData": {}
```

---

### paymentData

This object informs the payment method and installment options (if available) selected for the order.

Note that the `value` field corresponds to the full value to be payed by the shopper, whereas the `referenceValue` is the base number over which interests apply. If no interest apply to the order, they should be equal.

> ℹ️️ For this example, we are considering a single payment method, with a single installment and no interest. To learn more and explore more complex examples see the [Place order API request documentation.](https://developers.vtex.com/docs/api-reference/checkout-api#put-/api/checkout/pub/orders)

Use the options and information from the [simulation](https://developers.vtex.com/docs/guides/create-a-regular-order-using-the-checkout-api#1-simulate-a-cart) response data to assemble your own `paymentData`.

```json Response focus=7:16
"items": [],
"clientProfileData": {},
"shippingData": {
    "address": {},
    "logisticsInfo": []
},
"paymentData": {
    "payments": [
        {
            "paymentSystem": "1",
            "referenceValue": 10100,
            "value": 10100,
            "installments": 1
        }
    ]
}
```

---

## Step 4 - Review the `orderForm`

When you are done consolidating all of your shopping cart information, your `orderForm` should look something like this.

```json Response
{
    "items": [
        {
            "id": "1",
            "quantity": 1,
            "seller": "1",
            "price": 10000
        }
    ],
    "clientProfileData": {
        "email": "email@domain.com",
        "firstName": "Testing",
        "lastName": "VTEX",
        "document": "078051120",
        "documentType": "ssn",
        "phone": "1234567890",
        "corporateName": null,
        "tradeName": null,
        "corporateDocument": null,
        "stateInscription": null,
        "corporatePhone": null,
        "isCorporate": false
    },
    "shippingData": {
        "address": {
            "addressType": "residential",
            "receiverName": "Testing VTEX",
            "postalCode": "33301",
            "city": "Fort Lauderdale",
            "state": "FL",
            "country": "USA",
            "street": "110 East Broward Blvd",
            "number": null,
            "neighborhood": null,
            "complement": "Suite 1700",
            "reference": null,
            "geoCoordinates": []
        },
        "logisticsInfo": [
            {
            "itemIndex": 0,
            "selectedSla": "Regular",
            "price": 100            
            }
        ]
    },
    "paymentData": {
        "payments": [
            {
            "paymentSystem": "1",
            "referenceValue": 10100,
            "value": 10100,
            "installments": 1
            }
        ]
    }
}
```

---

### Returning customer

For a returning customer, it may be something like this.

```json Response
{
    "items": [
        {
            "id": "1",
            "quantity": 1,
            "seller": "1",
            "price": 10000
        }
    ],
    "clientProfileData": {
        "email": "email@domain.com"
    },
    "shippingData": {
        "address": {
            "addressId": "666c2e830bd9474ab6f6cc53fb6dd2d2"
        },
        "logisticsInfo": [
            {
            "itemIndex": 0,
            "selectedSla": "Regular",
            "price": 100
            }
        ]
    },
    "paymentData": {
        "payments": [
            {
            "paymentSystem": "1",
            "referenceValue": 10100,
            "value": 10100,
            "installments": 1
            }
        ]
    }
}
```

---

### Pickup delivery

If the delivery method is pickup point, add the information <code>"selectedDeliveryChannel": "pickup-in-point"</code>, as in this example.

> ℹ️️ This exemplifies a fairly simple fictitious shopping cart. The `orderForm` is actually highly customizable. Learn more about all possibilities in the [orderForm documentation.](https://developers.vtex.com/docs/guides/orderform-fields)

```json Response
{
   "logisticsInfo": [
            {
            "itemIndex": 0,
            "selectedSla": "Regular",
            "price": 100,
            "selectedDeliveryChannel": "pickup-in-point"
            }
        ]
    }
```

</CH.Spotlight>


## Checking the result

You should be able to verify your order was in fact placed in the [Order management module](https://help.vtex.com/en/tutorial/orders-list--tutorials_200#) in VTEX Admin.

You can also use the API requests [Get order](https://developers.vtex.com/docs/api-reference/orders-api#get-/api/oms/pvt/orders/-orderId-) and [List orders](https://developers.vtex.com/docs/api-reference/orders-api#get-/api/oms/pvt/orders) for this purpose.
