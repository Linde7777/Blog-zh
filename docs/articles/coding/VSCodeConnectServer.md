# 连接服务器
官方的连接教程太长，这里有个简短视频版本https://youtu.be/7kum46SFIaY?t=59  

上面教程的文字版本：
1. 进入插件商店，搜索remote，安装该插件 
2. 在你的虚拟机的终端中输入sudo apt install openssh-server
3. 选择SSH链接
![image](https://user-images.githubusercontent.com/69742577/160222467-208a64e6-e906-4661-9cd9-bc768ffeb31f.png)  

4. 点击这个+号，输入```ssh 用户名@ip地址```。用户名和地址是啥？去看你的服务器提供商的远程链接教程，里面有。
![image](https://user-images.githubusercontent.com/69742577/160222504-96654cf6-2c69-4f08-8ce2-e3347d51bd1c.png)  

# 连接本地虚拟机
跟上面一样，唯一的区别在于你需要在虚拟机的命令行里输入```ip address```获取该虚拟机的ip地址。  

# 补充
别忘了把这台服务器的ssh添加到你的github上，如果你忘了怎么操作：https://www.liaoxuefeng.com/wiki/896043488029600/896954117292416  

有时候git clone会失败，等一会就可以了。  

# 疑难解答
问题描述：第一次用VS Code连接成功，后面因为其他原因要重装虚拟机，按照上面的步骤连接，但VS Code连不上了，用Putty反而可以。  

解决方案：报错里有一个路径，类似于C:\Users\LENOVO\.ssh ，进入这个路径
1. 用记事本或者VS Code打开known_hosts，把包含你重装的虚拟机的ip那一条删掉
2. 打开同一目录下的config，把包含你重装的虚拟机的ip的那三行删掉。
3. 问题解决，按照原来的方法连接即可。  