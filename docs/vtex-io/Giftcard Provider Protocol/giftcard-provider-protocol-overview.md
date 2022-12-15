---
title: "Giftcard Provider Protocol - Overview"
slug: "giftcard-provider-protocol-overview"
hidden: false
createdAt: "2020-01-02T05:18:04.548Z"
updatedAt: "2020-09-29T21:41:38.573Z"
---
The **Gift Card Provider Protocol** is a set of definitions to help you integrate your Gift Card API into VTEX platform. 

To achieve this, you need to implement a web API (REST) following the specifications from this documentation and configure your provider in your store using [Gift Card Hub API](https://developers.vtex.com/reference/giftcard-hub-api-overview).

## Common parameters in the documentation

<table>
  <tr>
    <td><code>{{providerApiEndpoint}}</code></td>
    <td>Provider's endpoint for the implementation (mandatory)</td>
  </tr>
  <tr>
    <td><code>{{X-PROVIDER-API-AppKey}}</code></td>
    <td>The AppKey configured by the merchant (optional)</td>
  </tr>
  <tr>
    <td><code>{{X-PROVIDER-API-AppToken}}</code></td>
    <td>The AppToken configured by the merchant (optional)</td>
  </tr>
</table>