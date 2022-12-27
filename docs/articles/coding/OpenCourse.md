# 建议
~~母语不是英语的老师，说话反而更容易让人听懂，他们一般没有过快的语速，没有很多连读， 比如CS186 Fall 2020的两位老师。~~ 我得承认印度英语有时候不太容易听懂  

建议用Anki记录课后习题的错题，Windows的截屏键是Shift+win+S，截屏后Ctrl+V即可粘贴  

大多数不公开的课程视频都能在B站上找到，没有字幕的视频，可以用Chrome自带的实时字幕功能：Settings->Advanced->Accessibility->Live Caption    

先Fork官方给出的代码，再克隆到自己的本地，这样省事点。如果你是直接从官方克隆仓库到本地，你可以用以下步骤：  
1. Fork官方仓库，你会得到官方仓库的一个副本，它现在是你的仓库了！
2. 复制你的仓库的SSH链接
3. 在你的本地仓库输入`git remote -v`查看你的remote链接，确认你的remote链接是官方仓库的，接下来我们要替换这个链接。
4. 在本地仓库输入`git remote set-url origin 你复制的SSH链接`，再输入`git push -f`，`-f`会让你的本地仓库的内容强制覆盖你远程仓库的内容  

# 资料
https://github.com/PKUFlyingPig 飞猪的仓库里有很多公开课资料  

https://conanhujinming.github.io/comments-for-awesome-courses/  名校公开课程评价网  

https://github.com/izackwu/TeachYourselfCS-CN/blob/master/TeachYourselfCS-CN.md TeachYourselfCS