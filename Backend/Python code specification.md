## Module Import
**Bad**：
```
from <package name> import *
```
**Better**：
```
from <package name> import <module name>
```
**Good**：
```
import <package name>
import <very>.<deep>.<module name> as <short module name>
```

## `__init__.py`文件
一个有`__init__.py`文件的目录会被认为是一个Python包。从Python3.3开始即使没有`__init__.py`文件也可以被识别为包（称为“隐式命名空间包”），但推荐在写包时包含该文件。  
`__init__.py`文件中可以包含初始化代码。当`import <package name>.<module name>`的时候，会先在`<package name>`目录下寻找`__init__.py`文件，执行该文件里面的内容，然后再寻找`<package name>/<module name>.py`文件，执行`<module name>.py`文件里面的内容。  
如果一个`package`下面没有`modules`或者`sub-packages`没有共享代码的话，`__init__.py`文件内容为空即可。  
注：`module`（模块）就是Python脚本文件，`package`（包）就是组织模块的方式。`package`可以包含多个`modules`和`sub-packages`（子包）。

