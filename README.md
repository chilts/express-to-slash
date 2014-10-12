# express-to-slash #

If you're anal about slashes, you should use this. I don't think '/admin' and '/admin/' should serve the same thing, if
only because it makes relative links in the page point to completely different things.

Note: there is already [express-slash](https://www.npmjs.org/package/express-slash) which you use after your router so that
it flip-flops between slash and non-slash.

This package is more specific. It only redirects from a non-slash to slash version of the path, and you have to be explicit
about where you use it.

## Synopsis ##

```
var app = express()
var toSlash = require('express-to-slash')

app.all('/admin', toSlash())
app.all('/blog', toSlash(301)) // Moved Permanently
```

This will redirect all `.get()`, `.head()`, `.post()` etc requests to `/admin`. It will also include any querystring
which was included in the request.

e.g. `/admin?hello=world` will redirect to `/admin/?hello=world`

## AUTHOR ##

Written by [Andrew Chilton](http://chilts.org/):

* [Blog](http://chilts.org/)
* [GitHub](https://github.com/chilts)
* [Twitter](https://twitter.com/andychilton)
* [Instagram](http://instagram.com/thechilts)

## LICENSE ##

Copyright 2014 Andrew Chilton <andychilton@gmail.com>.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

(Ends)
