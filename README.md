Nitro does not compress response (same Content-Length: 6000), yet Vary: Accept-Encoding is added

```bash
$ curl -i -H "Accept-Encoding: gzip" http://localhost:3000
HTTP/1.1 200 OK
Vary: Accept-Encoding
content-type: text/html
Date: Tue, 22 Jul 2025 17:31:14 GMT
Connection: keep-alive
Keep-Alive: timeout=5
Content-Length: 6000

200 OK200 OK200...
```

```bash
$ curl -i -H "Accept-Encoding: identity" http://localhost:3000
HTTP/1.1 200 OK
content-type: text/html
Date: Tue, 22 Jul 2025 17:30:39 GMT
Connection: keep-alive
Keep-Alive: timeout=5
Content-Length: 6000

200 OK200 OK200...
```
