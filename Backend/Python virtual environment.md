
## 使用[venv](https://docs.python.org/3/library/venv.html)创建Python虚拟环境
**创建虚拟环境**： `python -m venv <virutal environment path>`  
**激活虚拟环境（Windows环境）**：`<virtual environment path>\Scripts\activate`  
**在虚拟环境下安装package**：`<virtual environment path>\Scripts\python.exe -m pip install <package name>`，当然如果已经激活虚拟环境了，可以直接执行`python install <package name>`。  

## 使用[conda](https://github.com/conda/conda)创建Python虚拟环境
**检查conda的版本**：`conda --version`  
**查看conda创建的虚拟环境列表**：`conda info --envs`或者`conda env list`  
**更改某个虚拟环境中的Python版本**：`conda install python=<version number> -n <env name>`  
**更新某个虚拟环境中的Python版本**：`conda update python`  
**创建特定Python版虚拟环境**：`conda create --name <env name> python=<version number>`  
**激活某个虚拟环境**：`conda activate <env name>`  
**退出某个虚拟环境**：`conda deactivate <env name>`  
**删除某个虚拟环境**：`conda remove --name <env name> --all`  
**查看当前虚拟环境下安装的package列表**：`conda list`  
**在当前虚拟环境下安装package**：`conda install pkg_name=<version number>`  
**更新当前虚拟环境下所有的package**：`conda update --all`  
**添加国内的镜像来加快package的安装速度**：
```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
```
**检查conda的配置**：`conda config --show`  
**设置搜索时显示通道地址**：`conda config --set show_channel_urls yes`  

## requirements.txt文件的使用和生成
**安装requirements.txt文件中的package**：`pip install -r requirements.txt`  
**自动生成requirements.txt文件**：  
首先进入项目目录，然后执行以下命令会在项目目录下生成requirements.txt文件。  
- **方法一**：`pip freeze > requirements.txt`
- **方法二**：`pipreqs --encoding utf-8 .`  