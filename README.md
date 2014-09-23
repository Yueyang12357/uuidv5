# UUIDv5

## Install

`npm install uuidv5`


## Use

`var createUUIDv5 = require('uuidv5');`

If you are unfamiliar with v5 UUIDs, read [this](http://en.wikipedia.org/wiki/Universally_unique_identifier#Version_5_.28SHA-1_hash.29). For a deeper look, read [RFC 4122](http://tools.ietf.org/html/rfc4122).


## API

### createUUIDv5(namespace, name, [raw_output])

* `namespace` can be 'url', 'dns', 'oid', or 'x500'. If it's none of those, it must be a UUID to use as a namespace, either in string or Buffer form.
* `name` can be a string or Buffer. What it should contain is namespace-dependent.
* `raw_output` is an optional flag. If set to `true`, the UUID will be returned as a Buffer instead of as a string.

### createUUIDv5.uuidToString(uuid)

Takes a Buffer-form uuid and returns it as a string.

### createUUIDv5.uuidFromString(uuidStr)

Takes a UUID as a string (with or without dashes [-]) and returns it as a Buffer.


### Examples

```javascript
var createUUIDv5 = require('uuidv5');

// Generate a UUID in the default URL namespace
var urlUUID = createUUIDv5('url', 'http://google.com/page');

// Default DNS namespace
var dnsUUID = createUUIDv5('dns', 'google.com');

// Create your own namespace
var privns = createUUIDv5('null', 'my-private-namespace', true); // Buffer form is more efficient
var privUUID = createUUIDv5(privns, 'some-named-thing');
```
