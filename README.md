# Postman Sandbox

Module that unifies execution of third-party JavaScript within Node VM and Browser iFrame.

> This module is part of Postman Runtime Core and is not intended for independent use.
>
> If you are looking to execute collections, you should bee using [Newman](https://github.com/postmanlabs/newman)

## Usage
```
var Sandbox = require('postman-sandbox'),
    context;

Sandbox.createContext(function (err, ctx) {
    if (err) {
        return console.error(err);
    }

    ctx.execute(`// code here`, {}, {}, function (err) {
        if (err) {
            return console.error(err);
        }
        console.log('executed')
    });
});
```

## Sandbox Environment

The following section outlines the API available inside sandbox scripts

### pm

- pm.globals
- pm.environment

#### pre-request script specials

- pm.request

#### test script specials

- pm.request
- pm.response
