## 分支介绍

- [linux_crontab](https://github.com/amoswdh/Linux-Help/tree/linux_crontab) 计划任务


## 阿里云日志服务使用

系统软件安装
软件统一安装在 /export/servers/tools/ 目录下

``` php
mkdir -p /export/servers/tools/ && cd /export/servers/tools/
## 下载脚本区分服务器节点, 以下脚本为 美西节点的安装脚本
## 其他节点参考 https://help.aliyun.com/document_detail/28982.html?spm=a2c4g.11186623.2.5.rmdooP#h2-url-3
wget http://logtail-release-us-west-1.vpc100-oss-us-west-1.aliyuncs.com/linux64/logtail.sh -O logtail.sh; chmod 755 logtail.sh; sh logtail.sh install us-west-1_vpc
```

## 安装完成后, 以管理员身份重启logtail服务
/etc/init.d/ilogtaild stop && /etc/init.d/ilogtaild start


常见问题:
跨账号日志收集问题;  eg. A账号的日志服务收集A账号下的服务器日志. 需要特殊处理授权问题即可;参考(https://www.alibabacloud.com/help/zh/doc-detail/49007.htm)

参考:

https://help.aliyun.com/document_detail/52578.html?spm=a2c4g.11186623.2.4.6Fuxq7