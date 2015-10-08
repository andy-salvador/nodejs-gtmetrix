gtmetrix
========

Access GTmetrix API methods with node.js

* [Node.js](https://nodejs.org)
* [GTMetrix](https://gtmetrix.com)
* [API documentation](https://gtmetrix.com/api/)


Example
-------

```js
var gtmetrix = require ('gtmetrix') ({
  email: 'your@mail.tld',
  apikey: 'abc123'
});

// Run test from London with Google Chrome
var test = {
  url: 'http://example.net/',
  location: 2,
  browser: 3
};

gtmetrix.test.create (test, console.log);
```

##### Result

```js
{ test_id: 'Ao0AYQbz',
  poll_state_url: 'https://gtmetrix.com/api/0.1/test/Ao0AYQbz' }
```


Installation
------------

`npm install gtmetrix`

You need an account at GTmetrix to get an API key.
The API key can be found [here](https://gtmetrix.com/api/#api-details) when you are logged in.


Configuration
-------------

The setup function takes an _object_ with these settings.

name    | type    | required | default | description
:-------|:--------|:---------|:--------|:--------------------
email   | string  | yes      |         | Your account email
apikey  | string  | yes      |         | Your account API key
timeout | integer | no       | 5000    | Wait timeout in ms


##### Example

```js
var gtmetrix = require ('gtmetrix') ({
  email: 'your@mail.tld',
  apikey: 'abc123',
  timeout: 10000
});
```


Error handling
--------------

The methods require a callback _function_ argument to process the results.
This `callback` received two arguments: `err` and `data`, as per industry standards.

When an error occurs `err` is an instance of `Error` with additional properties.

message          | description            | properties
:----------------|:-----------------------|:----------------------------------
request failed   | Request cannot be made | `error`
invalid response | Can't process response | `error` `statusCode` `contentType`
API error        | API returned an error  | `error` `statusCode` `contentType`


License
-------

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org>


Author
------

Franklin van de Meent
| [Website](https://frankl.in)
| [Github](https://github.com/fvdm)
