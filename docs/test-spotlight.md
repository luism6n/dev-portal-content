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

---

```json Response
{
  "items": [
    {
      "id": "1",
      "requestIndex": 0,
      "quantity": 1,
      "seller": "1",
      "sellerChain": [
        "1"
      ],
      "tax": 0,
      "priceValidUntil": "2023-07-12T11:49:01Z",
      "price": 9999,
      "listPrice": 9999,
      "rewardValue": 0,
      "sellingPrice": 2999700,
      "offerings": [],
      "priceTags": [
        {
          "name": "DISCOUNT@MANUALPRICE",
          "value": -5000,
          "rawValue": -50,
          "isPercentual": false,
          "identifier": "1234abc-5678b-1234c"
        }
      ],
      "measurementUnit": "un",
      "unitMultiplier": 300,
      "parentItemIndex": null,
      "parentAssemblyBinding": null,
      "availability": "available",
      "priceDefinition": {
        "calculatedSellingPrice": 2999700,
        "total": 2999700,
        "sellingPrices": [
          {
            "value": 2999700,
            "quantity": 1
          }
        ]
      }
    }
  ],
  "ratesAndBenefitsData": {
    "rateAndBenefitsIdentifiers": [],
    "teaser": []
  },
  "paymentData": {
    "installmentOptions": [
      {
        "paymentSystem": "2",
        "bin": null,
        "paymentName": "Visa",
        "paymentGroupName": "creditCardPaymentGroup",
        "value": 2999700,
        "installments": [
          {
            "count": 1,
            "hasInterestRate": false,
            "interestRate": 0,
            "value": 2999700,
            "total": 2999700,
            "sellerMerchantInstallments": [
              {
                "id": "LOJADOBRENO",
                "count": 1,
                "hasInterestRate": false,
                "interestRate": 0,
                "value": 2999700,
                "total": 2999700
              }
            ]
          }
        ]
      },
      {
        "paymentSystem": "6",
        "bin": null,
        "paymentName": "Boleto Bancário",
        "paymentGroupName": "bankInvoicePaymentGroup",
        "value": 2999700,
        "installments": [
          {
            "count": 1,
            "hasInterestRate": false,
            "interestRate": 0,
            "value": 2999700,
            "total": 2999700,
            "sellerMerchantInstallments": [
              {
                "id": "LOJADOBRENO",
                "count": 1,
                "hasInterestRate": false,
                "interestRate": 0,
                "value": 2999700,
                "total": 2999700
              }
            ]
          }
        ]
      },
      {
        "paymentSystem": "127",
        "bin": null,
        "paymentName": "MercadoPagoPro",
        "paymentGroupName": "MercadoPagoProPaymentGroup",
        "value": 2999700,
        "installments": [
          {
            "count": 1,
            "hasInterestRate": false,
            "interestRate": 0,
            "value": 2999700,
            "total": 2999700,
            "sellerMerchantInstallments": [
              {
                "id": "LOJADOBRENO",
                "count": 1,
                "hasInterestRate": false,
                "interestRate": 0,
                "value": 2999700,
                "total": 2999700
              }
            ]
          }
        ]
      },
      {
        "paymentSystem": "202",
        "bin": null,
        "paymentName": "Dinheiro",
        "paymentGroupName": "custom202PaymentGroupPaymentGroup",
        "value": 2999700,
        "installments": [
          {
            "count": 1,
            "hasInterestRate": false,
            "interestRate": 0,
            "value": 2999700,
            "total": 2999700,
            "sellerMerchantInstallments": [
              {
                "id": "LOJADOBRENO",
                "count": 1,
                "hasInterestRate": false,
                "interestRate": 0,
                "value": 2999700,
                "total": 2999700
              }
            ]
          }
        ]
      }
    ],
    "paymentSystems": [
      {
        "id": 202,
        "name": "Dinheiro",
        "groupName": "custom202PaymentGroupPaymentGroup",
        "validator": null,
        "stringId": "202",
        "template": "custom202PaymentGroupPaymentGroup-template",
        "requiresDocument": false,
        "displayDocument": false,
        "isCustom": true,
        "description": "",
        "requiresAuthentication": false,
        "dueDate": "2022-07-22T11:39:36.37197Z",
        "availablePayments": null
      },
      {
        "id": 6,
        "name": "Boleto Bancário",
        "groupName": "bankInvoicePaymentGroup",
        "validator": null,
        "stringId": "6",
        "template": "bankInvoicePaymentGroup-template",
        "requiresDocument": false,
        "displayDocument": false,
        "isCustom": false,
        "description": "",
        "requiresAuthentication": false,
        "dueDate": "2022-07-19T11:39:36.37197Z",
        "availablePayments": null
      },
      {
        "id": 2,
        "name": "Visa",
        "groupName": "creditCardPaymentGroup",
        "validator": null,
        "stringId": "2",
        "template": "creditCardPaymentGroup-template",
        "requiresDocument": false,
        "displayDocument": false,
        "isCustom": false,
        "description": "",
        "requiresAuthentication": false,
        "dueDate": "2022-07-19T11:39:36.37197Z",
        "availablePayments": null
      },
      {
        "id": 127,
        "name": "MercadoPagoPro",
        "groupName": "MercadoPagoProPaymentGroup",
        "validator": null,
        "stringId": "127",
        "template": "MercadoPagoProPaymentGroup-template",
        "requiresDocument": false,
        "displayDocument": false,
        "isCustom": false,
        "description": "",
        "requiresAuthentication": false,
        "dueDate": "2022-07-19T11:39:36.37197Z",
        "availablePayments": null
      }
    ],
    "payments": [],
    "giftCards": [],
    "giftCardMessages": [],
    "availableAccounts": [],
    "availableTokens": [],
    "availableAssociations": {}
  },
  "selectableGifts": [],
  "marketingData": {
    "utmSource": "app",
    "utmMedium": "CPC",
    "utmCampaign": "Black friday",
    "utmipage": "true",
    "utmiPart": "true",
    "utmiCampaign": "true",
    "coupon": null,
    "marketingTags": [
      "tag1",
      "tag2"
    ]
  },
  "country": "BRA",
  "postalCode": "12345-000",
  "geoCoordinates": [
    -47.924747467041016,
    -15.832582473754883
  ],
  "logisticsInfo": [
    {
      "itemIndex": 0,
      "addressId": null,
      "selectedSla": null,
      "selectedDeliveryChannel": null,
      "quantity": 1,
      "shipsTo": [
        "BRA"
      ],
      "slas": [
        {
          "id": "Normal",
          "deliveryChannel": "delivery",
          "name": "Normal",
          "deliveryIds": [
            {
              "courierId": "1",
              "warehouseId": "1_1",
              "dockId": "1",
              "courierName": "Transportadora",
              "quantity": 1,
              "kitItemDetails": []
            }
          ],
          "shippingEstimate": "3bd",
          "shippingEstimateDate": null,
          "lockTTL": "10d",
          "availableDeliveryWindows": {
            "startDateUtc": "2017-03-27T00:00:00+00:00",
            "endDateUtc": "2017-03-27T00:00:00+00:00",
            "price": 0,
            "lisPrice": 0,
            "tax": 0
          },
          "deliveryWindow": {
            "startDateUtc": "2014-04-21T09:00:00+00:00",
            "endDateUtc": "2014-04-21T12:00:00+00:00",
            "price": 0,
            "listprice": 1000,
            "tax": 0
          },
          "price": 1500,
          "listPrice": 1500,
          "tax": 0,
          "pickupStoreInfo": {
            "isPickupStore": false,
            "friendlyName": null,
            "address": null,
            "additionalInfo": null,
            "dockId": null
          },
          "pickupPointId": null,
          "pickupDistance": 0,
          "polygonName": null,
          "transitTime": "3bd"
        }
      ],
      "deliveryChannels": [
        {
          "id": "pickup-in-point"
        },
        {
          "id": "delivery"
        }
      ]
    }
  ],
  "messages": [],
  "purchaseConditions": {
    "itemPurchaseConditions": [
      {
        "id": "1",
        "seller": "1",
        "sellerChain": [
          "1"
        ],
        "slas": [
          {
            "id": "Normal",
            "deliveryChannel": "delivery",
            "name": "Normal",
            "deliveryIds": [
              {
                "courierId": "1",
                "warehouseId": "1_1",
                "dockId": "1",
                "courierName": "Transportadora",
                "quantity": 1,
                "kitItemDetails": []
              }
            ],
            "shippingEstimate": "3bd",
            "shippingEstimateDate": null,
            "lockTTL": "10d",
            "availableDeliveryWindows": {
              "startDateUtc": "2017-03-27T00:00:00+00:00",
              "endDateUtc": "2017-03-27T00:00:00+00:00",
              "price": 0,
              "lisPrice": 0,
              "tax": 0
            },
            "deliveryWindow": {
              "startDateUtc": "2014-04-21T09:00:00+00:00",
              "endDateUtc": "2014-04-21T12:00:00+00:00",
              "price": 0,
              "listprice": 1000,
              "tax": 0
            },
            "price": 1500,
            "listPrice": 1500,
            "tax": 0,
            "pickupStoreInfo": {
              "isPickupStore": false,
              "friendlyName": null,
              "address": null,
              "additionalInfo": null,
              "dockId": null
            },
            "pickupPointId": null,
            "pickupDistance": 0,
            "polygonName": null,
            "transitTime": "3bd"
          }
        ],
        "price": 9999,
        "listPrice": 9999
      }
    ]
  },
  "pickupPoints": [],
  "subscriptionData": null,
  "totals": [
    {
      "id": "Items",
      "name": "Total dos Itens",
      "value": 2999700
    }
  ],
  "itemMetadata": {
    "items": [
      {
        "id": "1",
        "seller": "1",
        "assemblyOptions": [
          {
            "id": "T-Shirt Customization",
            "name": "T-Shirt Customization",
            "required": false,
            "inputValues": {
              "T-Shirt Name": {
                "maximumNumberOfCharacters": 2,
                "domain": [
                  "[]"
                ]
              }
            },
            "composition": null
          }
        ]
      }
    ]
  }
}
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

---

```json Response
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

---

```json Response
{
  "userProfileId": "fb542e51-5488-4c34-8d17-ed8fcf597a94",
  "profileProvider": "VTEX",
  "availableAccounts": [],
  "availableAddresses": [
    {
      "addressType": "residential",
      "receiverName": "Clark Kent",
      "addressId": "666c2e830bd9474ab6f6cc53fb6dd2d2",
      "isDisposable": false,
      "postalCode": "12345-000",
      "city": "Metropolis",
      "state": "NY",
      "country": "USA",
      "street": "My street",
      "number": "123",
      "neighborhood": "My neighborhood",
      "complement": null,
      "reference": null,
      "geoCoordinates": [
        -47.924747467041016,
        -15.832582473754883
      ]
    }
  ],
  "userProfile": {
    "email": "clark.kent@example.com",
    "firstName": "Clark",
    "lastName": "Kent",
    "document": "12345678900",
    "documentType": "cpf",
    "phone": "+556199999999",
    "corporateName": null,
    "tradeName": null,
    "corporateDocument": null,
    "stateInscription": null,
    "corporatePhone": null,
    "isCorporate": false,
    "profileCompleteOnLoading": null,
    "profileErrorOnLoading": null,
    "customerClass": null
  },
  "isComplete": true
}
```

</CH.Code>

</CH.Spotlight>

<CH.Spotlight>

```json Response
{
  "allowManualPrice": boolean,
  "canEditData": boolean,
  "clientPreferencesData": {},
  "clientProfileData": {},
  "commercialConditionData": {},
  "customData": {},
  "giftRegistryData": {},
  "hooksData": {},
  "ignoreProfileData": boolean,
  "isCheckedIn": boolean,
  "itemMetadata": {},
  "items": {},
  "itemsOrdination": {},
  "loggedIn": boolean,
  "marketingData": {},
  "messages": [],
  "openTextField": {},
  "orderFormId": string,
  "paymentData": {},  
  "ratesAndBenefitsData": {},
  "salesChannel": "1",
  "selectableGifts": {},
  "sellers": {},
  "shippingData": {},
  "storeId": {},
  "storePreferencesData": {},
  "totalizers": {},
  "userProfileId": {},
  "userType": {},
  "value": number
}
```

---

## Step 3 - Assemble a cart

Assembling a cart from an API point of view means getting all order information into the appropriate data structure, the [orderForm](https://developers.vtex.com/docs/guides/orderform-fields).

An [orderForm](https://developers.vtex.com/docs/guides/orderform-fields) may include many elements, but for a simple order, we can focus on the main five.

> ℹ️️ Note that we are assembling this data structure to be sent as the request body in the next step. Below, we discuss these sections briefly, but you can learn more about each field in the [Place order API request documentation.](https://developers.vtex.com/docs/api-reference/checkout-api#put-/api/checkout/pub/orders)

```json Response focus=5,13,25,20
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

<CH.Spotlight>


<CH.Code>

```shell Shell
curl --request put \
 --url 'https://{accountname}.{environment}.com.br/api/checkout/pub/orders' \
 --header 'Accept: application/json' \
 --header 'Content-Type: application/json' \
 --header 'X-VTEX-API-AppKey: ' \
 --header 'X-VTEX-API-AppToken: ' \
 --data '{"items":[{"id":"123456789","quantity":1,"seller":"1"}],"clientProfileData":{"email":"string","firstName":"string","lastName":"string","documentType":"string","document":"string","phone":"string","corporateName":"string","tradeName":"string","corporateDocument":"string","stateInscription":"string","corporatePhone":"string","isCorporate":false},"shippingData":{"address":{"addressType":"residential","receiverName":"string","addressId":"string","postalCode":"string","city":"string","state":"string","country":"string","street":"string","number":"string","neighborhood":"string","complement":"string","reference":"string","geoCoordinates":[-47.924747467041016]},"logisticsInfo":[{"itemIndex":0,"selectedSla":"string","lockTTL":"string","shippingEstimate":"string","price":0,"deliveryWindow":{"startDateUtc":"string","endDateUtc":"string","price":0,"lisPrice":0,"tax":0}}],"updateStatus":"string"},"paymentData":{"giftCards":[{"redemptionCode":"HYUO-TEZZ-QFFT-HTFR","value":500,"balance":500,"name":"name-example","id":"1390324156495k195pmab4rall3di","inUse":true,"isSpecialCard":false}],"giftCardMessages":["?"],"paymentSystems":[{"id":2,"name":"Visa","groupName":"creditCardPaymentGroup","validator":{"regex":"^4","mask":"9999 9999 9999 9999","cardCodeRegex":"[^0-9]","cardCodeMask":"999","weights":[0]},"stringId":"string","template":"string","requiresDocument":false,"selected":false,"isCustom":false,"description":"string"}],"payments":[{"accountId":"string","bin":"string","installments":0,"paymentSystem":"string","referenceValue":0,"value":0}],"updateStatus":"string"},"marketingData":{"coupon":"string","utmSource":"string","utmMedium":"string","utmCampaign":"string","utmiPage":"string","utmiPart":"string","utmiCampaign":"string"},"openTextField":"string","salesAssociateData":{"salesAssociateId":"string"}}'
```

```python Python
import http.client

conn = http.client.HTTPSConnection("%7Baccountname%7D.%7Benvironment%7D.com.br")

payload = "{\"items\":[{\"id\":\"123456789\",\"quantity\":1,\"seller\":\"1\"}],\"clientProfileData\":{\"email\":\"string\",\"firstName\":\"string\",\"lastName\":\"string\",\"documentType\":\"string\",\"document\":\"string\",\"phone\":\"string\",\"corporateName\":\"string\",\"tradeName\":\"string\",\"corporateDocument\":\"string\",\"stateInscription\":\"string\",\"corporatePhone\":\"string\",\"isCorporate\":false},\"shippingData\":{\"address\":{\"addressType\":\"residential\",\"receiverName\":\"string\",\"addressId\":\"string\",\"postalCode\":\"string\",\"city\":\"string\",\"state\":\"string\",\"country\":\"string\",\"street\":\"string\",\"number\":\"string\",\"neighborhood\":\"string\",\"complement\":\"string\",\"reference\":\"string\",\"geoCoordinates\":[-47.924747467041016]},\"logisticsInfo\":[{\"itemIndex\":0,\"selectedSla\":\"string\",\"lockTTL\":\"string\",\"shippingEstimate\":\"string\",\"price\":0,\"deliveryWindow\":{\"startDateUtc\":\"string\",\"endDateUtc\":\"string\",\"price\":0,\"lisPrice\":0,\"tax\":0}}],\"updateStatus\":\"string\"},\"paymentData\":{\"giftCards\":[{\"redemptionCode\":\"HYUO-TEZZ-QFFT-HTFR\",\"value\":500,\"balance\":500,\"name\":\"name-example\",\"id\":\"1390324156495k195pmab4rall3di\",\"inUse\":true,\"isSpecialCard\":false}],\"giftCardMessages\":[\"?\"],\"paymentSystems\":[{\"id\":2,\"name\":\"Visa\",\"groupName\":\"creditCardPaymentGroup\",\"validator\":{\"regex\":\"^4\",\"mask\":\"9999 9999 9999 9999\",\"cardCodeRegex\":\"[^0-9]\",\"cardCodeMask\":\"999\",\"weights\":[0]},\"stringId\":\"string\",\"template\":\"string\",\"requiresDocument\":false,\"selected\":false,\"isCustom\":false,\"description\":\"string\"}],\"payments\":[{\"accountId\":\"string\",\"bin\":\"string\",\"installments\":0,\"paymentSystem\":\"string\",\"referenceValue\":0,\"value\":0}],\"updateStatus\":\"string\"},\"marketingData\":{\"coupon\":\"string\",\"utmSource\":\"string\",\"utmMedium\":\"string\",\"utmCampaign\":\"string\",\"utmiPage\":\"string\",\"utmiPart\":\"string\",\"utmiCampaign\":\"string\"},\"openTextField\":\"string\",\"salesAssociateData\":{\"salesAssociateId\":\"string\"}}"

headers = {
    'Accept': "application/json",
    'Content-Type': "application/json",
    'X-VTEX-API-AppKey': "",
    'X-VTEX-API-AppToken': ""
    }

conn.request("put", "/api/checkout/pub/orders", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```js Node.js
const http = require("https");

const options = {
 "method": "put",
 "hostname": "%7Baccountname%7D.%7Benvironment%7D.com.br",
 "port": null,
 "path": "/api/checkout/pub/orders",
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
  items: [{id: '123456789', quantity: 1, seller: '1'}],
  clientProfileData: {
    email: 'string',
    firstName: 'string',
    lastName: 'string',
    documentType: 'string',
    document: 'string',
    phone: 'string',
    corporateName: 'string',
    tradeName: 'string',
    corporateDocument: 'string',
    stateInscription: 'string',
    corporatePhone: 'string',
    isCorporate: false
  },
  shippingData: {
    address: {
      addressType: 'residential',
      receiverName: 'string',
      addressId: 'string',
      postalCode: 'string',
      city: 'string',
      state: 'string',
      country: 'string',
      street: 'string',
      number: 'string',
      neighborhood: 'string',
      complement: 'string',
      reference: 'string',
      geoCoordinates: [-47.924747467041016]
    },
    logisticsInfo: [
      {
        itemIndex: 0,
        selectedSla: 'string',
        lockTTL: 'string',
        shippingEstimate: 'string',
        price: 0,
        deliveryWindow: {startDateUtc: 'string', endDateUtc: 'string', price: 0, lisPrice: 0, tax: 0}
      }
    ],
    updateStatus: 'string'
  },
  paymentData: {
    giftCards: [
      {
        redemptionCode: 'HYUO-TEZZ-QFFT-HTFR',
        value: 500,
        balance: 500,
        name: 'name-example',
        id: '1390324156495k195pmab4rall3di',
        inUse: true,
        isSpecialCard: false
      }
    ],
    giftCardMessages: ['?'],
    paymentSystems: [
      {
        id: 2,
        name: 'Visa',
        groupName: 'creditCardPaymentGroup',
        validator: {
          regex: '^4',
          mask: '9999 9999 9999 9999',
          cardCodeRegex: '[^0-9]',
          cardCodeMask: '999',
          weights: [0]
        },
        stringId: 'string',
        template: 'string',
        requiresDocument: false,
        selected: false,
        isCustom: false,
        description: 'string'
      }
    ],
    payments: [
      {
        accountId: 'string',
        bin: 'string',
        installments: 0,
        paymentSystem: 'string',
        referenceValue: 0,
        value: 0
      }
    ],
    updateStatus: 'string'
  },
  marketingData: {
    coupon: 'string',
    utmSource: 'string',
    utmMedium: 'string',
    utmCampaign: 'string',
    utmiPage: 'string',
    utmiPart: 'string',
    utmiCampaign: 'string'
  },
  openTextField: 'string',
  salesAssociateData: {salesAssociateId: 'string'}
}));
req.end();
```

---

```json Response
{
  "orderForm": null,
  "transactionData": {
    "merchantTransactions": [
      {
        "id": "MYSTORE",
        "transactionId": "296D6D245C17437E823EB77E403FC88D",
        "merchantName": "MYSTORE",
        "payments": [
          {
            "paymentSystem": "6",
            "bin": null,
            "accountId": null,
            "tokenId": null,
            "value": 34390,
            "referenceValue": 34390,
            "giftCardRedemptionCode": null,
            "giftCardProvider": null,
            "giftCardId": null
          }
        ]
      }
    ],
    "receiverUri": "https://mystore.vtexpayments.com.br/split/1146512005522/payments",
    "gatewayCallbackTemplatePath": "/checkout/gatewayCallback/1146512005522/{messageCode}"
  },
  "orders": [
    {
      "orderId": "1146512005522-01",
      "orderGroup": "1146512005522",
      "state": null,
      "isCheckedIn": false,
      "sellerOrderId": "00-1146512005522-01",
      "storeId": null,
      "checkedInPickupPointId": null,
      "value": 34390,
      "items": [
        {
          "uniqueId": "9D6E447B3FF64CEDA33B17C01379C119",
          "id": "2",
          "productId": "2",
          "productRefId": "",
          "refId": "CBC30L",
          "ean": null,
          "name": "Chopp Brahma Claro 30L",
          "skuName": "Chopp Brahma Claro 30L",
          "modalType": null,
          "parentItemIndex": null,
          "parentAssemblyBinding": null,
          "assemblies": [],
          "priceValidUntil": "2022-07-13T18:30:46Z",
          "tax": 0,
          "price": 32890,
          "listPrice": 49900,
          "manualPrice": null,
          "manualPriceAppliedBy": null,
          "sellingPrice": 32890,
          "rewardValue": 0,
          "isGift": false,
          "additionalInfo": {
            "dimension": null,
            "brandName": "Brahma",
            "brandId": "2000000",
            "offeringInfo": null,
            "offeringType": null,
            "offeringTypeId": null
          },
          "preSaleDate": null,
          "productCategoryIds": "/1/",
          "productCategories": {
            "1": "Bebidas"
          },
          "quantity": 1,
          "seller": "1",
          "sellerChain": [
            "1"
          ],
          "imageUrl": "http://mystore.vteximg.com.br/arquivos/ids/155400-55-55/30l_v2.png?v=637303412106100000",
          "detailUrl": "/chopp-brahma-claro-30l/p",
          "components": [],
          "bundleItems": [],
          "attachments": [],
          "attachmentOfferings": [],
          "offerings": [],
          "priceTags": [],
          "availability": "available",
          "measurementUnit": "un",
          "unitMultiplier": 1,
          "manufacturerCode": null,
          "priceDefinition": {
            "calculatedSellingPrice": 32890,
            "total": 32890,
            "sellingPrices": [
              {
                "value": 32890,
                "quantity": 1
              }
            ]
          }
        }
      ],
      "sellers": [
        {
          "id": "1",
          "name": "Tracking QA",
          "logo": ""
        }
      ],
      "totals": [
        {
          "id": "Items",
          "name": "Total dos Itens",
          "value": 32890
        },
        {
          "id": "Discounts",
          "name": "Total dos Descontos",
          "value": 0
        },
        {
          "id": "Shipping",
          "name": "Total do Frete",
          "value": 1500
        },
        {
          "id": "Tax",
          "name": "Total da Taxa",
          "value": 0
        }
      ],
      "clientProfileData": {
        "email": "clark.kent@example.com",
        "firstName": "Clark",
        "lastName": "Kent",
        "document": "12345678900",
        "documentType": "cpf",
        "phone": "+5521998765432",
        "corporateName": null,
        "tradeName": null,
        "corporateDocument": null,
        "stateInscription": null,
        "corporatePhone": null,
        "isCorporate": false,
        "profileCompleteOnLoading": false,
        "profileErrorOnLoading": null,
        "customerClass": null
      },
      "ratesAndBenefitsData": {
        "rateAndBenefitsIdentifiers": [],
        "teaser": []
      },
      "shippingData": {
        "address": {
          "addressType": "residential",
          "receiverName": "Clark Kent",
          "addressId": "teste",
          "isDisposable": true,
          "postalCode": "70386000",
          "city": "Brasília",
          "state": "DF",
          "country": "BRA",
          "street": "Rua da minha casa",
          "number": "123",
          "neighborhood": "Copacabana",
          "complement": "15º andar",
          "reference": null,
          "geoCoordinates": [
            -47.924747467041016,
            -15.832582473754883
          ]
        },
        "logisticsInfo": [
          {
            "itemIndex": 0,
            "selectedSla": "Normal",
            "selectedDeliveryChannel": "delivery",
            "addressId": "teste",
            "slas": [
              {
                "id": "Normal",
                "deliveryChannel": "delivery",
                "name": "Normal",
                "deliveryIds": [
                  {
                    "courierId": "1",
                    "warehouseId": "1_1",
                    "dockId": "1",
                    "courierName": "Transportadora",
                    "quantity": 1,
                    "kitItemDetails": []
                  }
                ],
                "shippingEstimate": "3bd",
                "shippingEstimateDate": null,
                "lockTTL": "10d",
                "availableDeliveryWindows": [],
                "deliveryWindow": null,
                "price": 1500,
                "listPrice": 1500,
                "tax": 0,
                "pickupStoreInfo": {
                  "isPickupStore": false,
                  "friendlyName": null,
                  "address": null,
                  "additionalInfo": null,
                  "dockId": null
                },
                "pickupPointId": null,
                "pickupDistance": 0,
                "polygonName": null,
                "transitTime": "3bd"
              }
            ],
            "shipsTo": [
              "BRA",
              "COL",
              "USA"
            ],
            "itemId": "2",
            "deliveryChannels": [
              {
                "id": "delivery"
              },
              {
                "id": "pickup-in-point"
              }
            ]
          }
        ],
        "selectedAddresses": [
          {
            "addressType": "residential",
            "receiverName": "Clark Kent",
            "addressId": "teste",
            "isDisposable": true,
            "postalCode": "12345000",
            "city": "Rio de Janeiro",
            "state": "RJ",
            "country": "BRA",
            "street": "Rua da minha casa",
            "number": "123",
            "neighborhood": "Copacabana",
            "complement": "15º andar",
            "reference": null,
            "geoCoordinates": [
              -47.924747467041016,
              -15.832582473754883
            ]
          }
        ],
        "availableAddresses": [
          {
            "addressType": "residential",
            "receiverName": "Clark Kent",
            "addressId": "teste",
            "isDisposable": true,
            "postalCode": "12345000",
            "city": "Rio de Janeiro",
            "state": "RJ",
            "country": "BRA",
            "street": "Rua da minha casa",
            "number": "123",
            "neighborhood": "Copacabana",
            "complement": "15º andar",
            "reference": null,
            "geoCoordinates": [
              -47.924747467041016,
              -15.832582473754883
            ]
          }
        ],
        "pickupPoints": []
      },
      "paymentData": {
        "giftCards": [],
        "transactions": [
          {
            "isActive": true,
            "transactionId": "296D6D245C17437E823EB77E403FC88D",
            "merchantName": "MYSTORE",
            "payments": [],
            "sharedTransaction": false
          }
        ]
      },
      "clientPreferencesData": null,
      "commercialConditionData": null,
      "giftRegistryData": null,
      "marketingData": null,
      "storePreferencesData": {
        "countryCode": "BRA",
        "saveUserData": false,
        "timeZone": "E. South America Standard Time",
        "currencyCode": "BRL",
        "currencyLocale": 1046,
        "currencySymbol": "R$",
        "currencyFormatInfo": {
          "currencyDecimalDigits": 2,
          "currencyDecimalSeparator": ",",
          "currencyGroupSeparator": ".",
          "currencyGroupSize": 3,
          "startsWithCurrencySymbol": true
        }
      },
      "openTextField": {
        "value": null
      },
      "invoiceData": null,
      "itemMetadata": {
        "items": [
          {
            "id": "2",
            "seller": "1",
            "name": "Chopp Brahma Claro 30L",
            "skuName": "Chopp Brahma Claro 30L",
            "productId": "2",
            "refId": "CBC30L",
            "ean": null,
            "imageUrl": "http://mystore.vteximg.com.br/arquivos/ids/155400-55-55/30l_v2.png?v=637303412106100000",
            "detailUrl": "/chopp-brahma-claro-30l/p",
            "assemblyOptions": []
          }
        ]
      },
      "taxData": null,
      "customData": null,
      "hooksData": null,
      "changeData": null,
      "subscriptionData": null,
      "salesChannel": "1",
      "followUpEmail": "6c10d76b5170456d89823b38b7c8f6ac@ct.vtex.com.br",
      "creationDate": "2021-07-13T18:33:25.3029443Z",
      "lastChange": "2021-07-13T18:33:27.736557Z",
      "timeZoneCreationDate": "2021-07-13T15:33:25.3029443",
      "timeZoneLastChange": "2021-07-13T15:33:27.736557",
      "isCompleted": false,
      "hostName": "mystore",
      "merchantName": null,
      "userType": "",
      "roundingError": 0,
      "allowEdition": false,
      "allowCancellation": false,
      "isUserDataVisible": true,
      "allowChangeSeller": false,
      "orderFormCreationDate": "2021-07-13T18:33:25.1313373Z"
    }
  ],
  "salesAssociateData": {
    "salesAssociateId": "seller123"
  }
}
```

</CH.Code>

---

### Step 5 - Place the order

This `orderForm` can now be sent as the body in the [Place order API request.](https://developers.vtex.com/docs/api-reference/checkout-api#put-/api/checkout/pub/orders)

If you get a status `201 Created` response, take note of four pieces of information from its response content:

- `orderId`: ID of the order within VTEX’s Order Management System (OMS). You can find an  `orderId` in each object in the `orders` array.
- `transactionId`: ID of the transaction, which can be found in the objects contained in the `transactionData.merchantTransactions` array.
- `addressId`: if you're going to use the same address for shipping and billing, get this ID from the `orders[].shippingData.address` object.
- `Vtex_CHKO_Auth`: authentication cookie that is sent with the response.

>❗ Starting from the placing of the order, you have five minutes to complete the payment process. Otherwise, the order is automatically canceled and tagged `incomplete`.

<CH.Code>

```shell Shell
```

```python Python
```

```js Node.js
```

---

```json Response
```

</CH.Code>

---

## Step 6. Send payment information

With the `orderId` and `transactionId` values in hand, you must now inform VTEX of the payment data that should be used to resolve the order payment. To do this, use the [Send payment information API request](https://developers.vtex.com/docs/api-reference/payments-gateway-api#post-/api/pub/transactions/-transactionId-/payments). Note that there is also an alternative [private request for sending payment information](https://developers.vtex.com/docs/api-reference/payments-gateway-api#post-/api/pvt/transactions/-transactionId-/payments), that can be used to send saved credit card data.

The information you send in this step’s request body should be based on the `paymentData` section of your `orderForm`.

> ℹ️️ In the `fields` object, you can send an `addressId` to use an existing address or a new `address` object.

>❗ Make sure that all value-related fields match the information sent in [step four](https://developers.vtex.com/docs/guides/create-a-regular-order-using-the-checkout-api#4-place-the-order), when placing the order.

<CH.Code>

```shell Shell
curl --request post \
 --url 'https://{accountname}.vtexpayments.com.br/api/pub/transactions//payments' \
 --header 'Content-Type: application/json' \
 --header 'X-VTEX-API-AppKey: ' \
 --header 'X-VTEX-API-AppToken: ' \
 --data '[{"paymentSystem":4,"installments":1,"currencyCode":"BRL","value":100,"installmentsInterestRate":0,"installmentsValue":100,"referenceValue":100,"fields":{"holderName":"UserTest","cardNumber":"5378244888889174","validationCode":"231","dueDate":"10/19","document":"8041734561","accountId":"","address":null,"callbackUrl":""},"transaction":{"id":"{{transactionId}}","merchantName":"{{accountName}}"}}]'
```

```python Python
import http.client

conn = http.client.HTTPSConnection("%7Baccountname%7D.vtexpayments.com.br")

payload = "[{\"paymentSystem\":4,\"installments\":1,\"currencyCode\":\"BRL\",\"value\":100,\"installmentsInterestRate\":0,\"installmentsValue\":100,\"referenceValue\":100,\"fields\":{\"holderName\":\"UserTest\",\"cardNumber\":\"5378244888889174\",\"validationCode\":\"231\",\"dueDate\":\"10/19\",\"document\":\"8041734561\",\"accountId\":\"\",\"address\":null,\"callbackUrl\":\"\"},\"transaction\":{\"id\":\"{{transactionId}}\",\"merchantName\":\"{{accountName}}\"}}]"

headers = {
    'Content-Type': "application/json",
    'X-VTEX-API-AppKey': "",
    'X-VTEX-API-AppToken': ""
    }

conn.request("post", "/api/pub/transactions//payments", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```js Node.js
const http = require("https");

const options = {
 "method": "post",
 "hostname": "%7Baccountname%7D.vtexpayments.com.br",
 "port": null,
 "path": "/api/pub/transactions//payments",
 "headers": {
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

req.write(JSON.stringify([
  {
    paymentSystem: 4,
    installments: 1,
    currencyCode: 'BRL',
    value: 100,
    installmentsInterestRate: 0,
    installmentsValue: 100,
    referenceValue: 100,
    fields: {
      holderName: 'UserTest',
      cardNumber: '5378244888889174',
      validationCode: '231',
      dueDate: '10/19',
      document: '8041734561',
      accountId: '',
      address: null,
      callbackUrl: ''
    },
    transaction: {id: '{{transactionId}}', merchantName: '{{accountName}}'}
  }
]));
req.end();
```

---

```json Response
[
    {
        "paymentSystem": 1,
        "paymentSystemName": "American Express",
        "group": "creditCardPaymentGroup",
        "installments": 1,
        "installmentsInterestRate": 0,
        "installmentsValue": 10100,
        "value": 10100,
        "referenceValue": 10100,
        "fields": 
        {
            "holderName": "Testing VTEX",
            "cardNumber": "4444 3333 2222 1111",
            "validationCode": "1234",
            "dueDate": "10/20",
            "addressId": "666c2e830bd9474ab6f6cc53fb6dd2d2"
        },
        "transaction": {
            "id": "123456789abcdefgh",
            "merchantName": "MyStore"
        },
        "currencyCode": "USD"
    }
]
```

</CH.Code>

---

## Step 7. Request order processing

Finally, you must request the processing of the order with the [Process order API request](https://developers.vtex.com/docs/api-reference/checkout-api#post-/api/checkout/pub/gatewayCallback/-orderGroup-).

At this point, if everything is ok with the payment, the order should be placed. Otherwise, you should get a `status 500` error.

> Be aware that this process uses the gateway connectors configured in your VTEX environment. Be careful to avoid any unwanted charges or unexpected payment denials.

<CH.Code>

```shell Shell
curl --request post \
 --url 'https://{accountname}.{environment}.com.br/api/checkout/pub/gatewayCallback/123456789' \
 --header 'Accept: application/json' \
 --header 'Content-Type: application/json' \
 --header 'Cookie: Vtex_CHKO_Auth=0e/RpYIEZu19BuwXB4tZ7eIGu9HT8vdUAHWQDHDpxMc=; CheckoutDataAccess=0e/PoiTEZu19BuwXB4tZ7eIGu9HT8vdUAHWQDHDpxMc=' \
 --header 'X-VTEX-API-AppKey: ' \
 --header 'X-VTEX-API-AppToken: '
```

```python Python
import http.client

conn = http.client.HTTPSConnection("%7Baccountname%7D.%7Benvironment%7D.com.br")

headers = {
    'Cookie': "Vtex_CHKO_Auth=0e/RpYIEZu19BuwXB4tZ7eIGu9HT8vdUAHWQDHDpxMc=; CheckoutDataAccess=0e/PoiTEZu19BuwXB4tZ7eIGu9HT8vdUAHWQDHDpxMc=",
    'Accept': "application/json",
    'Content-Type': "application/json",
    'X-VTEX-API-AppKey': "",
    'X-VTEX-API-AppToken': ""
    }

conn.request("post", "/api/checkout/pub/gatewayCallback/123456789", headers=headers)

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
 "path": "/api/checkout/pub/gatewayCallback/123456789",
 "headers": {
  "Cookie": "Vtex_CHKO_Auth=0e/RpYIEZu19BuwXB4tZ7eIGu9HT8vdUAHWQDHDpxMc=; CheckoutDataAccess=0e/PoiTEZu19BuwXB4tZ7eIGu9HT8vdUAHWQDHDpxMc=",
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

---

```json Response
{}
```

</CH.Code>

</CH.Spotlight>

## Checking the result

You should be able to verify your order was in fact placed in the [Order management module](https://help.vtex.com/en/tutorial/orders-list--tutorials_200#) in VTEX Admin.

You can also use the API requests [Get order](https://developers.vtex.com/docs/api-reference/orders-api#get-/api/oms/pvt/orders/-orderId-) and [List orders](https://developers.vtex.com/docs/api-reference/orders-api#get-/api/oms/pvt/orders) for this purpose.
