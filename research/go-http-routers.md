
## Repositories

1. https://github.com/gernest/alien
1. https://github.com/go-chi/chi
1. https://github.com/labstack/echo
1. https://github.com/go-ozzo/ozzo-routing

## Feature comparison

| alien | chi | echo | ozzo | Feature |
| :---: | :---: | :---: | :---: | ------- |
| :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | Supports HTTP Methods GET POST PUT DELETE PATCH HEAD OPTION |
| :white_check_mark:  | :white_check_mark: | :white_check_mark: | :white_check_mark: | Chains middleware |
| :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: | Groups |
| :x: | :white_check_mark: | :x: | :x: | Uses context.Context |
| :x: | :x: | :white_check_mark: |:white_check_mark: | Data binding for JSON, XML and form payload |
| :x: | :white_check_mark:  | :white_check_mark: | :x: | Transport Layer Security (TLS) |
| :x: | | | :white_check_mark: | Content negotiation: Accept |
| :x: | :x: | :x: | :white_check_mark: | Content negotiation: Language |
| :x: | :x: | :white_check_mark: | :white_check_mark: | Auth: Basic |
| :x: | :x: | :white_check_mark: | :white_check_mark: | Auth: Bearer token |
| :x: | :x: | :x: | :white_check_mark: | JSON Web Token (JWT) support |
| :x: | :x: | :x: | :white_check_mark: | Cross-Origin Resource Sharing (CORS) support |
| :x: | :x: | :x: | :white_check_mark: | Static files |
|  [:link:](https://github.com/gernest/alien#usage)  | [:link:](https://github.com/go-chi/chi/tree/master/_examples) | [:link:](https://echo.labstack.com/cookbook/hello-world) | [:link:](https://github.com/qiangxue/golang-restful-starter-kit) | Examples |
| [:link:](https://godoc.org/github.com/gernest/alien) | | | | GoDoc |
| :x: | :warning: | :white_check_mark: | :white_check_mark: | HTTP return codes |
| :x: | :white_check_mark: | :white_check_mark: | :white_check_mark: | HTTP 404 - NOT FOUND |
| :x: | :white_check_mark: | :white_check_mark: | :white_check_mark: | HTTP 405 - METHOD NOT ALLOWED |

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
   1. Automatic TLS via Let’s Encrypt 
   1. Currently 70 issues.  So there's interest 
1. ozzo-routing
   1. **License:** MIT
   1. **Imports:** encoding/json, encoding/xml, errors, fmt, math, net/http, net/url regexp, reflect, sort, strings, strconv, sync, time
   1. Similar to Express frameworks

## References

1. https://github.com/avelino/awesome-go/blob/master/README.md#routers
1. https://github.com/diyan/go-web-framework-comparsion
1. http://verbally.flimzy.com/in-search-of-the-best-minimal-go-http-router/
1. http://blog.jonathanchannon.com/2015/11/16/content-negotiation-golang/
1. https://www.nicolasmerouze.com/build-web-framework-golang/
