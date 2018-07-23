# cli
    
## description
>CLI（command-line interface 命令行界面）是指在图形用户界面得到普及之前使用最为广泛的用户界面，
它通常不支持鼠标，用户通过键盘输入指令，计算机接收到指令后，予以执行。也有人称之为字符用户界面（CUI）。
 
## 开发 --demo

1. 进入开发目录执行 npm init
   将会创建 package.json和默认的配置。当然手动创建也没有问题。 

2. 在package.js文件中，需要新增配置项
   ```json
       "bin":{
           "node-cli": "bin/index.js"
       }
   ```
   其中node-cli是需要执行的命令名，bin/index.js是命令所调用的文件

3. 可以在bin/index.js 写入
    ```js
        #!/usr/bin/env node     // 指定脚本的解释程序为node
        console.log('my cli')
    ```  
4. 在开发目录执行 npm link （创建软连接）
   npm link命令通过链接目录和可执行文件，实现npm包命令的全局可执行。
   这样我们可以在任何地方执行 node-cli命令
   >参考：[npm link description](https://blog.csdn.net/juhaotian/article/details/78672390)
    
5. 发布: 本地调试成功后，我们需要发布到npm上面
   >npm: [URL](https://www.npmjs.com/)
     1. 本地登陆 npm login //输入以下命令，会提示输入用户名、密码、邮箱，这些都是注册时填写过的。    
     2. npm publish // package.json同级目录下执行
     3. TODO: package.json内的name即为我们的包名称 version为版本（每次publish都要修改version为更大）
   

