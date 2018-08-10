Isomorphic JSON-RPC 2.0 client for browser and Node.js with logging curl and time.

# Installation

```shell
yarn add jsonrpc-js
```

or

```shell
npm install jsonrpc-js --save
```

# Usage

```js
import JsonRpcClient from 'jsonrpc-js';

const jsonrpc = new JsonRpcClient({
    apiRoute: '/api/rpc/v1.0',
    headers: {
        'X-API-CLIENT': 'key',
    },
    withMeta: true,
});

jsonrpc
    .request('info.getSomething', { data: 'something' })
    .then(({ data, meta }) => {
        console.log('Data', data);
        console.log('Curl', meta.curl);
        console.log('Time for request', `${meta.timeRequest} ms`);
    })
    .catch((err) => console.log('ERROR', err));
```