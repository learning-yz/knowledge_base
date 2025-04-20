A crontab file contains instructions for the cron daemon following simplified manner: "run this command at this time this date".

## Common Commands
**1. 安装（以Ubuntu为例）** ：`apt-get install cron`  
**2. 查看cron状态** ： `service crond status`  
**3. 启动cron**：`service cron start`  
**4. 关闭cron**：`service cron stop`  
**5. 重启cron**：`service cron restart`  
**6. 设置某个用户的crontab服务**：`crontab -u <user>`  
**7. 编辑某个用户的crontab文件**：`crontab -e`，未指定用户的话，默认编辑当前用户的。  
**8. 查看某个用户的crontab文件**：`crontab -l`，未指定用户的话，默认编辑当前用户的。  
**9. 删除某个用户的crontab文件**：`crontab -r`，未指定用户的话，默认编辑当前用户的。  

## Crontab 文件格式
`* * * * * myCommand`  
第一个`*`表示分钟，值范围为`0-59`；  
第二个`*`表示小时，值范围为`0-23`；  
第三个`*`表示日期，值范围为`1-31`；  
第四个`*`表示月份，值范围为`1-12`或者使用`jan, feb, mar, ...`格式；
第五个`*`表示星期，值范围为`0-6`（`0`表示星期天）或者`1-7`（`7`表示星期天）或者使用`sun, mon, tue, ...`格式；

- 如果是`a~b`这种形式，表示从`a`到`b`之间随机选一个时间点执行。比如`8~11`，表示的是随机从`8, 9, 10, 11`中选一个时间点执行。如果没有数字，仅有`~`符号，表示的是整个值范围中随机选一个时间点执行。
	- `30 4 1~15 * * myCommand`表示每个月的1号到15号随机选一天的凌晨4点30分执行一次命令。
- 如果是`a-b`这种形式，表示的是`a`到`b`之间的每个时间点执行。比如`8-11`，表示的是`8, 9, 10, 11`时间点执行。可以使用`*`表示整个值范围，即每个时间点都执行。
	- `30 4 1-15 * * myCommand`表示每个月1号到15号期间每天的凌晨4点30分执行一次命令。
- 如果是`a, b, c`这种形式，表示的是`a`、`b`、`c`这三个时间点都执行。
	- `30 4 1,15,30 * * myCommand`表示每个月的1号，15号，30号的凌晨4点30分执行一次命令。
	- `30 4 1,15 * 5 myCommand`表示每个月的1号，15号，再加上每周五的凌晨4点30分执行一次命令。
- 如果是`*/<number>`这种形式，表示的是每隔`<number>`个时间段都执行。
	-  `* */2 * * * myCommand`表示每隔2小时执行一次命令。`/2`前面的`*`号也可以用`0-23`来代替，即`0-23/2`，这个命令和`* 0,2,4,6,8,10,12,14,16,18,20,22 * * * myCommand`命令的效果是一样的。