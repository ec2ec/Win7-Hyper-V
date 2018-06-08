# Win7-Hyper-V 客户端远程管理

### 当我们尝试使用Win7 Hyper-V客户端连接工作组中的Hyper-V服务器虚拟机时，

>报错：你没有完成此任务所需的权限，请与计算机XXX授权策略的管理员联系。

### 解决方法步骤：

1. 首先需要 `Hyper-V服务器`与 `Win7` 上拥有一个相同的 `账户，密码`。

2. 下载HVRemote.wsf脚本

3. 下载完毕后，将hvremote.wsf存放至本地目录

4. 以管理员身份运行cmd.exe。

5. 改变cscript的运行方式，因为HVRemote工具无法在系统默认的WScript 模式下执行。

     在命令提示符中运行`HVRemote /AnonDCOM:grant`命令。

6. 使用CMDKEY命令，将能连接到Hyper-V服务的账号和密码存储在本地。

     格式为：cdmkey /add:服务器名   /user:用户名   /pass:密码   
     cmdkey /list 查看密码是否已存储。

7. 在Hosts文件中，添加Hyper-V服务器主机名与IP地址的映射。


### 注意：
1. 在调用hvremote.wsf时候，杀毒软件可能会阻止，需要做相应处理。

