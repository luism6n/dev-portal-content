---
title: "Get Promotion By Id"
slug: "getcalculatorconfigurationbyid"
excerpt: "Retrieves a specific benefit by its Promotion ID"
hidden: false
createdAt: "2019-12-30T04:15:05.270Z"
updatedAt: "2020-09-30T19:37:17.268Z"
---
[block:callout]
{
  "type": "warning",
  "title": "Attention!",
  "body": "To get the Calculator Configuration ID, you need to access Admin and select one benefit. The ID is at the benefits' URL, after `/campaign` or `/promotions`."
}
[/block]
## Response body has the following properties 
[block:parameters]
{
  "data": {
    "h-0": "Attribute",
    "h-1": "Type",
    "h-2": "Description",
    "0-0": "`idCalculatorConfiguration`",
    "1-0": "`name`",
    "2-0": "`description`",
    "3-0": "`beginDateUtc`",
    "4-0": "`endDateUtc`",
    "5-0": "`lastModified`",
    "6-0": "`daysAgoOfPurchases`",
    "6-2": "Number of days that are considered to add the purchase history",
    "7-0": "`isActive`",
    "8-0": "`isArchived`",
    "9-0": "`isFeatured`",
    "10-0": "`disableDeal`",
    "11-0": "`activeDaysOfWeek`",
    "12-0": "`offset`",
    "13-0": "`activateGiftsMultiplier`",
    "14-0": "`newOffset`",
    "15-0": "`percentualDiscountValueList`",
    "16-0": "`maxPricesPerItems`",
    "17-0": "`cumulative`",
    "18-0": "`nominalShippingDiscountValue`",
    "19-0": "`absoluteShippingDiscountValue`",
    "20-0": "`nominalDiscountValue`",
    "21-0": "`maximumUnitPriceDiscount`",
    "22-0": "`percentualDiscountValue`",
    "23-0": "`percentualShippingDiscountValue`",
    "24-0": "`percentualTax`",
    "25-0": "`shippingPercentualTax`",
    "0-1": "string",
    "0-2": "Calculator Configuration ID",
    "1-1": "string",
    "1-2": "Promotion Name",
    "2-1": "string",
    "2-2": "Promotion internal description",
    "3-1": "string",
    "3-2": "Promotion Begin Date (UTC)",
    "4-1": "string",
    "4-2": "Promotion End Date (UTC)",
    "5-1": "string",
    "5-2": "When the Promotion was last modified.",
    "6-1": "integer",
    "7-1": "boolean",
    "7-2": "If set as true, the Promotion is activated. If set as false, the Promotion is deactivated",
    "8-1": "boolean",
    "8-2": "If set as true, the Promotion is archived. If set as false, the Promotion is not archived",
    "9-1": "boolean",
    "9-2": "Define if the promotion is featured. A featured promotion has a flag in the product that indicates the promotion",
    "10-1": "boolean",
    "10-2": "Deprecated",
    "11-1": "array",
    "11-2": "Define which days of the week the promotion will applied",
    "12-1": "integer",
    "12-2": "Time offset from UTC",
    "13-1": "boolean",
    "13-2": "If set as true, activates gifts Multiplier",
    "14-1": "float",
    "14-2": "New time offset from UTC",
    "15-1": "array",
    "15-2": "Deprecated",
    "16-1": "array",
    "16-2": "Deprecated",
    "17-1": "boolean",
    "17-2": "Define if a benefit can accumulate with another benefit",
    "18-1": "float",
    "18-2": "Define the nominal Shipping Discount Value",
    "19-1": "float",
    "19-2": "Define the absolute Shipping Discount Value",
    "20-1": "float",
    "20-2": "Define the nominal Discount Value",
    "21-1": "float",
    "21-2": "Define the maximum Unit Price Discount",
    "22-1": "float",
    "22-2": "Define the Percentual Discount Value",
    "23-1": "float",
    "23-2": "Define the Percentual Shipping Discount Value",
    "24-1": "float",
    "24-2": "Percentual Tax over purchase total value",
    "26-0": "`percentualDiscountValueList1`",
    "27-0": "`percentualDiscountValueList2`",
    "28-0": "`skusGift`",
    "31-0": "`nominalRewardValue`",
    "32-0": "`percentualRewardValue`",
    "35-0": "`orderStatusRewardValue`",
    "36-0": "`maxNumberOfAffectedItems`",
    "37-0": "`origin`",
    "39-0": "`idSellerIsInclusive`",
    "40-0": "`idsSalesChannel`",
    "42-0": "`marketingTags`",
    "44-0": "`paymentsMethods`",
    "45-0": "`stores`",
    "46-0": "`campaigns`",
    "47-0": "`storesAreInclusive`",
    "48-0": "`categories`",
    "49-0": "`categoriesAreInclusive`",
    "50-0": "`brands`",
    "51-0": "`brandsAreInclusive`",
    "52-0": "`products`",
    "55-0": "`productsAreInclusive`",
    "57-0": "`collections1BuyTogether`",
    "58-0": "`collections1BuyTogether`",
    "59-0": "`collections2BuyTogether`",
    "25-1": "float",
    "25-2": "Shipping Percentual Tax over purchase total value",
    "26-1": "float",
    "26-2": "Define the valid discounts for the SKUs in `listSku1BuyTogether`, discount list used for Buy Together Promotions",
    "27-1": "float",
    "27-2": "Equivalent to `percentualDiscountValueList1`",
    "28-1": "object",
    "28-2": "Define the Sku Gift Object",
    "31-1": "float",
    "31-2": "Define Nominal Reward Value that client will receive. Used for benefits type miles or benefits clubs",
    "32-1": "float",
    "32-2": "Define Percentual Reward Value that client will receive. Used for benefits type miles or benefits clubs",
    "35-1": "string",
    "35-2": "Define the order status reward value",
    "36-1": "integer",
    "36-2": "Define the max number of affected items for a benefit",
    "37-1": "string",
    "37-2": "Define the origin of the benefit, Marketplace or Seller",
    "39-1": "boolean",
    "39-2": "If set to true, this promotion will be applied to any seller present on the idSeller field. If set to false, sellers present on that field will make this promotion not to be applied",
    "40-1": "array",
    "40-2": "List of Sales Channels (Trade Policies) that activate this promotion",
    "42-1": "array",
    "42-2": "Benefit Marketing tags",
    "44-1": "object",
    "44-2": "Object compose by all the Payments Methods",
    "45-1": "array",
    "45-2": "deprecated",
    "46-1": "array",
    "46-2": "Campaign Audiences that activate this promotion",
    "47-1": "boolean",
    "47-2": "deprecated",
    "48-1": "object",
    "48-2": "Object compose by the categories that will active or deactivate the benefit",
    "49-1": "boolean",
    "49-2": "If set to true, this promotion will be applied to any category present on the categories field. If set to false, categories present on that field will make this promotion not to be applied",
    "50-1": "array",
    "50-2": "Object compose by the brands that will active or deactivate the benefit",
    "51-1": "boolean",
    "51-2": "If set to true, this promotion will be applied to any brand present on the brands field. If set to false, brands present on that field will make this promotion not to be applied",
    "52-1": "object",
    "52-2": "Object compose by the products that will active or deactivate the benefit",
    "55-1": "boolean",
    "55-2": "If set to true, this promotion will be applied to any product present on the products field. If set to false, products present on that field will make this promotion not to be applied",
    "57-1": "array",
    "57-2": "Define the collections that will generate the benefit, type Buy Together, More for less, Progressive Discount, Buy One Get One",
    "60-0": "`minimumQuantityBuyTogether`",
    "61-0": "`quantityToAffectBuyTogether`",
    "62-0": "`enableBuyTogetherPerSku`",
    "63-0": "`listSku1BuyTogether`",
    "64-0": "`listSku2BuyTogether`",
    "65-0": "`coupon`",
    "66-0": "`totalValueFloor`",
    "67-0": "`totalValueCeling`",
    "68-0": "`totalValueIncludeAllItems`",
    "69-0": "`totalValueMode`",
    "70-0": "`collections`",
    "71-0": "`collectionsIsInclusive`",
    "72-0": "`restrictionsBins`",
    "73-0": "`cardIssuers`",
    "74-0": "`totalValuePurchase`",
    "75-0": "`slasIds`",
    "76-0": "`isSlaSelected`",
    "77-0": "`isFirstBuy`",
    "78-0": "`firstBuyIsProfileOptimistic`",
    "80-0": "`isDifferentListPriceAndPrice`",
    "81-0": "`zipCodeRanges`",
    "82-0": "`itemMaxPrice`",
    "83-0": "`itemMinPrice`",
    "84-0": "`installment`",
    "85-0": "`isMinMaxInstallments`",
    "86-0": "`minInstallment`",
    "87-0": "`maxInstallment`",
    "88-0": "`merchants`",
    "89-0": "`clusterExpressions`",
    "90-0": "`paymentsRules`",
    "91-0": "`giftListTypes`",
    "92-0": "`productsSpecifications`",
    "93-0": "`affiliates`",
    "94-0": "`maxUsage`",
    "95-0": "`maxUsagePerClient`",
    "96-0": "`multipleUsePerClient`",
    "58-1": "array",
    "58-2": "Define the collections that will generate the benefit, type Buy Together, More for less, Progressive Discount, Buy One Get One",
    "59-1": "array",
    "59-2": "deprecated",
    "60-1": "integer",
    "60-2": "Define the minimum quantity for Buy Together benefit",
    "61-1": "integer",
    "61-2": "Define the quantity to affect buy Together Benefit",
    "62-1": "boolean",
    "62-2": "Enable Buy Together per SKU",
    "63-1": "array",
    "63-2": "SKU first list for the promotion Buy Togeter",
    "64-1": "array",
    "64-2": "SKU second list for the promotion Buy Together",
    "65-1": "array",
    "65-2": "deprecated",
    "66-1": "float",
    "66-2": "Minimum chart value to activate the promotion",
    "67-1": "float",
    "67-2": "Maximum chart value to activate the promotion",
    "68-1": "boolean",
    "68-2": "deprecated",
    "69-1": "string",
    "69-2": "Define if products that already are  receiving a promotion, will be considered on the chart total value. There are three options available: IncludeMatchedItems, ExcludeMatchedItems, AllItems",
    "70-1": "object",
    "70-2": "Object compose by the collections that will active or deactivate the benefit",
    "71-1": "boolean",
    "71-2": "If set to true, this promotion will be applied to any collection present on the categories field. If set to false, collections present on that field will make this promotion not to be applied",
    "72-1": "array",
    "72-2": "Define credit card Bins that actives the promotion",
    "73-1": "array",
    "73-2": "deprecated",
    "74-1": "float",
    "74-2": "Define total valeu a client must have in past orders to active the promotion",
    "75-1": "array",
    "75-2": "Shipping Method",
    "76-1": "boolean",
    "76-2": "Apply selected discount only when one of the defined shipping method is selected by the customer",
    "77-1": "boolean",
    "77-2": "Apply the discount only if it's a first buy",
    "78-1": "boolean",
    "78-2": "Apply the discount even if the user is not logged",
    "80-1": "boolean",
    "80-2": "Apply the benefit only if the list price and price is different",
    "81-1": "array",
    "81-2": "Define what is the range of the ZipCode that applies the benefit",
    "82-1": "integer",
    "82-2": "Maximum price of the item",
    "83-1": "integer",
    "83-2": "Minimum price of the item",
    "84-1": "integer",
    "84-2": "deprecated",
    "85-1": "boolean",
    "85-2": "Set if the benefits will be applied considering a minimum and maximum values for installments",
    "86-1": "integer",
    "86-2": "Minimum value for installment",
    "87-1": "integer",
    "87-2": "Maximum value for installment",
    "88-1": "array",
    "88-2": "deprecated",
    "89-1": "array",
    "89-2": "Define an expression to use with clusters",
    "90-1": "array",
    "90-2": "deprecated",
    "91-1": "array",
    "91-2": "Define Gifts List Type",
    "92-1": "array",
    "92-2": "deprecated",
    "93-2": "Define the affiliates",
    "93-1": "array",
    "94-1": "integer",
    "94-2": "Define how many times the benefit can be used",
    "95-1": "integer",
    "95-2": "Define how many times the benefit can be used per client",
    "96-1": "boolean",
    "96-2": "Define if the benefit can be used multiple times per client",
    "98-0": "`type`",
    "98-1": "string",
    "98-2": "Define what is the type of the benefit",
    "29-0": "`quantitySelectable`",
    "30-0": "`gifts`",
    "30-1": "array",
    "29-1": "integer",
    "29-2": "Define the quantity of SKU Gifts",
    "30-2": "Array that define which SKU Gifts was included",
    "33-0": "`applyToAllShippings`",
    "33-1": "boolean",
    "33-2": "Define if the Promotion will be applied to all kind of shipping",
    "34-0": "`nominalTax`",
    "34-1": "float",
    "34-2": "Define the Nominal Tax",
    "41-0": "`areSalesChannelIdsExclusive`",
    "41-1": "boolean",
    "41-2": "If set to false, this promotion will be applied to any sales channel present on the idsSalesChannel field. If set to true, Sales Channels present on that field will make this promotion not to be applied",
    "43-0": "`marketingTagsAreNotInclusive`",
    "43-1": "boolean",
    "43-2": "If set to false, this promotion will be applied to any marketing tag present on the marketingTags field. If set to true, marketing tags present on that field will make this promotion not to be applied",
    "53-0": "`id`",
    "54-0": "`name`",
    "54-1": "string",
    "53-1": "string",
    "53-2": "Product ID",
    "54-2": "Product Name",
    "56-0": "`skusAreInclusive`",
    "56-1": "boolean",
    "56-2": "If set to true, this promotion will be applied to any SKU present on the skus field. If set to false, SKUs present on that field will make this promotion not to be applied",
    "79-0": "`compareListPriceAndPrice`",
    "79-1": "boolean",
    "79-2": "Define if the List Price and Price are the same",
    "97-0": "`accumulateWithManualPrice`",
    "97-1": "boolean",
    "97-2": "Define if it is accumulate with Manual Price",
    "38-0": "`idSeller`",
    "38-1": "string",
    "38-2": "Define Seller Name"
  },
  "cols": 3,
  "rows": 99
}
[/block]
## Response body example:
[block:code]
{
  "codes": [
    {
      "code": "{\n    \"idCalculatorConfiguration\": \"1a9cae4f-5078-4a3c-bf5f-16869c93f122\",\n    \"name\": \"Campanha Social Seller\",\n    \"beginDateUtc\": \"2020-05-01T21:23:56.961Z\",\n    \"lastModified\": \"2020-05-01T21:25:09.374682Z\",\n    \"daysAgoOfPurchases\": 0,\n    \"isActive\": true,\n    \"isArchived\": false,\n    \"isFeatured\": false,\n    \"disableDeal\": false,\n    \"activeDaysOfWeek\": [],\n    \"offset\": -3,\n    \"activateGiftsMultiplier\": false,\n    \"newOffset\": -3.0,\n    \"percentualDiscountValueList\": [],\n    \"maxPricesPerItems\": [],\n    \"cumulative\": false,\n    \"metadata\": {\n        \"scope\": {\n            \"componentRepresentation\": {\n                \"allProducts\": true,\n                \"operator\": \"all\",\n                \"statements\": \"[]\"\n            }\n        }\n    },\n    \"effectType\": \"price\",\n    \"discountType\": \"percentual\",\n    \"nominalShippingDiscountValue\": 0.0,\n    \"absoluteShippingDiscountValue\": 0.0,\n    \"nominalDiscountValue\": 0.0,\n    \"maximumUnitPriceDiscount\": 0.0,\n    \"percentualDiscountValue\": 50.0,\n    \"rebatePercentualDiscountValue\": 0.0,\n    \"percentualShippingDiscountValue\": 0.0,\n    \"percentualTax\": 0.0,\n    \"shippingPercentualTax\": 0.0,\n    \"percentualDiscountValueList1\": 0.0,\n    \"percentualDiscountValueList2\": 0.0,\n    \"skusGift\": {\n        \"quantitySelectable\": 0\n    },\n    \"nominalRewardValue\": 0.0,\n    \"percentualRewardValue\": 0.0,\n    \"orderStatusRewardValue\": \"invoiced\",\n    \"maxNumberOfAffectedItems\": 0,\n    \"maxNumberOfAffectedItemsGroupKey\": \"perCart\",\n    \"applyToAllShippings\": false,\n    \"nominalTax\": 0.0,\n    \"origin\": \"marketplace\",\n    \"idSellerIsInclusive\": true,\n    \"idsSalesChannel\": [],\n    \"areSalesChannelIdsExclusive\": false,\n    \"marketingTags\": [],\n    \"marketingTagsAreNotInclusive\": false,\n    \"paymentsMethods\": [],\n    \"stores\": [],\n    \"campaigns\": [],\n    \"conditionsIds\": [\n        \"2e42b490-fe80-49b0-aa72-4def8457908d\"\n    ],\n    \"storesAreInclusive\": false,\n    \"categories\": [],\n    \"categoriesAreInclusive\": false,\n    \"brands\": [],\n    \"brandsAreInclusive\": false,\n    \"products\": [],\n    \"productsAreInclusive\": false,\n    \"skusAreInclusive\": true,\n    \"utmCampaign\": \"Interna\",\n    \"collections1BuyTogether\": [],\n    \"collections2BuyTogether\": [],\n    \"minimumQuantityBuyTogether\": 0,\n    \"quantityToAffectBuyTogether\": 0,\n    \"enableBuyTogetherPerSku\": false,\n    \"listSku1BuyTogether\": [],\n    \"listSku2BuyTogether\": [],\n    \"coupon\": [],\n    \"totalValueFloor\": 0.0,\n    \"totalValueCeling\": 0.0,\n    \"totalValueIncludeAllItems\": false,\n    \"totalValueMode\": \"IncludeMatchedItems\",\n    \"collections\": [],\n    \"collectionsIsInclusive\": false,\n    \"restrictionsBins\": [],\n    \"cardIssuers\": [],\n    \"totalValuePurchase\": 0.0,\n    \"slasIds\": [],\n    \"isSlaSelected\": false,\n    \"isFirstBuy\": false,\n    \"firstBuyIsProfileOptimistic\": false,\n    \"compareListPriceAndPrice\": false,\n    \"isDifferentListPriceAndPrice\": false,\n    \"zipCodeRanges\": [],\n    \"itemMaxPrice\": 0.0,\n    \"itemMinPrice\": 0.0,\n    \"installment\": 0,\n    \"isMinMaxInstallments\": false,\n    \"minInstallment\": 0,\n    \"maxInstallment\": 0,\n    \"merchants\": [],\n    \"clusterExpressions\": [],\n    \"paymentsRules\": [],\n    \"giftListTypes\": [],\n    \"productsSpecifications\": [],\n    \"affiliates\": [],\n    \"maxUsage\": 0,\n    \"maxUsagePerClient\": 0,\n    \"multipleUsePerClient\": false,\n    \"accumulateWithManualPrice\": false,\n    \"type\": \"regular\"\n}",
      "language": "json"
    }
  ]
}
[/block]