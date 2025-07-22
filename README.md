Nitro does not compress response (same Content-Length: 6000), yet Vary: Accept-Encoding is added

```bash
$ http :3000/test Accept-Encoding:gzip

HTTP/1.1 200 OK
Connection: keep-alive
Content-Length: 6000
Date: Tue, 22 Jul 2025 16:20:37 GMT
Keep-Alive: timeout=5
Vary: Accept-Encoding
content-type: text/html

200 OK200 OK200...
```

```bash
$ http :3000/test Accept-Encoding:identity

HTTP/1.1 200 OK
Connection: keep-alive
Content-Length: 6000
Date: Tue, 22 Jul 2025 16:20:41 GMT
Keep-Alive: timeout=5
content-type: text/html

200 OK200 OK200...
```
