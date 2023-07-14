---
title: "Hello, world!"
slug: "test-codehike"
hidden: false
createdAt: "2022-10-20T17:08:52.219Z"
updatedAt: "2022-10-21T14:33:45.242Z"
excerpt: "Insert a synopsis of your article here"
---

## Understanding the `home.jsonc` file

Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quia! Quidem, quisquam.

<CH.Code>

```shell Shell
curl --request post \
  # withClass[16] placeholder
 --url 'https://.{environment}.com.br/api/checkout/pub/orderForms/simulation?RnbBehavior=0' \
 --header 'Accept: application/json' \
 --header 'Content-Type: application/json' \
 --header 'X-VTEX-API-AppKey: ' \
 --header 'X-VTEX-API-AppToken: ' \
 --data '{"items":[{"id":"1","quantity":1,"seller":"1"}],"country":"BRA","postalCode":"12345-000","geoCoordinates":[-47.924747467041016]}'
```

</CH.Code>

<CH.Spotlight>

```json home.jsonc
{
  "store.home": {
    "blocks": [
      "list-context.image-list#demo",      
      "flex-layout.row#deals",
      "rich-text#shelf-title",
      "flex-layout.row#shelf",
      "info-card#home",
      "rich-text#question",
      "rich-text#link",
      "newsletter"
    ]
  },

  "shelf#home": {
    "blocks": ["product-summary.shelf"]
  },

  "product-summary.shelf": {
    "children": [
      "product-summary-name",
      "product-summary-description",
      "product-summary-image",
      "product-summary-price",
      "product-summary-sku-selector",
      "product-summary-buy-button"
    ]
  },

  "list-context.image-list#demo": {
    "children": ["slider-layout#demo-images"],
    "props": {
      "height": 720,
      "images": [
        {
          "image": "https://storecomponents.vteximg.com.br/arquivos/banner-principal.png",
          "mobileImage": "https://storecomponents.vteximg.com.br/arquivos/banner-principal-mobile.jpg"
        },
        {
          "image": "https://storecomponents.vteximg.com.br/arquivos/banner.jpg",
          "mobileImage": "https://storecomponents.vteximg.com.br/arquivos/banner-principal-mobile.jpg"
        }
      ]
    }
  },
  "slider-layout#demo-images": {
    "props": {
      "itemsPerPage": {
        "desktop": 1,
        "tablet": 1,
        "phone": 1
      },
      "infinite": true,
      "showNavigationArrows": "desktopOnly",
      "blockClass": "carousel"
    }
  },

  "rich-text#shelf-title": {
    "props": {
      "text": "## Summer",
      "blockClass": "shelfTitle"
    }
  },
  "flex-layout.row#shelf": {
    "children": ["list-context.product-list#demo1"]
  },
  "list-context.product-list#demo1": {
    "blocks": ["product-summary.shelf"],
    "children": ["slider-layout#demo-products"],
    "props": {
      "orderBy": "OrderByTopSaleDESC"
    }
  },
  "slider-layout#demo-products": {
    "props": {
      "itemsPerPage": {
        "desktop": 5,
        "tablet": 3,
        "phone": 1
      },
      "infinite": true,
      "fullWidth": true,
      "blockClass": "shelf"
    }
  },

  "info-card#home": {
    "props": {
      "id": "info-card-home",
      "isFullModeStyle": false,
      "textPosition": "left",
      "imageUrl": "https://storecomponents.vteximg.com.br/arquivos/banner-infocard2.png",
      "headline": "Clearance Sale",
      "callToActionText": "DISCOVER",
      "callToActionUrl": "/sale/d",
      "blockClass": "info-card-home",
      "textAlignment": "center"
    }
  },

  "rich-text#question": {
    "props": {
      "text": "**This is an example store built using the VTEX platform.\nWant to know more?**",
      "blockClass": "question"
    }
  },

  "rich-text#link": {
    "props": {
      "text": "\n**Reach us at**\nwww.vtex.com.br",
      "blockClass": "link"
    }
  },

  "product-summary-buy-button": {
    "props": { 
      "displayBuyButton": "displayButtonAlways"
    }
  }
}
```

---

### `store.home`
As we can see, the default `store.home` homepage template declares the following blocks:

- `list-context.image-list#demo`
- `flex-layout.row#deals`
- `rich-text#shelf-title`
- `flex-layout.row#shelf`
- `info-card#home`
- `rich-text#question`
- `rich-text#link`
- `newsletter`

```json home.jsonc focus=2:13
```

---

### `rich-text#question`

The `rich-text#question` block is responsible for rendering a component that displays markdown texts to users.

As we can see, the this block is using two props: `text` and `blockClass`. These are responsible for defining which text the component will display and for defining an ID that will be used for its customization.

```js home.jsonc focus=102:108

```

---

### `shelf#home`

```json home.jsonc focus=15:18
```

</CH.Spotlight>

<CH.Code>

```js app.js focus=2:4
function lorem(ipsum, dolor = 1) {
  const sit = ipsum == null ? 0 : ipsum.sit;
  dolor = sit - amet(dolor);
  return sit ? consectetur(ipsum) : [];
}
```

```python hello.py
print("Hello, world!")
```

---

```css styles.css
.lorem {
  color: #fff;
  padding: 10px;
  background: #000;
}
```

</CH.Code>


# Spotlight

This is how to use the `<CH.Spotlight>` component. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, quia! Quidem, quisquam.

<CH.Spotlight>

```js app.js
function lorem(ipsum, dolor = 1) {
  const sit = ipsum == null && 0;
  dolor = sit - amet(dolor);
  return sit ? consectetur(ipsum) : [];
}
```

---

Change focus

```js app.js focus=2:4

```

---

Or change the code

```js app.js focus=6:10
function lorem(ipsum, dolor = 1) {
  const sit = ipsum == null && 0;
  dolor = sit - amet(dolor);
  return sit ? consectetur(ipsum) : [];
}

function adipiscing(...elit) {
  console.log(elit);
  return elit.map((ipsum) => ipsum.sit);
}
```

---

Or change the file

<CH.Code>

```js app.js focus=1:4
function adipiscing(...elit) {
  console.log(elit);
  return elit.map((ipsum) => ipsum.sit);
}
```

---

```css styles.css
.lorem {
  color: #fff;
  padding: 10px;
  background: #000;
}
```

</CH.Code>

---

### By the way

- you can
- put any
- markdown
- here

👍

```js app.js

```

</CH.Spotlight>