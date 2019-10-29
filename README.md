## GOPROXY Introduction
<img src="https://github.com/snail007/goproxy/blob/master/doc/images/logo.jpg?raw=true" width="200" height="auto"/>
proxy is a high-performance http, https, websocket, tcp, udp, socks5, ss proxy server implemented by golang, supporting forward proxy, reverse proxy, transparent proxy, intranet penetration, TCP/UDP port mapping, SSH relay, TLS Encrypted transmission, protocol conversion, anti-pollution DNS proxy.   

---

[![stable](https://img.shields.io/badge/stable-stable-green.svg)](https://github.com/snail007/goproxy/) [![license](https://img.shields.io/github/license/snail007/goproxy.svg?style=plastic)]() [![download_count](https://img.shields.io/github/downloads/snail007/goproxy/total.svg?style=plastic)](https://github.com/snail007/goproxy/releases) [![download](https://img.shields.io/github/release/snail007/goproxy.svg?style=plastic)](https://github.com/snail007/goproxy/releases) 

---
### [点击我观看视频教程](https://space.bilibili.com/472844633)
- [中文说明](https://github.com/snail007/goproxy/blob/master/README_ZH.md)
- [中文手册](https://snail007.github.io/goproxy/manual/zh/)
- [Download](https://github.com/snail007/goproxy/releases)
- [Desktop Edition, Web Console : ProxyAdmin](https://github.com/snail007/proxy_admin_free)
- [Android Edition](/gui/README_ZH.md)
- [SDK](https://github.com/snail007/goproxy-sdk)
- [GORPOXY Manual](https://snail007.github.io/goproxy/manual/)
- [GORPOXY Tutorial](https://snail007.github.io/goproxy)
- [Free version VS commercial version](https://snail007.github.io/goproxy/free_vs_commercial/)

### What can it do?
- Chained proxies, the program itself can be used as an proxies, and if it is set up, it can be used as a secondary proxies or even an N-level proxies.
- Communication encryption, if the program is not a level one proxies, and the upper level proxies is also the program, then the communication between the upper level proxies and the upper level proxies can be encrypted, and the underlying tls high-intensity encryption is used, and the security is featureless.
- Smart HTTP, SOCKS5 proxy, will automatically determine whether the visited website is blocked. If it is blocked, it will use the upstream proxies (provided that the upstream proxies is configured) to access the website; if the visited website is not blocked, in order to speed up the access, the proxies will Direct access to the website without using a upstream proxies.
- Domain name black and white list, more free to control the way the website is accessed.
- Cross-platform, whether you are widows, linux, mac, or even raspberry pie, you can run the proxy very well.
- Multi-protocol support, support for HTTP(S), TCP, UDP, Websocket, SOCKS5 proxy.
- TCP/UDP port forwarding.
- Support intranet penetration, protocol supports TCP and UDP.
- SSH relay, HTTP (S), SOCKS5 proxy supports SSH relay, the upper Linux server does not need any server, a local proxy can be happy online.
- [KCP](https://github.com/xtaci/kcp-go) protocol support, HTTP(S), SOCKS5, SPS proxy supports KCP protocol to transmit data, reduce latency and improve browsing experience.
- Dynamic selection of upstream proxies, through the external API, HTTP (S), SOCKS5, SPS proxies can achieve user-based or IP-based speed limit, connection limit, dynamic access to upstream.
- Flexible upstream allocation, HTTP(S), SOCKS5 proxy can implement user- or IP-based speed limit, connection limit, and upper-level through configuration files.
- Transparent HTTP (S) proxy, in conjunction with iptables, forwards the outgoing 80, 443 traffic directly to the proxy at the gateway, enabling non-aware intelligent router proxy.
- Protocol conversion, which can convert existing HTTP(S) or SOCKS5 or SS proxy into one port and support HTTP(S) and SOCKS5 and SS proxy at the same time. Converted SOCKS5 and SS proxy. If the upstream is SOCKS5 proxy, then UDP is supported. Features while supporting powerful cascading authentication.
- Custom underlying encrypted transmission, http(s)\sps\socks proxy can encrypt tcp data via tls standard encryption and kcp protocol on top of tcp, in addition to support custom encryption after tls and kcp, that is Said custom encryption and tls|kcp can be used in combination, the internal AES256 encryption, you only need to define a password when you use it.
- Underlying compression efficient transmission, http(s)\sps\socks proxy can encrypt tcp data through custom encryption and tls standard encryption and kcp protocol on tcp, and can also compress data after encryption, that is, compression function And custom encryption and tls|kcp can be used in combination.
- Secure DNS proxy, which can secure and prevent pollution DNS queries through encrypted proxy communication between the DNS proxy server provided by the local proxy and the upstream proxy.
- Load balancing, high availability, HTTP(S)\SOCKS5\SPS proxies supports upstream load balancing and high availability, and multiple upstream repeat-P parameters can be used.
- Specify the egress IP. The HTTP(S)\SOCKS5\SPS proxy supports the client to connect with the ingress IP, and uses the ingress IP as the egress IP to access the target website. If the ingress IP is an intranet IP, the egress IP does not use the ingress IP.
- Support speed limit, HTTP(S)\SOCKS5\SPS proxy supports speed limit.
- SOCKS5 proxies supports cascading certification.
- The certificate parameter uses base64 data. By default, the -C, -K parameter is the path of the crt certificate and the key file. If it is the beginning of base64://, then the latter data is considered to be base64 encoded and will be used after decoding.
- Support client IP black and white list, more secure control of client access to proxy service, if black and white list is set at the same time, then only whitelist is effective. Socks / HTTP(S) / SPS / TCP / UDP / DNS / intranet NAT The bridge/intranet NAT the tbridge and supports the client IP black and white list.

### Why do you need it?

- When for some reason we are unable to access our services elsewhere, we can establish a secure tunnel to access our services through multiple connected proxy nodes.
- WeChat interface is developed locally for easy debugging.
- Remote access to intranet machines.
- Play LAN games with your friends.
- I used to play only on the LAN, and now I can play anywhere.
- Replace the sword inside Netnet, show IP internal Netcom, peanut shell and other tools.
- ..

 
The manual on this page applies to the latest version of goproxy. Other versions may not be applicable. Please use the command according to your own instructions.
 

### Joining the organization
[Click to join the gitter](https://gitter.im/go-proxy/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)

[Click to join the TG](https://t.me/snail007_goproxy)

## Download and install 

### Quick installation

0. If your VPS is a Linux 64-bit system, you only need to execute the following sentence to complete the automatic installation and configuration.

Tip: All operations require root privileges.

The free version performs this:

```shell
curl -L https://raw.githubusercontent.com/snail007/goproxy/master/install_auto.sh | bash
```

The commercial version performs this:

```shell
curl -L https://raw.githubusercontent.com/snail007/goproxy/master/install_auto_commercial.sh | bash
```

The installation is complete, the configuration directory is /etc/proxy. For more detailed usage, please refer to the manual directory above to learn more about the features you want to use.
If the installation fails or your vps is not a linux64-bit system, follow the semi-automatic steps below to install:
  
### Manual installation

1. Download the proxy

Download address: https://github.com/snail007/goproxy/releases/latest

Let's take v7.9 as an example. If you have the latest version, please use the latest version of the link. Note that the version number in the download link below is the latest version number.

The free version performs this:

```shell
Cd /root/proxy/
Wget https://github.com/snail007/goproxy/releases/download/v7.9/proxy-linux-amd64.tar.gz
```

The commercial version performs this:

```shell
Cd /root/proxy/
Wget https://github.com/snail007/goproxy/releases/download/v7.9/proxy-linux-amd64_commercial.tar.gz
```

2. Download the automatic installation script

The free version performs this:

```shell
Cd /root/proxy/
Wget https://raw.githubusercontent.com/snail007/goproxy/master/install.sh
Chmod +x install.sh
./install.sh
```

The commercial version performs this:

```shell
Cd /root/proxy/
Wget https://raw.githubusercontent.com/snail007/goproxy/master/install_commercial.sh
Chmod +x install_commercial.sh
./install_commercial.sh
```

## TODO
- http,socks proxy multiple upstream load balancing?
- http(s) proxy to increase pac support?
- Welcome to add group feedback..

## License
Proxy is licensed under GPLv3 license.

## Contact
Official QQ exchange group: 42805407

## Donation
If the proxy helps you solve a lot of problems, you can better support the proxy through the donation below.

BTC  ADDRESS: `1BJcBhGhREiz1q3VTYoiVPuAZy5PGxRG9z`

<img src="https://raw.githubusercontent.com/snail007/goproxy/master/docs/img/btc.png" width="150" height="auto"/>  

ETH  ADDRESS: `0x0fA4c567768d2E59E6221152EA52F4842866AFC8`

<img src="https://raw.githubusercontent.com/snail007/goproxy/master/docs/img/eth.png" width="150" height="auto"/>  

### Source code declaration

The author of this project found that a large number of developers based on the project for secondary development or using a large number of core code of the project without complying with the GPLv3 agreement, which seriously violates the original intention of using the GPLv3 open source agreement in this project. In view of this situation, the project adopts the source. The code delays the release strategy, to a certain extent, to curb these behaviors that do not respect open source and do not respect the labor results of others.
This project will continue to update the iterations and continue to release the full platform binary program, providing you with powerful and convenient proxies tools.
If you have customized, business needs, please send an email to `arraykeys@gmail.com`


## GOPROXY简介
<img src="https://github.com/snail007/goproxy/blob/master/doc/images/logo.jpg?raw=true" width="200" height="auto"/>  
Proxy是golang实现的高性能http，https，websocket，tcp，udp，socks5，ss代理服务器，支持正向代理、反向代理、透明代理、内网穿透、TCP/UDP端口映射、SSH中转、TLS加密传输、协议转换、防污染DNS代理，API认证，限速，限连接数。官方QQ交流群: 42805407。

---

[![stable](https://img.shields.io/badge/stable-stable-green.svg)](https://github.com/snail007/goproxy/) [![license](https://img.shields.io/github/license/snail007/goproxy.svg?style=plastic)]() [![download_count](https://img.shields.io/github/downloads/snail007/goproxy/total.svg?style=plastic)](https://github.com/snail007/goproxy/releases) [![download](https://img.shields.io/github/release/snail007/goproxy.svg?style=plastic)](https://github.com/snail007/goproxy/releases)  

---
### [点击我观看视频教程](https://space.bilibili.com/472844633)
- [点击下载](https://github.com/snail007/goproxy/releases)
- 如果上面不能正常下载，点击这里[镜像下载](https://www.host900.com/snail007/goproxy/)
- [桌面版，控制面板ProxyAdmin](https://github.com/snail007/proxy_admin_free/blob/master/README_ZH.md)
- [安卓版](https://github.com/snail007/goproxy-ss-plugin-android) 
- [SDK](https://github.com/snail007/goproxy-sdk)
- [GORPOXY帮助手册](https://snail007.github.io/goproxy/manual/zh/) 
- [GORPOXY实战教程](https://snail007.github.io/goproxy)  
- [免费版VS商业版](https://snail007.github.io/goproxy/free_vs_commercial/)

### 它能干什么？
- 链式代理，程序本身可以作为一级代理，如果设置了上级代理那么可以作为二级代理，乃至N级代理。  
- 通讯加密，如果程序不是一级代理，而且上级代理也是本程序，那么可以加密和上级代理之间的通讯，采用底层tls高强度加密，安全无特征。  
- 智能HTTP，SOCKS5代理，会自动判断访问的网站是否屏蔽，如果被屏蔽那么就会使用上级代理(前提是配置了上级代理)访问网站;如果访问的网站没有被屏蔽，为了加速访问，代理会直接访问网站，不使用上级代理。  
- 域名黑白名单，更加自由的控制网站的访问方式。  
- 跨平台性，无论你是widows，linux，还是mac，甚至是树莓派，都可以很好的运行proxy。  
- 多协议支持，支持HTTP(S)，TCP，UDP，Websocket，SOCKS5代理。  
- TCP/UDP端口转发。  
- 支持内网穿透，P2P传输，协议支持TCP和UDP，针对HTTP的优化穿透。  
- SSH中转，HTTP(S)，SOCKS5代理支持SSH中转，上级Linux服务器不需要任何服务端，本地一个proxy即可开心上网。  
- [KCP](https://github.com/xtaci/kcp-go)协议支持，HTTP(S)，SOCKS5代理支持KCP协议传输数据，降低延迟，提升浏览体验。  
- 动态选择上级代理，通过外部API，HTTP(S)，SOCKS5，SPS代理可以实现基于用户或者IP的限速，连接数限制，动态获取上级。
- 灵活的上级分配，HTTP(S)，SOCKS5，SPS代理可以通过配置文件实现基于用户或者IP的限速，连接数限制，指定上级。
- 反向代理，支持直接把域名解析到proxy监听的ip，然后proxy就会帮你代理访问需要访问的HTTP(S)网站。  
- 透明HTTP(S)代理，配合iptables，在网关直接把出去的80，443方向的流量转发到proxy，就能实现无感知的智能路由器代理。  
- 协议转换，可以把已经存在的HTTP(S)或SOCKS5或SS代理转换为一个端口同时支持HTTP(S)和SOCKS5和SS代理，转换后的SOCKS5和SS代理如果上级是SOCKS5代理，那么支持UDP功能，同时支持强大的级联认证功能。
- 自定义底层加密传输，http(s)\sps\socks代理在tcp之上可以通过tls标准加密以及kcp协议加密tcp数据，除此之外还支持在tls和kcp之后进行自定义加密，也就是说自定义加密和tls|kcp是可以联合使用的，内部采用AES256加密，使用的时候只需要自己定义一个密码即可。
- 底层压缩高效传输，http(s)\sps\socks代理在tcp之上可以通过自定义加密和tls标准加密以及kcp协议加密tcp数据，在加密之后还可以对数据进行压缩，也就是说压缩功能和自定义加密和tls|kcp是可以联合使用的。
- 安全的DNS代理，可以通过本地的proxy提供的DNS代理服务器与上级代理加密通讯实现安全防污染的DNS查询。
- 负载均衡，高可用，HTTP(S)\SOCKS5\SPS代理支持上级负载均衡和高可用，多个上级重复-P参数即可。  
- 指定出口IP，HTTP(S)\SOCKS5\SPS代理支持客户端用入口IP连接过来的，就用入口IP作为出口IP访问目标网站的功能。如果入口IP是内网IP，出口IP不会使用入口IP
- 支持限速，HTTP(S)\SOCKS5\SPS代理支持限速。  
- SOCKS5代理支持级联认证。  
- 证书参数使用base64数据，默认情况下-C，-K参数是crt证书和key文件的路径，如果是base64://开头，那么就认为后面的数据是base64编码的，会解码后使用。  
- 支持客户端IP黑白名单，更加安全的控制客户端对代理服务的访问，如果黑白名单同时设置，那么只有白名单生效。socks/http(s)/sps/tcp/udp/dns/内网穿透bridge/内网穿透tbridge，都支持客户端IP黑白名单。 

### 为什么需要它？

- 当由于某某原因，我们不能访问我们在其它地方的服务，我们可以通过多个相连的proxy节点建立起一个安全的隧道访问我们的服务。  
- 微信接口本地开发，方便调试。  
- 远程访问内网机器。  
- 和小伙伴一起玩局域网游戏。  
- 以前只能在局域网玩的，现在可以在任何地方玩。  
- 替代圣剑内网通，显IP内网通，花生壳之类的工具。  
- ..。  

 
本页手册适用于最新版goproxy，其他版本可能有的地方不再适用，请自己根据命令帮助使用。  
 

### 加入组织  
[点击加入交流组织gitter](https://gitter.im/go-proxy/Lobby?utm_source=share-link&utm_medium=link&utm_campaign=share-link)  

[点击加入交流组织TG](https://t.me/snail007_goproxy)  

## 下载安装 

### 快速安装

0.如果你的VPS是linux64位的系统，那么只需要执行下面一句，就可以完成自动安装和配置.

提示:所有操作需要root权限。 

免费版执行这个：  

```shell  
curl -L https://raw.githubusercontent.com/snail007/goproxy/master/install_auto.sh | bash  
```  

商业版执行这个：  

```shell  
curl -L https://raw.githubusercontent.com/snail007/goproxy/master/install_auto_commercial.sh | bash  
```  

安装完成，配置目录是/etc/proxy，更详细的使用方法请参考上面的手册目录，进一步了解你想要使用的功能。  
如果安装失败或者你的vps不是linux64位系统，请按照下面的半自动步骤安装:  
  
### 手动安装  

1.下载proxy

下载地址:https://github.com/snail007/goproxy/releases/latest   

下面以v7.9为例，如果有最新版，请使用最新版链接，注意替换下面的下载连接里面的版本号为最新版版本号。  

免费版执行这个：  

```shell  
cd /root/proxy/  
wget https://github.com/snail007/goproxy/releases/download/v7.9/proxy-linux-amd64.tar.gz  
```  

商业版执行这个：  

```shell  
cd /root/proxy/  
wget https://github.com/snail007/goproxy/releases/download/v7.9/proxy-linux-amd64_commercial.tar.gz  
```  

2.下载自动安装脚本

免费版执行这个：  

```shell  
cd /root/proxy/  
wget https://raw.githubusercontent.com/snail007/goproxy/master/install.sh  
chmod +x install.sh  
./install.sh  
```  

商业版执行这个：  

```shell  
cd /root/proxy/  
wget https://raw.githubusercontent.com/snail007/goproxy/master/install_commercial.sh  
chmod +x install_commercial.sh  
./install_commercial.sh  
```  

## TODO  
- http，socks代理多个上级负载均衡?
- http(s)代理增加pac支持?
- 欢迎加群反馈..。  

## License  
Proxy is licensed under GPLv3 license。  

## Contact  
官方QQ交流群: 42805407  

## Donation  
如果proxy帮助你解决了很多问题，你可以通过下面的捐赠更好的支持proxy。  
<img src="https://github.com/snail007/goproxy/blob/master/doc/images/alipay.jpg?raw=true" width="200"  height="auto"/>  
<img src="https://github.com/snail007/goproxy/blob/master/doc/images/wxpay.jpg?raw=true" width="200"  height="auto"/>  

### 源代码申明

本项目作者发现大量的开发者基于本项目进行二次开发或使用大量本项目核心代码而不遵循GPLv3协议，这严重违背了本项目使用GPLv3开源协议的初衷，鉴于这种情况，本项目采取源代码延迟发布策略，在一定程度上遏制这些不尊重开源，不尊重他人劳动成果的行为。  
本项目会持续更新迭代，持续发布全平台的二进制程序，给大家提供强大便捷的代理工具。  
如果你有定制，商业需求请发邮件至`arraykeys@gmail.com`