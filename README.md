# @feathersjs/express


> __Important:__ The code for this module has been moved into the main Feathers repository at [feathersjs/feathers](https://github.com/feathersjs/feathers) ([package direct link](https://github.com/feathersjs/feathers/tree/master/packages/express)). Please open issues and pull requests there. No changes in your existing Feathers applications are necessary.

[![Build Status](https://travis-ci.org/feathersjs/express.png?branch=master)](https://travis-ci.org/feathersjs/express)

Feathers Express framework bindings and REST provider

This plugin turns a Feathers v3+ application into a drop-in replacement for any Express application.

## Installation

```
npm install @feathersjs/express --save
```

> _Important:_ This plugin only works with `feathers` 3.0 and later

## Documentation

Please refer to the [@feathersjs/express API documentation](https://docs.feathersjs.com/api/express.html) for more details.

## Complete Example

Here's an example of a Feathers server that uses `@feathersjs/express`. 

```js
const feathers = require('@feathersjs/feathers');
const express = require('@feathersjs/express');

const app = express(feathers());

app.configure(express.rest());
app.use('/myservice', {
  get(id) {
    return Promise.resolve({ id });
  }
});

app.use((req, res) => res.json({ message: 'Hello world' }));

app.listen(3030);

console.log('Feathers app started on 127.0.0.1:3030');
```

## License

Copyright (c) 2017

Licensed under the [MIT license](LICENSE).
