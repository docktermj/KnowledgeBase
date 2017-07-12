


| alien | chi | echo | ozzo | Feature |
| :---: | :---: | :---: | :---: | ------- |
| :white_check_mark: | :white_check_mark: | :white_check_mark: | | Supports HTTP Methods GET POST PUT DELETE PATCH HEAD OPTION |
| :x: | :white_check_mark: | :white_check_mark: | | Chains middleware |
| :x: | :white_check_mark: | :white_check_mark: | | Groups |
| :x: | :white_check_mark: | | | Uses context.Context |
| | | :white_check_mark: | | Data binding for JSON, XML and form payload |
| | | :white_check_mark: | | Automatic TLS via Let’s Encrypt |
| | | :white_check_mark: | | HTTP/2 support |
| :x: | [:link:](https://github.com/go-chi/chi/tree/master/_examples) | [:link:](https://echo.labstack.com/cookbook/hello-world) | | Examples |
| :x: | :warning: | :white_check_mark: | | HTTP return codes |
| :x: | :white_check_mark: | | | HTTP 404 - NOT FOUND |
| :x: | :white_check_mark: | | | HTTP 405 - METHOD NOT ALLOWED |

## Misc

1. alien
   1. **License:** MIT
   1. **Imports:** errors, net/http, path, strings, sync
1. chi
   1. **License:** MIT
   1. **Imports:** context, fmt, net, net/http, regexp, sort, strings, sync
1. echo
   1. **License:** MIT
   1. **Imports:** buffio, bytes, crypto/tls encoding/json, encoding/xml, errors, fmt, io, log, mime/multipart, net/http, net/url, os, path, path/filepath, reflect, runtime, strconv, strings, sync, time, github.com/dgrijalva/jwt-go, github.com/labstack/gommon, github.com/valyala/fasttemplate, golang.org/x/crypto
   1. Better development artifacts.  Makefile, Unit tests. Gopkg
   1. More recent activity
   1. Currently 70 issues.  So there's interest 

## References

1. https://github.com/avelino/awesome-go/blob/master/README.md#routers
1. https://github.com/diyan/go-web-framework-comparsion
1. http://verbally.flimzy.com/in-search-of-the-best-minimal-go-http-router/
1. http://blog.jonathanchannon.com/2015/11/16/content-negotiation-golang/
1. https://www.nicolasmerouze.com/build-web-framework-golang/
