---
title: Hello World
date: 2020-01-01
---

# This is a H1 header

Lorem ipsum blah blah blah


- list
  - item
  - item
- list
  - item
  - item

## Some code

`single-line code in backticks`

```js[server.js]
const http = require('http')
const bodyParser = require('body-parser')

http.createServer((req, res) => {
  bodyParser.parse(req, (error, body) => {
    res.end(body)
  })
}).listen(3000)
```

Go to [About](/about)
