---
title: Let's Encrypt
date: 2016-12-21 11:47:39
tags:
---

### 使用Let's Encrypt生成免费SSL证书

官网：[Let's Encrypt](https://letsencrypt.org/)

Let's Encrypt是由互联网安全研究小组（ISRG，一个公益组织）提供的服务。提供免费、自动化、开放的证书签发服务。

Let's Encrypt颁发的证书有期是90天，需要在过期前进行续期，好在Let's Encrypt已经提供了自动续期的脚本。

官网推荐使用[Certbot](https://certbot.eff.org/)工具来部署Https证书。在Certbot首页上选择Web服务器及服务器OS类型，我们在这里以Nginx + CentOS 6为例来说明。

原文链接：[https://certbot.eff.org/#centos6-nginx](https://certbot.eff.org/#centos6-nginx)

0. #### 生成证书

	0. 安装证书生成工具certbot-auto：

		```
		wget https://dl.eff.org/certbot-auto
		chmod a+x certbot-auto
		```
	0. 安装依赖

		运行```./certbot-auto```，安装所有依赖项。过程中可能会提示```Virtualenv Command Not Found```，需要[安装pip](https://pip.pypa.io/en/stable/installing/)、virtualenv包：```pip install virtualenv```。

	0. 配置Nginx
		
		为需要配置https的站点添加以下配置，将访问/.well-known的请求指向本地目录。Let's Encrypt在生成证书的过程中，会在/var/www/www.xxx.com/.well-known目录生成一个临时文件，并且会访问类似于http://www.xxx.com/.well-known/acme-challenge/HGr8U1IeTW4kY_Z6UIyaakzOkyQgPr_7ArlLgtZE8SX的url，来检查域名配置是否有效。

		添加以下配置，并重启Nginx：nginx -s reload，如果reload不生效，可以试试restart。
		
		```
		server {

			...			

			location /.well-known {
	        	alias /var/www/www.xxx.com/.well-known;
	    	}

			...

		}
		```

		*即使证书生成之后，也需要保留Nginx的这一个配置，因为证书的续期还需要这一个配置。*

	0. 通过向导生成证书

		运行```./certbot-auto certonly```，会通过向导方式一步一步来生成证书。过程中间会用到上一步在Nginx中配置的本地目录。

		**对证书生成过程和原理比较熟悉的话，可以不使用向导方式，直接使用certbot-auto命令```./certbot-auto certonly --webroot -w /var/www/www.xxx.com -d xxx.com -d www.xxx.com -w /var/www/thing -d thing.is -d m.thing.is```可以快速高效地生成证书**

		生成的证书默认在/etc/letsencrypt/live/www.xxx.com/目录。

0. #### 配置Nginx使用证书

	添加以下配置，并重启Nginx：```nginx -s reload```，如果reload不生效，可以试试restart。

	```
	server {

		...
		listen 443;

	    ssl on;
        ssl_stapling_verify on;
        ssl_certificate         /etc/letsencrypt/live/www.xxx.com/fullchain.pem;
        ssl_certificate_key     /etc/letsencrypt/live/www.xxx.com/privkey.pem;

		...

	}
	```

0. #### 检查证书的有效性

	打开浏览器，检查证书的有效性。

0. #### 证书续期

	Let's Encrypt颁发的证书有期是90天，需要在过期前进行续期，好在Let's Encrypt已经提供了自动续期的脚本。

	官网说明，可以一天调用两次，如果检测到证书不需要更新，是什么都不做的，以减少意外造成的故障。

	先运行```certbot-auto renew --dry-run```命令检查证书自动续期是否正常，如果正常，将```certbot-auto renew --quiet```命令添加到系统的计划任务cron中，就可以实现证书自动续期了。

	```
	01 1 * * * ./path/to/certbot-auto renew --quiet
	```
	表示每天的1点1分自动执行续期脚本。





