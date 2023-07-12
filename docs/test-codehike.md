---
title: "Hello, world!"
slug: "test-codehike"
hidden: false
createdAt: "2022-10-20T17:08:52.219Z"
updatedAt: "2022-10-21T14:33:45.242Z"
excerpt: "Insert a synopsis of your article here"
---

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