---
title: "設置專案"
date: 2022-12-13T14:46:54+08:00
weight: 20
---

dev server configuration
static resource: icon font cdn 

## vite server proxy
vite.config.js
https://vitejs.dev/config/
```js
  server: {
    port: 3000,
    proxy: {
      // http://localhost:3000/api -> http://localhost:4567api/
      '/api': 'http://localhost:4567',
    }
  },
```

## .eslintrc.js
```js
module.exports = {
  extends: ["plugin:vue/essential", "eslint:recommended", "@vue/prettier"],
  parserOptions: {
    parser: "babel-eslint"
  },
  rules: {
    semi: ["error", "always"],
    "no-console": "off"
  }
};
```
## .prettierrc.js
```js
module.exports = {
  semi: false,
  singleQuote: true,
  arrowParens: "avoid"
};
```