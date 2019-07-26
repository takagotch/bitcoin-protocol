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
      servces: Buffer(8).fill(0),
      timestamp: Math.round(Date.now() / 1000),
      receiverAddress: {
        services: Buffer(8).fill(0),
        address: '0.0.0.0',
        port: 8333
      },
      nonce: Buffer(8).fill(123),
      userAgent: 'foobar',
      startHeight: 0,
      relay: true
    }
  })
})

```

```json
{
 magic: Number
}

{
  magic: Number
}

{
  magic: Number,
  command: String,
  length: Number,
  checksum: Buffer,
  payload: Object
}





















```

```
```


