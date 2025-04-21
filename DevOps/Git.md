## Common Commands
**1. 克隆项目**：`git clone <repo address>`  
**2. 查看远程所有branch**：`git branch -r`  
**3. 创建本地branch追踪远程仓库origin对应的branch**：`git checkout -b <local branch name> origin/<remote branch name>`  ，通常`<local branch name>`和`<remote branch name>`设为同一个名字，即本地和远程branch同名。  
**4. 同步远程branch到本地对应的branch**：  
- 方法一：  
```
git checkout <local branch name>
git pull origin <remote branch name>
```
`git pull`会从远程仓库origin拉取branch的更新，并合并到当前的本地branch中。  
- 方法二：  
```
git fetch origin
git checkout <local branch name>
git merge origin/<remote branch name>
```
`git fetch`会从远程仓库origin获取所有branch的更新，但是不会自动合并到本地branch。使用`git merge`将远程branch的更新合并到当前的本地branch中。  