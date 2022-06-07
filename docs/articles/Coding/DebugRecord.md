### 先判断再赋值还是先赋值再判断？
```
            for (int i = 0; i < k; i++) {
                if (lastNode == null) {
                    return dummy.next;
                }
                lastNode = lastNode.next;
            }
            ListNode next = lastNode.next;
```
这是[Reverse Nodes in k-Group](https://leetcode.cn/problems/reverse-nodes-in-k-group/)中的一个问题。
这样写会导致```ListNode next=lastNode.next```出错，因为lastNode可能为null，null.next是非法的。
要把```if(lastNode==null) return dummy.next``` 和 ```lastNode=lastNode.next```调换一下位置。

### 安装8.0版本的Mysql时在Starting the server步骤卡住
安装5.7版本的Mysql server，问题解决

### 用指针处理int数组
```
  int len = 9;
  int *arr0 = (int *)malloc(sizeof(int) * len);
  int *arr1 = (int *)malloc(sizeof(int) * len);
  
  //wrong version:
  for (int i = 0; i < len; i += 1) {
    *(arr0 + sizeof(int) * i) = i + 1;
    *(arr1 + sizeof(int) * i) = i + 1;
  }

  //correct version:
  for (int i = 0; i < len; i += 1) {
    *(arr0 + i) = i + 1;
    *(arr1 + i) = i + 1;
  }
  
```
写汇编写懵了，C语言的编译器会自动帮你乘上sizeof(int)。  

### Junit Test在Debug模式闪退
在跳出一个循环的时候，Debug模式自动退出，Console显示Junit抛出了一个Timeout Exception。把原作者给出的`@Test(timeout = 1 0000)`的限制改为`@Test(timeout = 1 0000 0000)`后，问题解决。    
奇怪的是执行Junit Test不会抛出Timeout Exception。

### if if if 还是if else if else if?

我平时一直喜欢用
```
if( ) {
}
if( ) {
}
if( ) {
}
```
这种格式写if语句，很少用else，因为我觉得if else叠加次数后很乱。  
不过有时候必须要用if else if，比如下面的代码：
```
if (array[x][y] > target) {
     y -= 1;
}
else if (array[x][y] < target) {
     x += 1;
    }
return false;
```
假设第一个if语句是if(array[3][0]>target)，执行完第一条if语句后，y变为-1，如果进入第二条语句，会产生IndexOutOfBoundaryException  

if if if 判断完一个if语句后，会接着判断下一个if语句。  
![image](https://user-images.githubusercontent.com/69742577/166632801-5e16c5e1-01ca-442b-8478-3155f12bbea2.png)


if else if else只会判断其中的一个if语句  
![image](https://user-images.githubusercontent.com/69742577/166633052-13557f32-fda4-47fd-984d-4998e34dfce2.png)



### 相同的hashcode
```
public static int hashCode(int[] array) {
        int total = 0;
        for (int element : array) {
            total = total * 256;
            total = total + element;
        }
        return total;
    }

public static void main(String[] args) {
    int[] array1 = {80, 103, 142, 91, 160, 250, 7, 7, 7, 7};
    int[] array2 = {130, 105, 209, 7, 7, 7, 7};
    int hashCode1 = hashCode(array1);
    int hashCode2 = hashCode(array2);
    System.out.println("hashCode1: " + hashCode1);//117901063
    System.out.println("hashCode2: " + hashCode2);//117901063

    }
```
这个hashCode()函数会产生相同的hashCode，256=2^8，相乘几次后会溢出，hashCode取决于数组的最后几位数字

### 变化的stack.size()
```
for (int i = 0; i < stack1.size(); i++) {
       stack2.push(stack1.pop());
}
```
for循环写习惯了，干啥都要用for循环。
for循环判断条件中的stack1.size()会随着stack1.pop()变小
应该改为```while(stack1.size>0)```