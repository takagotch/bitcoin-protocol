### bitcoin-protocol
---
https://github.com/mappum/bitcoin-protocol

```js
var net = require('net')
var bp = require('bitcoin-protocol')

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

{
  magic: Number,
  command: String,
  payload: Object
}

{
  version: Number,
  services: Buffer,
  timestamp: Number,
  receiverAddress: {
    services: Buffer,
    address: String,
    port: Number
  },
  senderAddress: {
    services: Buffer,
    address: String,
    port: Number
  },
  nonce: Buffer,
  userAgent: String,
  startHeight: Number,
  relay: Boolean
}

[
  {
    time: Number,
    services: Buffer,
    address: String,
    port: Number
  },
]

[
  {
    type: Number,
    hash: Buffer
  },
]

{
  version: Number,
  locator: [
    Buffer
  ],
  hashStop: Buffer
}

{
  version: Number,
  ins: [
    {
      hash: Buffer,
      index: Number,
      script: Buffer,
      sequence: Number
    }
  ],
  outs: [
    {
      value: BN,
      script: Buffer
    },
  ],
  locktime: Number
}

{
  header: {
    version: Number,
    prevHash: Buffer,
    merkleRoot: Buffer,
    timestamp: Number,
    bits: Number,
    nonce: Number,
  },
  transactions: [
    {},
  ]
}

[
  {
    header: {
      version: Number,
      prevHash: Buffer,
      merkleRoot: Buffer,
      timestamp: Number,
      bits: Number,
      nonce: Number,
    },
    nTransactions: Number
  }
]

{
  nonce: Buffer
}

{
  message: String,
  ccode: Number,
  reason: String,
  data: Buffer
}

{
  data: Buffer,
  nHashFuncs: Number,
  nTweak: Number,
  nFlags: Number
}

{
  data: Buffer
}

{
  header: {
    version: Number,
    prevHash: Buffer,
    merkleRoot: Buffer,
    timestamp: Number,
    bits: Number,
    nonce: Number
  },
  numTransactions: Number,
  hashes: [
    Buffer
  ],
  flags: Buffer
}

{
  payload: Buffer,
  signature: Buffer
}

```

```
```


