你好！
很冒昧用这样的方式来和你沟通，如有打扰请忽略我的提交哈。我是光年实验室（gnlab.com）的HR，在招Golang开发工程师，我们是一个技术型团队，技术氛围非常好。全职和兼职都可以，不过最好是全职，工作地点杭州。
我们公司是做流量增长的，Golang负责开发SAAS平台的应用，我们做的很多应用是全新的，工作非常有挑战也很有意思，是国内很多大厂的顾问。
如果有兴趣的话加我微信：13515810775  ，也可以访问 https://gnlab.com/，联系客服转发给HR。
Popub
=====

Publish a service from localhost onto your server.

Scenario
--------

If you have a web service, a game service, an SSH service, a VNC service, or any TCP service at your home computer. Your home computer is behind NAT and don't have a public and static IP address, but you want your friends to connect to your service.

If you operate another computer or server, which has a public or static IP address, you can run Popub there, to relay the data between your home computer and your friends, so that your service is made public accessible.

Building
--------

Download the source code, and the latest [Go](https://golang.org/dl/).

On your home computer, type:

```
cd popub-local
go build
```

On your server machine, type:

```
cd popub-relay
go build
```

Running
-------

Assume you have a web service at `localhost:80`, you want to publish it as `my.server.addr:8080`, and you want to use `my.server.addr:46687` to communicate between your home computer and your server machine.

On your home computer, type:

```
cd popub-local
./popub-local localhost:80 my.server.addr:46687 SomePassword
```

On your server machine, type:

```
cd popub-relay
./popub-relay :46687 :8080 SomePassword
```

Note: The password is for authorization only, your traffic is not encrypted.

Running as Systemd services
---------------------------

Refer to [systemd/README.md](systemd/README.md) for instructions on running as Systemd services.

License
-------

This program is licensed under GPL version 3. See [COPYING](COPYING) for details.

See Also
--------

Also please check [pofwd](https://github.com/m13253/pofwd), which is a general purpose port forwarder. It is like [socat](http://www.dest-unreach.org/socat/), but handles concurrency.
