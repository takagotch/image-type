### image-type
---
https://github.com/sindresorhus/image-type

```js
const readChunk = require('read-chunk');
const imageType = require('image-type');

const buffer = readChunk.sync('unicorn.png', 0, 12);
imageType(buffer);


const http = require('http');
const imageType = require('image-type');

const url = 'https://assets-cdn.github.com/images/spinners/octocat-spinner-32.gif';

http.get(url, response => {
  response.on('readable', () => {
    const chunk = response.read(imageType.minimumBytes);
    response.destroy();
    console.log(imageType(chunk));
  });
});

const xhr = new XMLHttpRequest();
xhr.open('GET', 'unicorn.png');
xhr.responseType = 'arraybuffer';

xhr.onload = () => {
  imageType(new Uint8Array(this.response));
};

xhr.send();

```

```sh
npm install image-type
```

```
```


