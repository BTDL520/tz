# tz
梯子

1、VPS一台，系统随意，本教程基于Debian 9 的系统。

2、域名一个，并做好解析（若是不需要套用CND就不用到cloudflare关联域名解析服务器，直接在域名提供商那里解析域名）

PS：CDN最近经常抽风，若是撸羊毛的人太多了，难免会崩溃，毕竟是免费的。个人觉得，暂时不需要CDN。

推荐域名注册地址（有隐私保护）：点击访问

推荐国人商家VPS（CN2 GIA洛杉矶）：点击注册

推荐大品牌VPS （CN2 GIA 搬瓦工）：点击注册

Trojan一键安装脚本


安装wget

yum -y install wget    ##ContOS Yum 安装 wget
apt - get install wget    ## Debian Ubuntu安装wget
脚本如下

wget的- ñ -不-检查-证- q - Øtrojan_install 。sh “ https://raw.githubusercontent.com/V2RaySSR/Trojan/master/trojan_install.sh” && chmod + x trojan_install 。sh && bash trojan_install 。SH 
使用工具连接Trojan
这里推荐使用Mellow这个一个工具，这个工具可以实现分流，当然，你若是不习惯，也可以继续使用你的V2rayN连接。
下载地址：点击下载  （ exe为Win客户端  dmg为Mac客户端 ）
作者用的CONF文件

[端点]
; 标签，解析器，解析器-具体PARAMS ...
直接，内置，自由，域策略= UseIP
拒绝，内置，黑洞
Dns - Out ，内置，dns
Http - Out ，内置，http ，地址= 192.168 。100.1 ，端口= 1087 ，用户= myuser ，pass = mypass 
袜子-输出，内置的，袜子，地址= 127.0 。0.1 ，端口= 1080
代理- 1 ，vmess1 ，vmess1 ：// 75da2e14-4d08-480b-b3cb-0079a0c51275@example.com ？：443 /路径网络= WS＆TLS =真ws.host = example.com
代理- 2 ，vmess1 ，vmess1 ：// 75da2e14-4d08-480b-b3cb-0079a0c51275@example.com ？：10025网络= TCP
代理- 3 ，SS ，SS ：// AES-128-GCM：pass@192.168.100.1 ：8888
代理- 4 ，vmess1 ，vmess1 ：// 75da2e14-4d08-480b-b3cb-0079a0c51275@example.com ？：443 /路径网络= HTTP＆http.host = example.com％2Cexample1.com＆TLS =真tls.allowinsecure =真
代理- 7 ，vmess1 ，vmess1 ：// 75da2e14-4d08-480b-b3cb-0079a0c51275@example.com ？：10025网络= KCP＆kcp.mtu = 1350＆kcp.tti = 20＆kcp.uplinkcapacity = 1＆kcp.downlinkcapacity = 2＆kcp.congestion =假头= none＆sockopt.tos = 184
代理- 8 ，vmess1 ，vmess1 ：// 75da2e14-4d08-480b-b3cb-0079a0c51275@example.com ？：10025网络= QUIC＆quic.security =无＆quic.key =＆标题=无＆TLS =假sockopt.tos = 184
 
[ EndpointGroup ]
; 标签，冒号-分隔的列表中选择或端点标签，战略，策略-具体PARAMS ...
组- 1 ，袜子-停止，间隔= 300 ，超时= 6 
 
[路由]
domainStrategy = IPIfNonMatch 
 
[ RoutingRule ]
; 类型，过滤器，端点标记或指定组标记
域名-关键字，地理位置：类别-广告-全部，拒绝 
IP - CIDR ，223.5 。5.5 / 32 ，直接  
IP - CIDR ，8.8 。8.8 / 32 ，组- 1  
IP - CIDR ，8.8 。4.4 / 32 ，组- 1  
PROCESS - NAME ，木马。exe文件，直接 
GEOIP ，cn ，直接 
GEOIP ，私人，直接  
PORT ，123 ，直  
DOMAIN - KEYWORD ，geosite ：CN ，直接 
域名，www 。谷歌。COM ，集团- 1 
DOMAIN - FULL ，WWW 。谷歌。COM ，集团- 1 
DOMAIN - SUFFIX ，google 。COM ，集团- 1 
最后，集团- 1 
 
[ Dns ]
; 劫持= dns端点标记
劫持=的dns -输出 
; cliengIp = ip
clientIp = 114.114 。114,114 
 
[ DnsServer ]
; 地址，端口，标签
本地主机
223.5.5.5
8.8 。8.8 ，53 ，远程  
8.8.4.4
 
[ DnsRule ]
; 类型，过滤器，dns服务器标签
DOMAIN - KEYWORD ，geosite ：地理位置- ！CN ，远程 
DOMAIN - SUFFIX ，google 。COM ，远程 
 
[ DnsHost ]
; 域= ip
doubleclick.net = 127.0.0.1
 
[日志]
loglevel =警告
