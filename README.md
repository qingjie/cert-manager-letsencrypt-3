```
namespace: default
-- cafe-master.yaml


namespace:cafe
coffee-minion.yaml
coffee.yaml


namespace:tea
tea.yaml
tea-minion.yaml
```


```
curl -v --resolve cafe.example.com:$IC_HTTPS_PORT:$IC_IP http://cafe.example.com:$IC_HTTPS_PORT/coffee --insecure
curl -v --resolve cafe.example.com:$IC_HTTPS_PORT:$IC_IP http://cafe.example.com:$IC_HTTPS_PORT/tea --insecure
```



```
qzhaos-MBP:tst8 qzhao$ curl -v --resolve cafe.example.com:$IC_HTTPS_PORT:$IC_IP http://cafe.example.com:$IC_HTTPS_PORT/coffee --insecure
* Added cafe.example.com:80:3.224.255.211 to DNS cache
* Hostname cafe.example.com was found in DNS cache
*   Trying 3.224.255.211...
* TCP_NODELAY set
* Connected to cafe.example.com (3.224.255.211) port 80 (#0)
> GET /coffee HTTP/1.1
> Host: cafe.example.com
> User-Agent: curl/7.64.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Server: nginx/1.17.9
< Date: Fri, 20 Mar 2020 14:09:29 GMT
< Content-Type: text/plain
< Content-Length: 158
< Connection: keep-alive
< Expires: Fri, 20 Mar 2020 14:09:28 GMT
< Cache-Control: no-cache
<
Server address: 192.168.0.251:80
Server name: coffee-bbd45c6-b8pj2
Date: 20/Mar/2020:14:09:29 +0000
URI: /coffee
Request ID: c86ba1b3f993a26a43015d79da7e76e3
* Connection #0 to host cafe.example.com left intact
* Closing connection 0
```

```
qzhaos-MBP:tst8 qzhao$ curl -v --resolve cafe.example.com:$IC_HTTPS_PORT:$IC_IP http://cafe.example.com:$IC_HTTPS_PORT/tea --insecure
* Added cafe.example.com:80:3.224.255.211 to DNS cache
* Hostname cafe.example.com was found in DNS cache
*   Trying 3.224.255.211...
* TCP_NODELAY set
* Connected to cafe.example.com (3.224.255.211) port 80 (#0)
> GET /tea HTTP/1.1
> Host: cafe.example.com
> User-Agent: curl/7.64.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Server: nginx/1.17.9
< Date: Fri, 20 Mar 2020 14:09:56 GMT
< Content-Type: text/plain
< Content-Length: 155
< Connection: keep-alive
< Expires: Fri, 20 Mar 2020 14:09:55 GMT
< Cache-Control: no-cache
<
Server address: 192.168.6.140:80
Server name: tea-5857f7786b-zz6f5
Date: 20/Mar/2020:14:09:56 +0000
URI: /tea
Request ID: 5df677b0bf74a157777476dbeec10c17
* Connection #0 to host cafe.example.com left intact
* Closing connection 0
```
