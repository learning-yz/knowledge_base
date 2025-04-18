## Common Commands
**1. 创建Project**： 
  `django-admin startproject <project name> . `
  注意命令最后的`.` ，这表示在当前的目录下创建Project。
**2. 启动Project**： 
  python manage.py runserver` 
**3. 创建App**： 
  `python manage.py startapp <app name>` 
  一个App可以理解为是某个功能模块，而一个Project下面可以包含多个App，这些App共同服务于这个Project。当然一个App也可以被多个Project所用，即App复用的概念。
**4. 为App下的数据变化生成迁移代码** ：
  `python manage.py makemigrations <app name>`
  该命令一般会在修改该app目录下的models.py文件后执行，会为models.py中的变化在Migration目录下生成数据库相关的python代码
**5. 查看数据迁移`python`代码对应的`SQL`代码**：
  `python manage.py sqlmigrate <app name> <migration number>`
  `<migration number>` 即想查看的数据迁移python代码文件名中的数字。
**6. 实际更新数据库** ：
  `python manage.py migrate`
   在实际更新之前建议先运行`python manage.py check`进行检查后再执行上面的代码。
**7. 打开python命令行**：
  `python manage.py shell`
   比起直接用`python`启动的命令行，该命令会预先`import`该Project的设置，这让我们可以使用一些数据库访问的API。
**8. 创建超级用户**：
  `python manage.py createsuperuser`
**9. 测试App**：
  `python manage.py test <app name>`
   该命令会寻找该App下面的测试文件（通常以tests开头），并进行测试。

## Time Zone Settings
为了时间的正确，需要在`settings.py`文件中设置`TIME_ZONE`变量。中国可以设置为`Asia/Shanghai`。其他国家的时间设置可以参考这个[链接](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)
