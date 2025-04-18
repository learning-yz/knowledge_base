NPM（Node Package Manager）用于安装、更新、移除和管理Node.js packages或者说modules（简称npm包）。安装Node.js的时候会自动安装NPM。

## Common Commands
**1. 安装包** ：  
  `npm install -g <package name>` 是全局安装，用`-g`或者`--global`表示。  
  `npm install <package name>` 是本地安装，命令在项目根目录下执行，把包安装到项目`node_modules`目录下。  
  `npm install <package name> --save-dev` 是安装一个仅开发时需要的包，包会出现在项目的`package.json`文件的`devDependencies`中。    
  `npm install <package name> --save-exact`是保存包的确切版本，而不是包的版本范围。执行命令后可在生成的`package-lock.json`中查看包的确切版本。  
  `npm install` 在不指定具体package name的时候，会安装目录下`package.json`文件中列出的所有依赖包。  
  上述命令有一些简写方法。  
  `npm i`相当于`npm install` 。  
  `npm i -D`相当于`npm install --save-dev` 。  
  `npm i -E`相当于`npm install --save-exact`。  
**2. 移除包** ：  
  `npm uninstall <package name>`  
**3. 查看安装包的版本**：  
  `npm list <pacakge name>`会查看已安装的指定的包的版本。  
  `npm list`会查看所有本地包的版本。  
**4. 查看包的最新可安装版本**：  
  `npm view <package name> version`  
  `npm view <package name> versions`可以列出包的所有可用版本，但是命令执行耗时较长。    
**5. 执行本地或者远程npm包中可执行文件** ：  
  `npx <pkg>[@<version>]`   
   NPX（Node Package eXecute）一般用于一次性命令，比如创建项目。 零安装执行。  
   *创建Next.js应用*：`npx create-next-app@latest`     
   *创建Remix应用*：`npx create-remix@latest`   
**6.  构建项目包** ：    
  `npm run build`，在项目目录下执行该命令，该项目目录下必须包含一个`package.json`文件。它会调用`package.json`文件中`scripts`中对应的`build`命令来构建。  
  
   