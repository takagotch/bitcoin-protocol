### bitcoin-protocol
---
https://github.com/mappum/bitcoin-protocol

```js
var net = require()
var bp = require()

var decoder = bp.createDecodeStream()
decoder.on('data', function (message) { console.log(message) })

var encoder = bp.createEncodeStream()

var socket = net.connect(8333, '127.0.0.1', function () {
  socket.pipe(decoder)
  encoder.pipe(socket)
  
  encoder.write({
    magic: 0xd9b4bef9,
    command: 'version',
    payload: {
      version: 70012,
      servces:
    }
  })
})

```

```
```

```
```


