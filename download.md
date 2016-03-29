---
layout: page
title: Download
permalink: /download/
---

CHM 格式电子文档下载
-----

https://sourceforge.net/projects/netkiller/files/htmlhelp.chm/

YUM 在线安装
-----

http://netkiller.sourceforge.net/pub/repo/

		
# cat >> /etc/yum.repos.d/netkiller.repo <<EOF
[netkiller]
name=Netkiller Free Books
baseurl=http://netkiller.sourceforge.net/pub/repo/
enabled=1
gpgcheck=0
gpgkey=
EOF
		
		
查找包

		
# yum search netkiller

netkiller-centos.x86_64 : Netkiller centos Cookbook
netkiller-cryptography.x86_64 : Netkiller cryptography Cookbook
netkiller-docbook.x86_64 : Netkiller docbook Cookbook		
		
		
安装包

yum install netkiller-docbook		
		
RPM 安装包

http://rpmfind.net/linux/RPM/sourceforge/n/ne/netkiller/netkiller-1.0.1-1.x86_64.html

deb:

https://sourceforge.net/projects/netkiller/files/Package/

GITUB

GIT clone:

		
$ git clone	https://github.com/netkiller/netkiller.github.com.git
		
		
Document URL
-----

Home: http://netkiller.github.io/

Mirror: http://netkiller.sourceforge.net/
