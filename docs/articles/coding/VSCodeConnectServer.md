# 连接服务器
官方的连接教程太长，这里有个简短视频版本https://youtu.be/7kum46SFIaY?t=59  

上面教程的文字版本：
1. 进入插件商店，搜索remote，安装该插件  
2. 选择SSH链接
![image](https://user-images.githubusercontent.com/69742577/160222467-208a64e6-e906-4661-9cd9-bc768ffeb31f.png)  

3. 点击这个+号，输入```ssh 用户名@ip地址```。用户名和地址是啥？去看你的服务器提供商的远程链接教程，里面有。
![image](https://user-images.githubusercontent.com/69742577/160222504-96654cf6-2c69-4f08-8ce2-e3347d51bd1c.png)  

# 连接本地虚拟机
跟上面一样，唯一的区别在于你需要在虚拟机的命令行里输入```ip address```获取该虚拟机的ip地址。  
如果这个虚拟机出问题了，尽量不要删了重装，删了就很难用VS Code连回去了，只能用PuTTY。  