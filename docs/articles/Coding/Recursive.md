网址：https://codingbat.com/java/Recursion-1  
  
我的答案https://github.com/Linde7777/CodingBat_Recursion1_Solutions

建议先在里面注册个账号（花不了你一分钟的时间），写代码之前记得登录，这样它就会帮你把你的代码保存下来。
第一次接触递归一脸懵逼很正常，我一开始也这样，现在我感觉我的递归写得比以前好很多了。

刚接触递归，你可能很想定义一个变量来存储数据，使用`return 常数+function();` 这种语句，不用声明新的变量（实际上你也不应该声明新变量），就能实现类似static修饰符的效果。
return func(...); 会让函数开始“循环”。
递归函数里面必须设置一个退出条件，比如 `if(n==0) return 123;` 不然函数执行起来的时候就会陷入死循环。