# promisified-pipe

```shell script
npm i promisified-pipe
```

# API

```ts
function promisifiedPipe(input: stream.Readable, output: stream.Writable): Promise<void>
```

# Example

Usage example in an Express.js request handler (middleware). This code will send the file from disk back to the browser.

```js
const fs = require("fs");
const promisifiedPipe = require("promisified-pipe");

function downloadFile(req, res, next) {
  promisifiedPipe(fs.createReadStream(req.params.file), res).catch(next);
}
```
