## 计划脚本

- laravel 框架计划任务.sh示例

``` php
#!/usr/bin/env sh

kill -9 `ps -ef | grep 'erp:timeliness_statistics' | grep -v grep | awk '{print $2}'`
ps -ef | grep 'erp:timeliness_statistics' | grep -v grep
if [ $? -eq 0 ];then
	sleep 1
	echo "It is running ...do not run it again!"
	exit 1
else
	echo "Running erp:timeliness_statistics ..."
	cd /export/data/tomcatRoot/customer.orderplus.com
	APP_ENV=production /export/servers/php/bin/php artisan erp:timeliness_statistics
fi
```

-- 手动执行 .sh
<p>
输入命令：jobs
终端显示：[1]+ Stopped vim /etc/network/interfaces > /home/leo/Desktop/ip.txt (wd: /)


继续输入命令：jobs -l
终端显示：[1]+ 4664 停止 vim /etc/network/interfaces > /home/leo/Desktop/ip.txt (wd: /)

看到4664,这个就是PID了

现在开始杀掉它：
输入命令:kill 4664
终端没有显示。ok。


再用jobs命令查看，确认已经杀掉了。
</p>
-- 计划任务示例
``` php
00 15 * * * /export/scripts/erp_timeliness_statistics.sh >> /export/logs/support.orderplus.com/erp_timeliness_statistics.log 2>&1
```
时间从左向右分别代表 分钟、小时、几号、月份、星期


