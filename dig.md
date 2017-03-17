## DNS

DNS （Domain Name System 的缩写）的作用非常简单，就是根据域名查出IP地址。举例来说，如果你要访问域名math.stackexchange.com，首先要通过DNS查出它的IP地址是151.101.129.69。

## 查询过程

`dig math.stackexchange.com`

```bash
; <<>> DiG 9.8.3-P1 <<>> math.stackexchange.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 49446
;; flags: qr rd ra; QUERY: 1, ANSWER: 4, AUTHORITY: 4, ADDITIONAL: 0

;; QUESTION SECTION:
;math.stackexchange.com.		IN	A

;; ANSWER SECTION:
math.stackexchange.com.	300	IN	A	151.101.129.69
math.stackexchange.com.	300	IN	A	151.101.193.69
math.stackexchange.com.	300	IN	A	151.101.65.69
math.stackexchange.com.	300	IN	A	151.101.1.69

;; AUTHORITY SECTION:
stackexchange.com.	172414	IN	NS	ns-cloud-d1.googledomains.com.
stackexchange.com.	172414	IN	NS	ns-cloud-d2.googledomains.com.
stackexchange.com.	172414	IN	NS	ns-1029.awsdns-00.org.
stackexchange.com.	172414	IN	NS	ns-925.awsdns-51.net.

;; Query time: 6 msec
;; SERVER: 202.101.172.35#53(202.101.172.35)
;; WHEN: Fri Mar 17 21:56:19 2017
;; MSG SIZE  rcvd: 239
```

第一段是查询参数和统计。

```bash
; <<>> DiG 9.8.3-P1 <<>> math.stackexchange.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 49446
;; flags: qr rd ra; QUERY: 1, ANSWER: 4, AUTHORITY: 4, ADDITIONAL: 0
```

第二段是查询内容。

```bash
;; QUESTION SECTION:
;math.stackexchange.com.		IN	A
```

上面结果表示，查询域名math.stackexchange.com的A记录，A是address的缩写。

第三段是DNS服务器的答复。

```bash
;; ANSWER SECTION:
math.stackexchange.com.	300	IN	A	151.101.129.69
math.stackexchange.com.	300	IN	A	151.101.193.69
math.stackexchange.com.	300	IN	A	151.101.65.69
math.stackexchange.com.	300	IN	A	151.101.1.69
```

上面结果显示，math.stackexchange.com有四个A记录，即四个IP地址。600是TTL值（Time to live 的缩写），表示缓存时间，即600秒之内不用重新查询。

第四段显示stackexchange.com的NS记录（Name Server的缩写），即哪些服务器负责管理stackexchange.com的DNS记录。

```bash
;; AUTHORITY SECTION:
stackexchange.com.	172414	IN	NS	ns-cloud-d1.googledomains.com.
stackexchange.com.	172414	IN	NS	ns-cloud-d2.googledomains.com.
stackexchange.com.	172414	IN	NS	ns-1029.awsdns-00.org.
stackexchange.com.	172414	IN	NS	ns-925.awsdns-51.net.
```

上面结果显示stackexchange.com共有四条NS记录，即四个域名服务器，向其中任一台查询就能知道math.stackexchange.com的IP地址是什么。

最后是DNS服务器的一些传输信息

```bash
;; Query time: 6 msec
;; SERVER: 202.101.172.35#53(202.101.172.35)
;; WHEN: Fri Mar 17 21:56:19 2017
;; MSG SIZE  rcvd: 239
```

上面结果显示，本机的DNS服务器是202.101.172.35，查询端口是53（DNS服务器的默认端口），以及回应长度是239字节。


如果不想看到这么多内容，可以使用+short参数。

```bash
→ dig +short ath.stackexchange.com
151.101.65.69
151.101.129.69
151.101.1.69
151.101.193.69
```

## 参考

http://www.ruanyifeng.com/blog/2016/06/dns.html
