mock-webtorrent
===============

Use like you would use feross/webtorrent.

# example

### what you would do with actual webtorrent

```js
var WebTorrent = require('webtorrent')
var client1 = new WebTorrent()
var client2 = new WebTorrent() // Note this line...

client1.seed(...)
client2.download(...)
```

### what you do with this mock

```js
var WebTorrent = require('mock-webtorrent')
var client1 = new WebTorrent()
var client2 = client1 // Note this line...

client1.seed(...)
client2.download(...)
```

# api

### `client.destroy()`

### `client.remove(infoHash)`

- `infoHash` is a string, e.g. `'01a6faadd5d05e3af27dff2424e0a99bdeb825fc'`

### `client.seed(files, cb(torrent))`

- `files` is an array of filename strings, e.g. `[ 'file1.txt', 'awesome.avi' ]`
- `cb` is a callback function that has the argument `torrent`

### `client.add(infoHash, [config,] cb(torrent))`
### `client.download(infoHash, [config,] cb(torrent))`

- `infoHash` is a string, e.g. `'01a6faadd5d05e3af27dff2424e0a99bdeb825fc'`
- `config` is an optional object that doesn't do anything in this mock
- `cb` is a callback function that has the argument `torrent`

### `torrent`

- `torrent.infoHash`
- `torrent.files`

### `file`

- `name` is a string of the filename, e.g. `'awesome.avi'`
- `getBlobURL()` is a function that returns a string of the blob URL
- `createReadStream()` is a function that returns a read stream of the file

# install

With [npm](http://nodejs.org/download) do:

	npm install mock-webtorrent

# todo

- tests
- travis-ci
- implement more of the webtorrent api, as needed

# license

[VOL](http://veryopenlicense.com)
