# pull-pair

simplest duplex pull stream.

A duplex pair of streams `{source, sink}`)

such that a reading everything that the sink reads the source outputs.

``` js
var pull = require('pull-stream')
var pair = require('pull-pair')

var p = pair()

pull(pull.values([1, 2, 3]), p.sink)
pull(p.source, pull.collect(function (err, values) {
  if(err) throw err
  console.log(values) //[1, 2, 3]
}))

```


## License

MIT
