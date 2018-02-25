# JS

[TOC]

由布兰登艾奇发明

包括：ECMAscript：基础语法

​	    BOM：浏览器对象模型

​	    DOM：文档对象模型



## 能够干什么？

- 动态效果
- 数据验证
- 使用ajax
- 能够制作游戏等实现逻辑处理
- 能够使用cookie



## JS是什么？

​	JavaScript是一种基于事件和对象驱动的解释型、松散型的语言。

​	解释型：由浏览器解释运行

​	松散型：非严格类型，不用明确指定数据类型



## 如何引入

- 外部引入：<script src="lianxi.js"></script>
- script标签对
- 重定向：<a href="javascript:alert(1);">重定向</a>
- 行内样式：<a href="" onclick="alert(1)">行内</a>



## 调试

```
alert(1);以对话框的形式弹出括号里的内容
```

```
console.log(1);以控制台的方式输出值
```

```
console.dir(1);以控制台的方式输出结构
```

```
document.write('将括号内的内容写到文档中');
document.write('<b>可以识别标签</b>');
document.write('<a href="">这是a标签</a>');
```



## 变量

> 变量是内存里面的一块地址单元

####	定义方式

* 先声明后使用

  ```
  let box;    //定义一个变量box
  console.log(box);   //输出box中的值
  ```

* 声明的同时赋值

  ```
  let sum=200;    //声明一个sum变量，并赋给sum一个初始值200
  ```


* 同时声明多个变量时，中间用逗号隔开

  ```
  let sum,a,b;    //同时声明3个变量
  ```

#### 变量命名注意

* 不能以关键字或者是保留字命名
* 不能以数字开头
* 以数字、字母、下划线、$构成
* 严格区分大小写 （html、css、汇编不区分大小写）
* 变量的命名要有意义
* 变量以首字母大写的方式和驼峰命名法来命名

#### 注意

* 先声明后使用
* 一个变量，只声明没有赋值，默认值为undefined
* 变量不能被重复声明
* 若一个变量，没有声明但是赋值了，那么这个变量就会被当作一个全局变量来处理，不会报错



## 常量

> 不能被改变的量
>
> 必须在声明的时候初始化



## 数据类型

> *<u>两者的划分是依据在内存中存储位置的不同来划分的</u>*
>
> *<u>所以在使用引用数据类型的时候，一定要注意传递的是地址</u>*
>
> *<u>在使用基础数据类型的时候，注意，传递的是值</u>*

#### 初始数据类型

* Number  数值类型

  ```
  let num=0b10;   //二进制用0b或0B表示
  console.log(num);	//输出2
  let nub=0x10;	//十六进制
  console.log(nub);	//输出16
  let nub=0o10;	//八进制
  console.log(nub);	//输出8
  ```

  加权算法

* String  字符串

  ```
  let str='abc';	\\单双引号均可，单不能嵌套单，双不能嵌套双
  \ 	转义字符
  \n	换行
  \t	制表符
  \f	分页符
  \v	垂直制表符
  \r	回车
  ```

* boolean  布尔类型

  true    false

* null  空

  就是一个占位符

* undefined  值只有一个，就是它本身

* Symbol  用来表示唯一值

#### 引用数据类型

* 函数function
* 数组array
* 对象object



## 运算符

* 算术运算符    +   -   *   /   %

  ```
  let a=200;
  let b=300;
  console.log(a+b);    //500
  ```

  ```
  let a='200';
  let b=300;
  console.log(a+b);   //200300
  //当一个字符串和数字相加时，结果是字符串
  ```

  ```
  let a='200';
  let b=true;
  console.log(a+b);   //200true
  //字符串相加等于连接
  ```

  ```
  //男生有200人，女生有300人，共500人
  let men=200;
  let women=300;
  console.log("男生有"+men+"人，女生有"+women+"人，共"+(men+women)+"人");
  ```

  ```
  //取余
  let a=5;
  let b=3;
  let result=b%a;
  console.log(result);    //3
  ```

* 逻辑运算符    &&    ||    ！

  * &&：和，并且          ||：或者  

    * ！：非        0  0.0  null  undefined  false  “”（空字符）  NaN 都为假，其余都是真

    * ！运算的结果一定是一个boolean类型值

    * &&和||如果能够计算出结果，立即停止运算

  ```
  let result,a;
  result=true&&false;
  a=true||false;
  console.log(result);    //false
  console.log(a);    //true
  ```

  &&    两者都满足为真

  ||     只要有一个满足为真即可

    * 判断的时候，可以用bool类型值判断，但结果是第一个值或是第二个值

  ```
  let result,a;
  result=1&&2;
  a=1||0;
  console.log(result);    //2
  console.log(a);    //1
  ```

* 赋值运算符    +=   -=   *=   /=    %=

  ```
  let a=300;
  a-=100;     //a=a-100
  console.log(a);     //200
  ```

* 比较运算符   >   <   >=   <=   !=   ==   ===   !==

  ```
  let str='123';
  let c=123
  console.log(str==c);     //true  ==只比较转化成的数值
  console.log(str===c);     //false  ===不但比较数值，还比较类型
  ```

  ```
  //null不等于0
  let str=null;
  let c=0;
  console.log(str==c);     //false
  ```

  ```
  //undefined不等于0
  let str=undefined;
  let c=0;
  console.log(str==c);     //false
  ```

  ```
  //undefined==null
  let str=undefined;
  let c=null;
  console.log(str==c);     //true
  console.log(str===c);     //false
  ```

  ```
  let str='abc';
  let c='def';
  console.log(str<c);     //true  根据ASCII码进行比较
  ```

  ```js
  console.log(1-'123');		//-122		隐式数据类型转化 number
  console.log(1>true);		//false
  console.log(null==undefined);		//true		特殊情况
  ```

  a=97  A=65  0=48

  当字符串和字符串进行比较时，比较的是ASCII码值

  ==只比较转化成的数值

  ===不但比较数值，还比较类型


* 一元运算符  

  * ++  自增  --  自减

    存在赋值的情况就会有区别，++在前就先加

    ```
    let result,a=1;
    result=++a;
    console.log(result);    //2
    ```

    ```
    let result,a=1;
    result=a++;
    console.log(result);    //1
    ```

  * typeof  检测数据类型

    ```
    let nub=123;    //'number'
    let str='123';  //'string'
    let bool=true;  //'bool'
    let n=null;     //'object'
    let un=undefined;   //'undefined'
    let fun=function () {}; //'function'
    let arr=[];     //'object'
    let obj={};     //'object'

    let result=typeof nub;
    console.log(result);
    ```


* 三元运算符
  * 目的是为了赋值
  * ```
    let res;
    res=1>0?'a':'b';
    console.log(res);   //a
    ```

  * ```
    let res;
    res=false?'a':'b';
    console.log(res);   //b
    ```
    ​

* 特殊运算符

  * new  用来创建对象
  * delete  用来删除对象的属性和方法
* 扩展运算符
  * ... 



## 流程控制

> 流程：代码执行的顺序
>
> 流程控制：当满足一定的条件时，执行不同的代码，即控制代码的执行顺序

#### 选择结构

* if

  > 只能进入一个分支，不可同时进入多个
  >
  > 条件要足够严谨

  * 用括号表示条件，用大括号表示执行语句

  ```
  let time=prompt('请输入时间'，'5');	//5为输入框默认值
  if (time>6) {
      console.log('class over');
  }
  ```

  * else  表示不满足条件时执行的语句

  ```
  let grade=prompt('请输入成绩');
  if (grade==100) {
      console.log('优秀');
  }
  else if (grade>=80 && grade<100) {
      console.log('良好');
  }
  else if (grade>=60 && grade<80) {
      console.log('及格');
  }
  else if (grade>=0 && grade<60) {
      console.log('不及格');
  }
  else {
      console.log('输入错误');
  }
  ```

  * break中断循环；continue跳过当前这次循环，继续执行下一次循环

    ```
    for(let x=0;x<=5;x++){
        document.write('外部第'+x+'次</br>');
        for(let y=0;y<=5;y++){
            if(y===3){
                continue;				//跳出当前次循环
            }
            document.write('内部第'+y+'次');
        }
    }
    ```

    ```
    for(let x=0;x<=5;x++){
        document.write('外部第'+x+'次</br>');
        for(let y=0;y<=5;y++){
            if(x==3){
                break;					//跳出循环
            }
            document.write('内部第'+y+'次');
        }
    }
    ```

  * 四则运算

  ```
  let a=prompt('请输入第一个数');
  let b=prompt('请输入第二个数');
  let fu=prompt('请输入运算符');
  if (fu=='+') {
      console.log(parseInt(a)+parseInt(b));
  }
  else if (fu=='-') {
      console.log(a-b);
  }
  else if (fu=='*') {
      console.log(a*b);
  }
  else if (fu=='/') {
      console.log(a/b)
  }
  else {
      console.log('输入错误');
  }
  ```

* switch

  >switch只能用来判断单个值，并且一般还是可枚举的。
  >
  >每一个case结束之后需要加break

  * 四则运算

  ```
  let a=prompt('请输入第一个数');
  let b=prompt('请输入第二个数');
  let fu=prompt('请输入运算符');
  switch (fu) {
      case '+':
          console.log(parseInt(a)+parseInt(b));
          break;
      case '-':
          console.log(a-b);
          break;
      case '*':
          console.log(a*b);
          break;
      case '/':
          console.log(a/b)
          break;
      default:
          console.log('输入错误');
  }
  ```

#### 循环结构

* 最重要的是循环的次数


* for

  * for (循环结构) {

    ​	循环体;

    }

    通过循环结构来控制循环的停止，从而控制循环的次数。

  * 在满足条件的时候，不断地去执行循环体

  * 执行顺序：初始化——判断循环条件——如果满足，执行循环体——执行步进——判断循环条件——如果满足，继续执行循环体——执行步进，直到不满足条件——循环结束

  * ​

* while

  ```
  let nub=5;		//先判断，再执行
  while (nub>0) {
      nub--;
      console.log(nub);
  }
  ```

* do while

  ```
  let nub=5;		//先执行，再判断
  do {
      nub--;
      console.log(nub);
  }
  while (nub>0);
  ```

#### 顺序结构

#### 练习

* 九九乘法表+表格

  ```
  //九九乘法表+表格
  document.write("<table border='1px' width='300px' cellspacing='0' cellpadding='3px'>");
  let x=1,y=1,res=0;
  for(let x=1;x<=10; x++) {
      document.write('<tr height="30px">');
      for(let y=1;y<=10;y++){
          res=x*y;
          document.write('<td>');
          if(y<=x){
              document.write(y+'x'+x+'='+res+' ');
          }
          document.write('</td>');
      }
  }
  ```

* 棋盘，32格，芝麻，0.0001

  ```
  let b=1,s=0;
  for (let q=1; q<=32; q++) {
      for (let p=0; p<(q-1); p++) {
          b=b*2;
      }
      s=s+b;
      b=1;
  }
  document.write('</br>');
  document.write(0.00001*s);
  ```

* 0-5的阶乘之和

  ```
  let sum=2;
  for(let i=2;i<=5;i++) {
      let a=1;
      for (let j=i;j>1;j--){
          a*=j;
      }
      sum+=a;
  }
  document.write('0-5的阶乘之和为'+sum+'</br>');
  ```

* 打印水仙花数

  ```
  let a=0,b=0,count=0;
  for (let x=1;x<10;x++) {
      for (let y=0;y<10;y++){
          for (let z=0;z<10;z++) {
              a=x*x*x+y*y*y+z*z*z;
              b=100*x+10*y+z;
              if (a==b) {
                  document.write(b+'</br>');
                  count+=1;
              }
          }
      }
  }
  ```

* 打印*

  ```
  for (let i=1;i<=5;i++) {
      for (let j=1;j<=i;j++){
          document.write('*');
      }
      document.write('<br>');
  }
  ```

* 1-100，能被3整除的数字之和

  ```
  let sum=0;
  for (let i=1;i<=100;i++) {
      if(i%3==0) {
          sum+=i;
      }
  }
  console.log(sum);
  ```

* 大马 2 x，中马 1 y，z小马 0.5，x+y+z=100,2x+y+0.5z=100

  ```
  let x=0,y=0,z=0,res=0;
  for (let x=0; x<=100; x++) {
      for (let y=0;y<=100; x++){
          for (let z=(100-x-y); z>=0;z--){
              res=(2*x+y+0.5*z);
              if(res==100){
                  console.log('大马有'+x+'头'+'中马有'+y+'头'+'小马有'+z+'头'+'<br>');
              }
          }
      }
  }
  ```

* 表格隔行、隔列变色

  ```
  //表格隔行变色
  document.write('<table border="1px" width="300px" cellspacing="0">');
  for (let row=1;row<=10;row++) {
      if (row%2==0) {
          document.write('<tr height="30px" bgcolor="#ffc0cb">');
      }
      else {
          document.write('<tr height="30px">');
      }
      for (let col=1; col<=10; col++) {
          document.write('<td></td>')
      }
      document.write('</tr>');
  }
  document.write('</table>');

  //表格隔列变色
  document.write('<table border="1px" width="300px" cellspacing="0">');
  for (let row=1;row<=10;row++) {
      document.write('<tr height="30px">');
      for (let col=1; col<=10; col++) {
          if (col%2==0) {
              document.write('<td bgcolor="#6495ed">');
          }
          else {
              document.write('<td>');
          }
          document.write('</td>');
      }
      document.write('</tr>');
  }
  document.write('</table>');

  ```




## 数组

> 有直接或者是间接联系的数据的集合
>
> 方便存储数据和管理数据

* 有很多数据之间是有关系的

* 定义方式：let arr=[ ];

  ​		    let  arr=new Array{ }

* 数组天然会形成下标，用下标来获取数组的长度

* 可以通过改变数组的长度，也就是length属性，来调节数组的长度

* 遍历数组使用for

* 若某个位置没有值，默认是undefined

* 数组可以存储任何数据类型，比如：函数、数组、对象等

* ```
  //定义一个数组
  let arr=[1,'a',true,false,null,5];
  console.log(arr);   //(6) [1, "a", true, false, null, 5]
  console.log(arr[0]);    //1
  arr[0]='1234';
  console.log(arr);   //(6) ["1234", "a", true, false, null, 5]
  arr[6]=undefined;
  console.log(arr);   //(7) ["1234", "a", true, false, null, 5, undefined]

  //定义一个空数组
  let brr=[];
  brr[1]=1;
  console.log(brr);   //(2) [empty, 1]
  console.log(brr[0]);    //undefined
  ```

* ```
  //找出数组中大于5的数的个数
  let arr=[1,2,2,2,5,5,12,3,12,3,123,6,123];
  let count=0;
  for(let i=0;i<arr.length;i++) {				//arr.length,得到数组长度
      if (arr[i]>5) {
          count+=1;
      }
  }
  console.log(count);
  ```

* ```
  //选出数组中大于5的数，组成一个新数组
  let arr=[1,2,2,2,5,5,12,3,12,3,123,6,123];
  let brr=[];
  for(let i=0;i<arr.length;i++) {
      if (arr[i]>5) {
          brr[brr.length]=arr[i];				//brr.length=下标
      }
  }
  console.log(brr);
  ```

* ```
  //输入一个数字或者是字符添加在数组最后
  let arr=[1,2,2,2,5,5,12,3,12,3,123,6,123];
  let a=prompt('请输入一个数字或字符');
  arr[arr.length]=a;
  console.log(arr);

  ```

* ```
  //将一个数组复制到一个新的数组
  let arr=[1,2,2,2,5,5,12,3,12,3,123,6,123];
  let brr=[];
  for(let i=0;i<arr.length;i++) {
      brr[brr.length]=arr[i];
  }
  console.log(arr,'</br>',brr);
  ```

* ```
  //将数组中数字内容求和
  let arr=[1,2,12,6,5];
  let sum=0;
  for(let i=0;i<arr.length;i++) {
      sum+=arr[i];
  }
  console.log(sum);
  ```

* ```
  //判断数组中是否所有的数字都大于0
  let arr=[1,2,12,6,-5];
  let flag='所有数字均大于0';
  for(let i=0;i<arr.length;i++) {
      if (arr[i]<=0) {
          flag='存在不大于0的数字';
      }
  }
  console.log(flag);
  ```

* ```
  //合并两个数组
  let arr=[1,2,12,6,5],brr=[2,2,2];
  for(let i=0;i<brr.length;i++) {
      arr[arr.length]=brr[i];
  }
  console.log(arr,brr);
  ```

* ```
  //找到数组中5所在的位置
  let arr=[1,2,5,12,6,5];
  let str='';
  for(let i=0;i<arr.length;i++) {
      if (arr[i]==5) {
          str+=i;
          str+=',';
      }
  }
  console.log(str);
  ```

* ```
  //将一个数组反转
  let arr=[1,2,5,12,6,5];
  let brr=[];
  for(let i=1;i<=arr.length;i++) {
      brr[brr.length]=arr[arr.length-i];
  }
  console.log(brr);
  //方法二
  let arr=[1,2,5,12,6,5],n=0;
  for(let i=0;i<arr.length/2;i++) {
      n=arr[arr.length-i-1];
      arr[arr.length-i-1]=arr[i];
      arr[i]=n;
  }
  console.log(arr);
  ```

* ```
  //求一个数组中最大的数
  let arr=[1,2,5,12,6,5];
  let max=arr[0];
  for(let i=1;i<arr.length;i++) {
      if(max<arr[i]){
           max=arr[i];
      }
  }
  console.log(max);
  ```

* ```
  //移除数组中等于3的元素
  let arr=[1,2,5,3,12,6,5];
  let brr=[];
  for(let i=0;i<arr.length;i++) {
      if(arr[i]==3){
          continue;
      }
      else {
          brr[brr.length]=arr[i];
      }
  }
  console.log(brr);
  //法二
  let arr=[1,2,5,3,3,12,3,6,5];
  for(let i=arr.length-1;i>=0;i--) {
      if(arr[i]==3){
          for(let j=i;j<arr.length;j++){
              arr[j]=arr[j+1];
          }
          arr.length-=1;
      }
  }
  console.log(arr);
  ```

* ```
  //删除数组中的第一个值
  let arr=[1,2,5,3,12,6,5];
  let brr=[];
  for(let i=1;i<arr.length;i++) {
      brr[brr.length]=arr[i];
  }
  console.log(brr);
  //法二
  let arr=[1,2,5,3,12,6,5];
  for(let j=0;j<arr.length;j++){
      arr[j]=arr[j+1];
  }
  arr.length-=1;
  console.log(arr);
  ```

* ```
  //

  ```

* 在数组的前面去添加一个值

  ```js
  let arr=[1,2,5,3,12,6,5];
  let a=prompt('请输入一个任意值');
  let brr=[a];
  for(let i=0;i<arr.length;i++) {
      brr[brr.length]=arr[i];
  }
  console.log(brr);
  //法二
  let arr=[1,2,5,3,12,6,5];
  let a=prompt('请输入一个任意值');
  arr.length+=1;
  for(let i=arr.length-1;i>=0;i--){
      arr[i]=arr[i-1];
  }
  arr[0]=a;
  console.log(arr);
  ```

* 在数组的后面添加一个值

  ```js
  let arr=[1,2,5,3,12,6,5],brr=[];
  let a=prompt('请输入一个任意值');
  for(let i=0;i<arr.length;i++) {
      brr[brr.length]=arr[i];
  }
  brr[brr.length]=a;
  console.log(brr);

  let arr=[1,2,5,3,12,6,5];
  let a=prompt('请输入一个任意值');
  arr[arr.length]=a;
  console.log(arr);
  ```

* 在数组的后面去删除一个值

  ```js
  let arr=[1,2,5,3,12,6,5],brr=[];
  for(let i=0;i<arr.length-1;i++) {
      brr[brr.length]=arr[i];
  }
  console.log(brr);
  ```

* 从一个数组中，取出3位置到5位置的字符，组成一个新的数组

  ```js
  let arr=[1,2,5,3,12,6,5],brr=[];
  for(let i=3;i<6;i++) {
      brr[brr.length]=arr[i];
  }
  console.log(brr);
  ```

* 选择排序

  ```js
      for (let i=0;i<arr.length-1;i++) {
          for (let j=i;j<arr.length;j++) {
              if (type=='asc') {
                  if (arr[j]>arr[i]) {
                      let tmp = arr[j];
                      arr[j] = arr[i];
                      arr[i] = tmp;
                  }
              }
              else if (type=='desc') {
                  if (arr[j] < arr[i]) {
                      let tmp = arr[j];
                      arr[j] = arr[i];
                      arr[i] = tmp;
                  }
              }
          }
  console.log(arr);
  ```

* 冒泡排序

  ```js
  let arr=[1,4,5,3,12,6,5];
  for (let i=arr.length-1;i>=0;i--) {
      for (let j=0;j<=i;j++) {
          if (arr[j]>arr[j+1]) {
              let tmp=arr[j];
              arr[j]=arr[j+1];
              arr[j+1]=tmp;
          }
      }
  }
  console.log(arr);
  ```

#### 二维数组

> 当一维数组里面的每个值都是数组的时候，这个数组成为二维数组

```js
let arr=[[1,2],[true,false],['a','b']];
console.log(arr);               //(3) [Array(2), Array(2), Array(2)]
```

* 遍历

  ```js
  let arr=[[1,2],[true,false],['a','b']];
  for (let i=0;i<arr.length;i++) {
      for (let j=0;j<arr[i].length;j++) {
          console.log(arr[i][j]);
      }
  }
  ```

* 复制一个二维数组

  ```js
  let arr=[[1,2],[1,2,3,4,5,6],[1,2,3,4]];
  let brr=[];
  for(let i=0;i<arr.length;i++) {
      brr[i]=[];
      for (let j=0;j<arr[i].length;j++){
          brr[i][j]=arr[i][j];
      }
  }
  console.log(brr);
  ```

* 求二维数组的最大值

  ```js
  let arr=[[1,2],[1,2,3,4,5,6],[1,2,3,4]];
  let max=arr[0][0];
  for (let i=0;i<arr.length;i++) {
      for (let j=0;j<arr[i].length;j++) {
          if(max<arr[i][j]) {
              max=arr[i][j];
          }
      }
  }
  console.log(max);
  ```

* 求二维数组的和

  ```js
  let arr=[[1,2],[1,2,3,4,5,6],[1,2,3,4]];
  let sum=0;
  for(let i=0;i<arr.length;i++){
      for (let j=0;j<arr[i].length;j++) {
          sum+=arr[i][j];
      }
  }
  console.log(sum);
  ```

* 求得一个二维数组中，长度最长的数组

  ```js
  let arr=[[1,2],[1,2,3,4,5,6],[1,2,3,4]];
  let max=arr[0];
  for (let i=0;i<arr.length;i++) {
          if(max.length<arr[i].length){
          max=arr[i];
      }
  }
  console.log(max);
  ```




## 内存

* 内存单位
  * 位 	    bit	1b=2状态
  * 字节    B          1B=8b
  * K         1KB=2^10B        KB=1024B      Kb=1024bit
  * M        1MB=1024KB
  * G         1GB=1024MB
  * T          1TB=1024GB
* 内存包括
  * 栈区（存放初始数据类型，**传值**）
  * 堆区（存放引用数据类型，**传址**）




## 函数function

> 将实现某一特定功能的代码封装起来，以便重复使用

* 定义方式

  * 以关键字的方式定义

    ```js
    function fun() {
        console.log('这是一个函数');
    }
    ```

  * 以对象的方式定义

    ```js
    let fun=new Function('a','alert(1)');
    ```

  * 以自变量的方式定义

    ```js
    let fun=function () {
        console.log('这也是一个函数');
    }
    ```


  * 以对象的方式定义

    ```js
    let fun = new Function();
    ```

#### 函数的参数

* 形式参数

  在函数定义的时候，括号里的参数叫做形式参数

* 实际参数

  在函数运行的时候，在函数括号里的参数，叫做实际参数

* 形式参数和实际参数的个数可以不痛

* 默认传递的值是undefined

* 形式参数和实际参数是对应一一进行赋值的

* 形式参数是用来接收实际参数的

* 形式参数的个数，由函数的功能而决定

* 形式参数可以接收任何类型的值

* *<u>如果传递的值全等于undefined，那么就会启用默认值</u>*

* 练习

  * 封装冒泡排序

    ```js
    function bupple(arr,type='asc') {
        for (let i=0;i<arr.length;i++) {
            for (let j=0;j<arr.length-i-1;j++) {
                if (type=='asc') {                  //升序
                    if (arr[j]>arr[j+1]) {
                        let tmp = arr[j];
                        arr[j] = arr[j + 1];
                        arr[j + 1] = tmp;
                    }
                }
                else if (type=='desc') {               //降序
                    if (arr[j]<arr[j+1]) {
                        let tmp = arr[j];
                        arr[j] = arr[j + 1];
                        arr[j + 1] = tmp;
                    }
                }
            }
        }
        console.log(arr);
    }
    bupple([1,33,5,5,23,3,8]);
    ```

  * 求数组的和

    ```js
    function add(arr) {
        let sum=0
        for (let i=0;i<arr.length;i++) {
            if (arr[i] instanceof Array) {				//判断是否为数组
               for (let j=0;j<arr[i].length;j++) {
                   sum+=arr[i][j];
               }
            }
            else {
                sum+=arr[i];
            }
        }
        console.log(sum);
    }
    add([[1,2,3],[1,1]]);
    ```

  * 一个数组，截取下标为a到b的范围

    ```js
    function jiequ(arr,a,b) {
        let brr=[];
        if (a<0) {
            a=0;
        }
        if (b>arr.length-1) {
            b=arr.length-1;
        }
        for (let i=a;i<=b;i++) {
            brr[brr.length]=arr[i];
        }
        console.log(brr);
    }
    jiequ([1,4,5,'d',68,3,2,],2,5);
    ```

    ​

#### 函数的返回值

* 任何一个函数在运行结束之后，都会返回
* 函数默认返回undefined
* 函数一旦返回，意味着函数立即停止运行
* 函数可以有多条返回语句，但是只能运行一条语句
* 函数只能返回一个值，但是可以返回任何数据类型
* 当要使用函数内部运行得出的值时，只有通过返回值才能使用

#### 函数的作用域

> 变量或者函数在某个范围内有意义

#### 环境

* 宿主环境 —— 浏览器

* 执行环境

  * 全局环境 —— Window

    当一个变量或者函数定义在全局环境中的时候，我们叫做全局函数或者全局变量，拥有全局的作用域

  * 局部环境 —— 函数

    当一个变量或者函数定义在局部环境中的时候，我们叫做局部函数或局部变量，拥有局部的作用域


* 全局变量 —— 全局作用域
* 局部变量 —— 局部作用域

#### 作用域链

> 当一个函数在运行的时候，会自动创建一个集合，用来保存可见范围内的所有变量，这个集合就是作用域链

#### 预解析

> 在代码开始运行之前，提前加载或者是解析一些东西

* 在代码开始运行之前，以关键字var定义的变量和以关键字function定义的函数，会提前加载到内存中（相对应的环境中）

#### 回调函数

> 将一个函数作为另外一个函数的参数的时候，这个函数称之为回调函数

* 四则运算

  ```js
  function fu(type,m,n) {
      type(m,n);
  }
  function add(a,b) {
      console.log(a+b);
  }
  function reduce(a,b) {
      console.log(a-b);
  }
  function c(a,b) {
      console.log(a*b);
  }
  function ch(a,b) {
      console.log(a/b);
  }
  ```


#### 递归函数

> 当一个函数自己调用自己的时候，我们称之为递归函数

* 阶乘

  ```js
  function jc(n) {
      if (n==1) {
          return 1;			
      }
      return n*jc(n-1);		//自己调用自己
  }
  console.log(jc(5));
  ```



####垃圾处理

* 对于局部变量，在函数运行结束之后，立即被删除
* 对于不再引用的对象，js将在某一个时刻将它删除

####闭包

> 在一个函数内部嵌套另外一个函数，在内部函数中用到了外部的局部变量，那么当在外部调用内部函数的时候，就会形成闭包，保存内部的局部变量

```js
function aa(){
    var nub=200;
    function bb() {
        console.log(nub);
    }
    return bb;
}
let fun=aa();
fun();
```





## 对象

* 类是对象的抽象，对象是类的实例化，现有对象后有类

* 数组是对象，一切皆对象

* 属性的值可以是任何数据类型

* 创建方式

  * 以json格式创建对象
  * 用构造函数创建对象  new Fun ();
  * 用object创建对象  new Object() ;

* 删除对象：

  ```js
  let obj={
    name='lisi';
    age=18;
  }
  delete obj.name;		//删除对象的属性
  obj=null;				//删除对象
  console.log(obj.sex)	//当想输出一个属性，但对象并不具有时，输出的是undefined
  ```

  ​

* 构造函数：提供对象的初始化

  ```js
  function person(name,age) {					//普通函数作为构造函数
      this.name=name;							//this指针
      this.age=age;
      this.talk=function () {
          console.log(' can talk');
      }
  }
  let fanny = new person('fanny',18);
  let xiaoming = new person('xiaoming',18);
  fanny.name='sha';
  console.log(fanny);

  class person {
    constructor(){
      初始化
    }
  }
  ```

* this 指针

* 访问对象的属性和方法使用 . 运算符 或是使用[ ]进行访问

  ```js
  let obj={
    name:'lisi',
    age:30,
    fun:fuction(){
    	console.log(1);
    }
  };
  obj.name
  obj['name']
  obj.fun()
  obj['fun']()
  ```


* 将age>15的对象组成一个新数组

  ```js
  let crr=[
      {nub:1,name:'lisi',age:29},
      {nub:2,name:'lisi1',age:13},
      {nub:3,name:'lisi2',age:22},
      {nub:4,name:'lisi3',age:19},
  ]
  function age(arr) {
      let brr=[];
      for(let i=0;i<arr.length;i++) {
          if (arr[i].age>15) {
              brr[brr.length]=arr[i];
          }
      }
      console.log(brr);
  }
  age(crr)；
  ```

* 原型(原型对象)

  ```js
  function person(n,age) {
      this.name=n;
      this.age=age;
  }

  person.prototype.run=function () {				//存放在静态区中
      console.log(this.name);
  };

  person.prototype.talk=function () {
      console.log(' can talk');
  };

  let obj1=new person('lisi',18);
  console.log(obj1);
  obj1.run();
  ```

* 原型链

  一个普通对象的_proto____属性会指向构造函数的原型对象，构造函数的原型对象的  ____proto____会指向原型对象的构造函数的原型，一直向上，最终指向Object的原型

  ```js
  xiaohuang.__proto__ === dog.prototype
  dog.prototype.__proto__ === animal.protptype
  animal.prototype.__proto__ === Object.prototype
  Object.prototype.__proto__ === null
  ```

  ​

* 一切皆对象

  ​


####数组方法

* join ：将数组的元素组成一个字符串，以separator为分隔符，省略的话则用默认用逗号为分隔符，该方法只接收一个参数：即分隔符。

  ```js
  let arr=[1,2,3];
  console.log(arr.join());            //1,2,3
  console.log(arr.join('-'));         //1-2-3
  console.log(arr);                   //(3) [1, 2, 3]
  console.log(arr.join('^'));         //1^2^3
  ```

  通过join()方法可以实现重复字符串，只需传入字符串以及重复的次数，就能返回重复后的字符串，函数如下：  

  ```js
  function repeatString(str, n) {
  return new Array(n + 1).join(str);
  }
  console.log(repeatString("abc", 3)); // abcabcabc
  console.log(repeatString("Hi", 5)); // HiHiHiHiHi
  ```

* push :可以接收任意数量的参数，把它们逐个添加到数组末尾，并返回修改后数组的长度。 

* pop:数组末尾移除最后一项，减少数组的 length 值，然后返回移除的项。

  ```js
  var arr = ["Lily","lucy","Tom"];
  var count = arr.push("Jack","Sean");
  console.log(count); // 5
  console.log(arr); // ["Lily", "lucy", "Tom", "Jack", "Sean"]
  var item = arr.pop();
  console.log(item); // Sean
  console.log(arr); // ["Lily", "lucy", "Tom", "Jack"]
  ```

* shift ：删除原数组第一项，并返回删除元素的值；如果数组为空则返回undefined 。

* unshift：将参数添加到原数组开头，并返回数组的长度 。

  ```js
  var arr = ["Lily","lucy","Tom"];
  var count = arr.unshift("Jack","Sean");
  console.log(count); // 5
  console.log(arr); //["Jack", "Sean", "Lily", "lucy", "Tom"]
  var item = arr.shift();
  console.log(item); // Jack
  console.log(arr); // ["Sean", "Lily", "lucy", "Tom"]
  ```

* sort：按升序排列数组项——即最小的值位于最前面，最大的值排在最后面。

  在排序时，sort()方法会调用每个数组项的 toString()转型方法，然后比较得到的字符串，以确定如何排序。即使数组中的每一项都是数值， sort()方法比较的也是字符串，因此会出现以下的这种情况：

  ```js
  var arr1 = ["a", "d", "c", "b"];
  console.log(arr1.sort()); // ["a", "b", "c", "d"]
  arr2 = [13, 24, 51, 3];
  console.log(arr2.sort()); // [13, 24, 3, 51]
  console.log(arr2); // [13, 24, 3, 51](元数组被改变)
  ```

  为了解决上述问题，sort()方法可以接收一个比较函数作为参数，以便我们指定哪个值位于哪个值的前面。

  ```js
  function compare(value1, value2) {
  	return value1-value2;
  }
  arr2 = [13, 24, 51, 3];
  console.log(arr2.sort(compare)); // [3, 13, 24, 51]
  ```

  如果需要通过比较函数产生降序排序的结果，只要交换比较函数返回的值即可：

  ```js
  function compare(value1, value2) {
  	return value2-value1;
  }
  arr2 = [13, 24, 51, 3];
  console.log(arr2.sort(compare)); // [51, 24, 13, 3]
  ```

* reverse ：反转数组项的顺序。

  ```js
  var arr = [13, 24, 51, 3];
  console.log(arr.reverse()); //[3, 51, 24, 13]
  console.log(arr); //[3, 51, 24, 13](原数组改变)
  ```

* concat：将参数添加到原数组中，不会改变原数组。这个方法会先创建当前数组一个副本，然后将接收到的参数添加到这个副本的末尾，最后返回新构建的数组。在没有给 concat()方法传递参数的情况下，它只是复制当前数组并返回副本。

  ```js
  var arr = [1,3,5,7];
  var arrCopy = arr.concat(9,[11,13]);
  console.log(arrCopy); //[1, 3, 5, 7, 9, 11, 13]
  console.log(arr); // [1, 3, 5, 7](原数组未被修改)
  ```

  从上面测试结果可以发现：传入的不是数组，则直接把参数添加到数组后面，如果传入的是数组，则将数组中的各个项添加到数组中。但是如果传入的是一个二维数组呢？

  ```js
  var arrCopy2 = arr.concat([9,[11,13]]);
  console.log(arrCopy2); //[1, 3, 5, 7, 9, Array[2]]
  console.log(arrCopy2[5]); //[11, 13]
  ```

  上述代码中，arrCopy2数组的第五项是一个包含两项的数组，也就是说concat方法只能将传入数组中的每一项添加到数组中，如果传入数组中有些项是数组，那么也会把这一数组项当作一项添加到arrCopy2中。

* slice ：返回原数组中指定开始下标到结束下标之间的项组成的新数组。slice()方法可以接受一或两个参数，即要返回项的起始和结束位置。在只有一个参数的情况下， slice()方法返回从该参数指定位置开始到当前数组末尾的所有项。如果有两个参数，该方法返回起始和结束位置之间的项——但不包括结束位置的项。

  ```js
  var arr = [1,3,5,7,9,11];
  var arrCopy = arr.slice(1);
  var arrCopy2 = arr.slice(1,4);
  var arrCopy3 = arr.slice(1,-2);
  var arrCopy4 = arr.slice(-4,-1);
  console.log(arr); //[1, 3, 5, 7, 9, 11](原数组没变)
  console.log(arrCopy); //[3, 5, 7, 9, 11]
  console.log(arrCopy2); //[3, 5, 7]
  console.log(arrCopy3); //[3, 5, 7]
  console.log(arrCopy4); //[5, 7, 9]
  ```

  arrCopy只设置了一个参数，也就是起始下标为1，所以返回的数组为下标1（包括下标1）开始到数组最后。 
  arrCopy2设置了两个参数，返回起始下标（包括1）开始到终止下标（不包括4）的子数组。 
  arrCopy3设置了两个参数，终止下标为负数，当出现负数时，将负数加上数组长度的值（6）来替换该位置的数，因此就是从1开始到4（不包括）的子数组。 
  arrCopy4中两个参数都是负数，所以都加上数组长度6转换成正数，因此相当于slice(2,5)。

* splice ：很强大的数组方法，它有很多种用法，可以实现删除、插入和替换。

  删除：可以删除任意数量的项，只需指定 2 个参数：要删除的第一项的位置和要删除的项数。例如， splice(0,2)会删除数组中的前两项。

  插入：可以向指定位置插入任意数量的项，只需提供 3 个参数：起始位置、 0（要删除的项数）和要插入的项。例如，splice(2,0,4,6)会从当前数组的位置 2 开始插入4和6。
  替换：可以向指定位置插入任意数量的项，且同时删除任意数量的项，只需指定 3 个参数：起始位置、要删除的项数和要插入的任意数量的项。插入的项数不必与删除的项数相等。例如，splice (2,1,4,6)会删除当前数组位置 2 的项，然后再从位置 2 开始插入4和6。

  splice()方法始终都会返回一个数组，该数组中包含从原始数组中删除的项，如果没有删除任何项，则返回一个空数组。

  ```js
  var arr = [1,3,5,7,9,11];
  var arrRemoved = arr.splice(0,2);
  console.log(arr); //[5, 7, 9, 11]
  console.log(arrRemoved); //[1, 3]
  var arrRemoved2 = arr.splice(2,0,4,6);
  console.log(arr); // [5, 7, 4, 6, 9, 11]
  console.log(arrRemoved2); // []
  var arrRemoved3 = arr.splice(1,1,2,4);
  console.log(arr); // [5, 2, 4, 4, 6, 9, 11]
  console.log(arrRemoved3); //[7]
  ```

* forEach：对数组进行遍历循环，对数组中的每一项运行给定函数。这个方法没有返回值。参数都是function类型，默认有传参，参数分别为：遍历的数组内容；第对应的数组索引，数组本身。

  ```js
  var arr = [1, 2, 3, 4, 5];
  arr.forEach(function(x, index, a){
  console.log(x + '|' + index + '|' + (a === arr));
  });
  // 输出为：
  // 1|0|true
  // 2|1|true
  // 3|2|true
  // 4|3|true
  // 5|4|true
  ```

* map：指“映射”，对数组中的每一项运行给定函数，返回每次函数调用的结果组成的数组。

  下面代码利用map方法实现数组中每个数求平方。

  ```js
  var arr = [1, 2, 3, 4, 5];
  var arr2 = arr.map(function(item){
  	return item*item;
  });
  console.log(arr2); //[1, 4, 9, 16, 25]
  ```

* filter()：“过滤”功能，数组中的每一项运行给定函数，返回满足过滤条件组成的数组。

  ```js
  var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  var arr2 = arr.filter(function(x, index) {
  return index % 3 === 0 || x >= 8;
  }); 
  console.log(arr2); //[1, 4, 7, 8, 9, 10]
  ```

* every()：判断数组中每一项都是否满足条件，只有所有项都满足条件，才会返回true

  ```js
  var arr = [1, 2, 3, 4, 5];
  var arr2 = arr.every(function(x) {
  return x < 10;
  }); 
  console.log(arr2); //true
  var arr3 = arr.every(function(x) {
  return x < 3;
  }); 
  console.log(arr3); // false
  ```

* some()：判断数组中是否存在满足条件的项，只要有一项满足条件，就会返回true。

  ```js
  var arr = [1, 2, 3, 4, 5];
  var arr2 = arr.some(function(x) {
  return x < 3;
  }); 
  console.log(arr2); //true
  var arr3 = arr.some(function(x) {
  return x < 1;
  }); 
  console.log(arr3); // false
  ```

* find：用于找出第一个符合条件的数组成员。它的参数是一个回调函数，所有数组成员依次执行该回调函数，直到找出第一个返回值为`true`的成员，然后返回该成员。如果没有符合条件的成员，则返回`undefined`。

* findIndex()：也是查找目标元素，找到就返回元素的位置，找不到就返回-1。

  他们的都是一个查找回调函数。

  ```js
  [1, 2, 3, 4].find((value, index, arr) => {
  })
  ```

  查找函数有三个参数。

  value：每一次迭代查找的数组元素。

  index：每一次迭代查找的数组元素索引。

  arr：被查找的数组。

  ```js
  const arr1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11]
  var ret1 = arr1.find((value, index, arr) => {
   return value > 4
  })
  var ret2 = arr1.find((value, index, arr) => {
   return value > 14
  })
  var ret3 = arr1.findIndex((value, index, arr) => {
   return value > 4
  })
  var ret4 = arr1.findIndex((value, index, arr) => {
   return value > 14
  })
  console.log('%s', ret1)			//5
  console.log('%s', ret2)			//undefined
  console.log('%s', ret3)			//4
  console.log('%s', ret4)			//-1
  ```

* **includes** ：用来判断一个数组是否包含一个指定的值，根据情况，如果包含则返回 true，否则返回false。

  ```js
  const arr1 = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', NaN]
  console.log('%s', arr1.includes('c'))		//true
  console.log('%s', arr1.includes('z'))		//false
  console.log('%s', arr1.includes(NaN))		//true
  ```

  includes()函数的第二个参数表示判断的起始位置。

  第二个参数也可以是负数，表示从右数过来第几个，但是不改变判断搜索的方向，搜索方向还是从左到右。

  ```js
  const arr1 = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', NaN]
  console.log('%s', arr1.includes('d', 1))		//true
  console.log('%s', arr1.includes('d', 3))		//true
  console.log('%s', arr1.includes('d', 4))		//false
  console.log('%s', arr1.includes('k', -1))       //false
  console.log('%s', arr1.includes('k', -2))       //true
  console.log('%s', arr1.includes('i', -3))       //false

  ```

* 练习

  * 求得在一个数组中，下标大于5的元素组成的数组

    ```js
    let arr1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11];
    let brr=[];
    arr1.forEach(function (value,index) {
        if (index>5) {
            brr[brr.length]=value;
        }
    });
    console.log(brr);
    ```

  * 在一个数组中，求得大于5的元素组成的数组

    ```js
    let arr1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11];
    let brr=[];
    arr1.forEach(function (value) {
        if (value>5) {
            brr[brr.length]=value;
        }
    });
    console.log(brr);
    ```

  * 在一个数组中，求得每个数的平方组成的数组

    ```js
    let arr1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11];
    let brr=[];
    arr1.forEach(function (value) {
        brr[brr.length]=value*value;
    });
    console.log(brr);
    ```

    ​


#### 字符串方法

* **concat**：将两个或多个字符的文本组合起来，返回一个新的字符串。

  ```js
  var a = "hello";
  var b = ",world";
  var c = a.concat(b);
  alert(c);				//c = "hello,world"
  ```

* **indexOf：**返回字符串中一个子串第一处出现的索引（从左到右搜索）。如果没有匹配项，返回 -1 。

  ```js
  var index1 = a.indexOf("l");		//index1 = 2
  var index2 = a.indexOf("l",3);		//index2 = 3
  ```

* **charAt：**返回指定位置的字符。

  ```js
  var get_char = a.charAt(0);			//get_char = "h"
  ```

* **lastIndexOf：**返回字符串中一个子串最后一处出现的索引（从右到左搜索），如果没有匹配项，返回 -1 。

  ```js
  var index1 = lastIndexOf('l');		//index1 = 3
  var index2 = lastIndexOf('l',2)		//index2 = 2
  ```

* **substring：**返回字符串的一个子串，传入参数是起始位置和结束位置。

  ```js
  var sub_string1 = a.substring(1);		//sub_string1 = "ello"
  var sub_string2 = a.substring(1,4);		//sub_string2 = "ell"
  ```

* **substr：**返回字符串的一个子串，传入参数是起始位置和长度

  ```js
  var sub_string1 = a.substr(1);			//sub_string1 = "ello"
  var sub_string2 = a.substr(1,4);		//sub_string2 = "ello"
  ```

* **slice()：**返回从 start 到 end （不包括）之间的字符，可传负值

  ```js
  var str = 'this is awesome';
  str.slice(4, -1); //" is awesom"
  ```

* **replace：**用来查找匹配一个正则表达式的字符串，然后使用新字符串代替匹配的字符串。?

  ```js
  var result1 = a.replace(re,"Hello");	//result1 = "Hello"
  var result2 = b.replace(re,"Hello");	//result2 = ",world"
  ```

* **split：**通过将字符串划分成子串，将一个字符串做成一个字符串数组。

  ```js
  var arr1 = a.split("");			//arr1 = [h,e,l,l,o]
  ```

* **toLowerCase：**将整个字符串转成小写字母。

  ```js
  var lower_string = a.toLowerCase();		//lower_string = "hello"
  ```

* **toUpperCase：**将整个字符串转成大写字母。

  ```js
  var upper_string = a.toUpperCase();		//upper_string = "HELLO"
  ```

* **trim：**去除 str 开头和结尾处的空白字符，返回 str 的一个副本，不影响字符串本身的值

* **trimLeft**: 去除字符串左边的空格

* **trimRight**: 去除字符串右边的空格

  ```js
  var str = ' abc ';
  str.trim(); // 'abc'
  console.log(str); // ' abc '
  ```

* **charCodeAt：**返回指定索引处的unicode字符（十六进制）

  ```js
  str.charCodeAt(0);   //97
  ```

* **includes()**：返回布尔值，表示是否找到了参数字符串。这三个方法都支持第二个参数，表示开始搜索的位置。

* **startsWith()**：返回布尔值，表示参数字符串是否在原字符串的头部。这三个方法都支持第二个参数，表示开始搜索的位置。

* **endsWith()**：返回布尔值，表示参数字符串是否在原字符串的尾部。这三个方法都支持第二个参数，表示开始搜索的位置。

  ```js
  var s = 'Hello world!';
  s.startsWith('world', 6) // true
  s.endsWith('Hello', 5) // true
  s.includes('Hello', 6) // false
  ```

* **repeat()**： 返回一个新字符串，表示将原字符串重复n次。

  ```js
  'x'.repeat(3) // "xxx"
  'hello'.repeat(2) // "hellohello"
  'na'.repeat(0) // ""
  ```

  ​


abs         绝对值

ceil		向上取整

cos

floor	向下取整

max

min

PI

pow		幂

random		随机数

round		四舍五入

sin

sqrt		开方

tan



## 内置顶层函数

* Number()

  * isNaN( )方法：判断是否能转化为数值类型

  * NaN是一个数值类型

  * ```js
    console.log(Number(undefined));		//NaN
    console.log(Number(true));			//1
    console.log(Number(false));			//0
    console.log(Number(null));			//0
    ```

* String()

  * 将其他类型转化为字符串形式

* Boolean()

* parseInt()

  * ```js
    console.log(parseInt('123djian'))		//123
    console.log(parseInt('123djia35453n'))		//123
    ```

  * 转化整数

* parseFloat()

  * 转化小数




## BOM 浏览器对象模型

* 浏览器窗口	Window	顶层对象
* 历史记录  history  地址栏  location  文档  document  是window的子对象



#### Window

* ```js
  var aa=200;
  function fun() {		//fun函数直接挂到Window对象的属性下
    this.aa=300;
  }
  fun();					//window.fun();
  console.log(aa);		//300
  ```

* alert

* 时间函数：

  * setInterval：在指定的时间内，重复不断的去做某个事情

    ```js
    setInterval(function(){				//参数：function、间隔时间,时间单位为ms
      console.log(1);
    },1000);
    ```

  * setTimeout

    ```js
    setTimeout (function(){
      console.log(1);					//只执行1次
    },500)
    ```

  * clearInterval

    ```js
    let t=setInterval();
    clearInterval(t);					//使setInterval停止
    ```

  * clearTimeout

    ```js
    let t=setTimeout();
    clearTimeout(t);					//清除setTimeout的返回值
    ```

    ​

* open

  ```js
  window.onload=function(){
    let btn=document.querySelector('button');
    btn.onclick=function(){
      window.open("http://www.baidu.com");
    }
  }
  ```

* close

  ```js
  window.onload=function(){
    let btn=document.querySelector('button');
    btn.onclick=function(){
      window.close();								//关闭窗口
    }
  }
  ```

* confirm

  ```js
  window.onload=function(){
    let btn=document.querySelector('button');
    btn.onclick=function(){
      let res=window.confirm('是否确认关闭此窗口');
      if(res){
        console.log('确认');
      }
      else{
        console.log('取消')；
      }
    }
  }
  ```

* document

* frames

* getComputedStyle

* history

* localStorage

* location

* navigator

* prompt

* screen

* sessionStorage



#### Location地址栏

*  https://www.baidu.com/s?wd=%E4%BB%8A%E6%97%A5%E6%96%B0%E9%B2%9C%E4%BA%8B&tn=SE_Pclogo_6ysd4c7a&sa=ire_dl_gh_logo&rsv_dl=igh_logo_pc

* http://localhost:63342/js/lianxi.html?_ijt=ieiv8ija55v4l7p81b9nupp1td

* http、https：网络协议，超文本传输协议，网络间的数据在传输时的通用协议

* 127.0.0.1：8020/www.baidu.com：主机名/域名

* ：8020 或 ：80  端口号

* /s/    路径 pathname

* ？  aa=bb&cc=dd    查询字符串，进行网络间数据的传递

* \#box    hash  锚地址

* 属性

  * protocol：获取协议

  * host：主机名和端口号

  * hostname：主机名

  * port：端口号

  * search：查询字符串

  * pathname：路径

  * hash：锚地址

  * location.href：获取完整路径，可以用来设置完整路径，页面就会跳转

  * assign( )

    ```js
    window.onload=function(){
      let btn=document.querySelector('button');
      btn.onclick=function(){
        window.assign("http://www.baidu.com");			//加载一个页面,会留下历史记录
      }
    }
    ```


  * replace( )

    ```js
    window.onload=function(){
      let btn=document.querySelector('button');
      btn.onclick=function(){
        window.replace("http://www.baidu.com");			//替换当前页面,不会留下历史记录
      }
    }
    ```

  * reload( )

    ```js
    window.onload=function(){
      let btn=document.querySelector('button');
      btn.onclick=function(){
        window.reload(true);		 //重新加载,如果有参数true,跳过缓存，重新加载页面；否则不跳过
      }
    }
    ```



#### history  历史

* history.back( )：后退

* history.forward：前进

* history.go(n)；

  history.go(0)：刷新

  history.go(-n)：后退

* ```js
  window.onload=function () {
      let back=document.querySelector('.back');
      let go=document.querySelector('.go');
      let load=document.querySelector('.load');
      back.onclick=function () {
          history.back();
      };
      go.onclick=function () {
          history.forward();
      };
      load.onclick=function () {
          history.go(0);
      }
  };
  ```





## DOM  文档对象模型

> 对于元素的内容、属性、样式、位置的操作

* document.title：设置文档标题

* ```js
  console.log(document.documentElement.clientWidth);		//获取浏览器窗口的宽高
  console.log(document.documentElement.clientHeight);		
  console.log(window.screen.width);						//获取屏幕分辨率
  console.log(window.screen.height);
  ```

* 获取元素的方法

  * 用原生的js方式获取的元素叫做dom对象或dom对象集

  * document.querySelector();：只能获取匹配元素的第一个

  * document.querySelectorAll();：获取所有匹配的元素

  * instanceof：用来检测某一个对象是否是某个构造函数的实例

    ```js
    window.onload=function () {						
    	let div=document.querySelectorAll('div');
    	console.log(div instanceof Array);				//判断是否为数组
    }
    ```

  * dom对象集可以用forEach()方法

  * ```js
    window.onload=function () {
    	let div=document.getElementsByClassName('aa');
    	let res=document.getElementById('bb');
    	let p=document.getElementsByTagName('p');
    	let input=document.getElementsByName('pp');
      	console.log(div);
        console.log(res);
        console.log(p);
        console.log(input);
        console.log(div[0].getElementsByTagName('p'));
        console.log(p[1].getElementsByClassName('a'));
        console.log(res.getElementsByTagName('p'));
    }
    ```

  * 元素内容的获取

    * innerHTML：改变元素内容，可以识别标签

    * innerText：改变元素内容，不识别标签

      ```js
      window.onload=function(){
          let div=document.querySelectorAll('div');
          div.forEach(function(value,index){
              value.innerHTML='<b>这是第'+index+'个div</b>';
          });
      };													//这是第i个div

      window.onload=function(){
          let div=document.querySelectorAll('div');
          div.forEach(function(value,index){
              value.innerText='<b>这是第'+index+'个div</b>';
          });
      };													//<b>这是第i个div</br>
      ```

      ```js
      let arr=[
          {id:1,content:'这是第一个li'},
          {id:2,content:'这是第二个li'},
          {id:3,content:'这是第三个li'},
          {id:4,content:'这是第四个li'}
      ];

      window.onload=function(){
          let str='';
          arr.forEach(function (value,index) {
              str+='<li>'+value.content+'</li>';
          });
          document.querySelector('ul').innerHTML=str;
      };
      ```

* 对于元素属性的操作

  * src alt href id className name value等等

  * ```js
    window.onload=function(){
        let a=document.querySelector('a');
        console.dir(a);
      	a.id='one';
        a.style.color='red';
        a.style.textDecoration='none';
    };
    ```

  * HTML属性是对象，其属性值可以通过对象.属性=属性值来设定

  * 每个HTML属性都有一个style属性，可以修改CSS属性，他也是一个对象，在修改CSS属性时，可以通过对象.style.属性=属性值来进行设置。

* 对于元素样式的操作

  * 要获取元素样式，通过div.style.color的方式，只能获取行内样式。




## 文档树模型

> 整个文档构成了树结构模型

> 整个文档中的各种类型的节点，和节点之间的相互关系，构成了html文档树模型

* 节点

  * 节点的类型

    * 元素
    * 属性
    * 文本
    * 注释
    * 文档

  * 表格

    |      | nodeType | nodeName  | nodeValue |
    | :--: | :------: | :-------: | :-------: |
    |  文档  |    9     | #document |   null    |
    |  元素  |    1     |  大写的标签名   |   null    |
    |  属性  |    2     |    属性名    |    属性值    |
    |  文本  |    3     |   #text   |   文本内容    |
    |  注释  |    8     | #comment  |   注释内容    |

* 节点之间的相互关系

  * 父子关系  同辈关系
    * console.log(div.parentElement);
    * console.log(div.parentNodes);
    * console.log(div.childNodes);
    * console.log(div.children);
    * console.log(div.firstChild);
    * console.log(div.firstElementChild);
    * console.log(div.lastChild);
    * console.log(div.lastElementChild);
    * console.log(div.nextSibling);
    * console.log(div.nextElementSibling);
    * console.log(div.previousSibling);
    * console.log(div.previousElementSibling);

* 操作节点

  * 元素节点

  ```js
  let img=document.createElement('img');	//创建img元素
  div.appendChild(img);					//将img元素放在div中，作为div的最后一个子元素

  let a=document.querySelector('a');		//获取a元素
  div.appendChild(a);						//将a元素放到div中，作为div的最后一个子元素，原先所在的										位置没有a元素
  										//实现的元素位置的移动
  document.body.insertBefore(a,div);		//将a元素放在div元素之前

  function inserAfter(newE,oldE) {		//自定义放在元素之后的函数
      let next=oldE.nextElementSibling;
      if(next){
          oldE.parentNode.insertBefore(newE,next);
      }
      else{
          oldE.parentNode.appendChild(newE);
      }
  }
  inserAfter(img,b);

  document.body.removeChild(a);

  document.body.replaceChild(img,a);

  let copy=div.cloneNodes();
  let copy2=div.cloneNodes(true);
  ```

  * 属性节点

    当自定义属性时，通过div.aa的方式是无法获取非正式属性的，只有通过attributes才能获取，attributes中存放了元素的所有正式和非正式的属性

  ```js
  let div=document.querySelector('div');	//<div aa='bb'></div>
  div.attribute.aa;						//获取自定义aa属性
  div.getAttribute('9aa');					//获取自定义aa属性
  div.setAttribute('cc','ddd');			//设置自定义属性cc='ddd'
  ```




## 事件

> 是用户或者是浏览器的一些行为或者是操作

#### 鼠标事件

- click：点击
- dblclick：双击
- mousemove：鼠标移动
- mouseover：鼠标移入
- mouseout：鼠标移出
- mouseenter：鼠标进入
- nouseleave：鼠标离开
- mouseup：鼠标按下
- mousedown：鼠标抬起
- mousewheel：鼠标滚轮

```js
window.onload=function() {
    let div = document.querySelector('div');
    div.style.cssText = 'width:200px;height:200px;background:red';
    div.onclick = function () {
        this.style.background = 'yellow';
    };
    div.ondblclick = function () {
        this.style.background = 'pink';
    };
    div.onmousemove=function () {
        this.style.color='white';
    };
    div.onmouseover=function(){
        this.style.width='300px';
    };
    div.onmouseout=function(){
        this.style.width='200px';
    };
    div.onmouseenter=function(){
        this.style.border='10px solid blue';
    };
    div.onmouseleave=function(){
        this.style.border='10px solid green';
    };
    div.onmousedown=function(){
        this.style.height='300px';
    };
    div.onmouseup=function () {
        this.style.height='200px';
    };
};
```



#### 滚轮事件

```js
let div=document.querySelector('.box');
div.addEventListener('mousewheel',function(){			//一般浏览器
  console.log(1);
});
div.addEventListener('DOMMouseScroll',function(){		//火狐浏览器
  console.log(2);
});
```

```js
<!DOCTYPE html>		//向上滚动高度减小，向下滚动高度增大
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>滚轮事件</title>
</head>
<style>
    .box{
        width: 200px;
        height: 200px;
        background: pink;
    }
</style>
<body>
    <div class="box"></div>
</body>
<script>
    let box=document.querySelector('.box');
    let speed=5;
    function wheel(e) {
        let way=e.wheelDelta||e.detail;				  //前者一般浏览器适用，后者火狐浏览器适用
        if(way===120||way===-3){                      //向上滚动时，火狐浏览器为-3，谷歌浏览器为120
            this.style.height=this.offsetHeight-speed+'px';
        }
        else if(way===-120||way===3){                 //向下滚动时，火狐浏览器为3，谷歌浏览器为-120
            this.style.height=this.offsetHeight+speed+'px';
        }
    }
    box.addEventListener('mousewheel',wheel);
    box.addEventListener('DOMMouseScorll',wheel);
</script>
</html>
```

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>滚轮事件</title>
</head>
<style>
    .box{
        width: 200px;
        height: 200px;
        background: pink;
    }
</style>
<body>
    <div class="box"></div>
</body>
<script>
    let div=document.querySelector('.box');
    function wheel(dom,upfun,downfun) {
        function w(e) {
            e.preventDefault();
            let way=e.wheelDelta||e.detail;
            if(way===120||way===-3){
                upfun.call(dom);            //如果用upfun(),那么这里的this指向的是window,所以需要用
            }                               //call方法来改变this的指向，使this指向dom
            else if(way===-120||way===3){
                downfun.call(dom);
            }
        }
        dom.addEventListener('mousewheel',w);
        dom.addEventListener('DOMMouseScroll',w);
    }
    let speed=5;
    wheel(div,function () {
        this.style.width=this.offsetWidth+speed+'px';
    },function () {
        this.style.width=this.offsetWidth-speed+'px';
    });
</script>
</html>
```

* 改变this指针指向

  * call方法（改变指针指向并执行函数）
  * apply方法（改变指针指向并执行函数）
  * bind方法（改变指针指向但不执行函数）

  ```js
      function fun(a,b){
          console.log(a,b);
          console.log(this.name);
      }
      let obj={
          name:'lisi'
      };
      fun(1,2);
      fun.call(obj,1,2);		//参数一为要改变的this指向，后面的参数是函数的形参
      fun.apply(obj,[1,2]);	//参数一为要改变的this指向，函数的形参用数组的形式传递
  ```

  ​

  ```js
  var nub=200;
  let obj={
    nub:100,
    fun:function(){
      this.nub+=200;
    }
  }
  obj.fun();						//this指向obj
  let f=obj.fun;
  f();							//this指向window
  console.log(nub,obj.nub);		//400 300
  ```





#### 键盘事件

* onkeydown( )：键盘按下时触发
* onkeypress( )：键盘按住时触发
* onkeyup( )：键盘抬起时触发



#### 表单事件

```js
<body>

    <input type="text" />
    <select name="学历" id="">
        <option value="">学士</option>
        <option value="">硕士</option>
        <option value="">博士</option>
    </select>

<script>

    let select=document.querySelector('select');
    let input=document.querySelector('input');
    input.value='默认值';
    input.onfocus=function () {
        console.log('获取焦点');
    };
    input.onblur=function () {
        console.log('失去焦点');
    };
    input.onchange=function () {		//当失去焦点之后才知道是否发生了改变
        console.log('发生改变');
    };
    input.oninput=function () {			//输入框中的内容已发生改变就执行函数
        console.log(input.value);
    };
    select.onchange=function () {
        console.log(1);
    }
    
</script>
</body>
```





####滚动事件

```js
window.onscroll=function(){
  
}
```

- 将一个200宽的div，不断地增大宽度，以每200毫秒的速度增大10px

  ```js
  window.onload=function () {
      let div=document.querySelector('div');
      let str=200;
      setInterval(function (){
          str+=10;
          div.style.width=str+'px';
      },200);
  };
  ```

  ​

- 动画函数 animate

  ```
  动画函数 animate (obj,attrObj,dur,fun,callback)
  obj   要动画的对象
  attrobj   要动画的属性对象
  {width:xxxx,height:xxx,left:xxxx,top:xxxx,opacity:xxx}  //不加单位
  dur   持续时间
  fun   动画方式
  callback 回调函数 

  ```

- offsetleft   offsettop

  - 看上级元素有无定位，如果直接父元素没有定位，一直向上找，如果间接父元素有定位，计算间接父元素的距离，如果一直没有，就计算距离body的
  - 计算有定位属性的上级元素的距离  body
  - 只能获取，不能设置

- 获取屏幕大小

  - document.documentElement.clientHeight 
  - document.documentElement.clientWidth

- 元素滚动条的高度

  - document.documentElement.scollTop
  - document.body.scllTop
  - 能获取，也能设置



#### 事件监听

* addEventListener()

  removeEventListener()

* attachEvent()

  detachEvent()

  ```js
  let div=document.querySelector('div');
      function click() {
          console.log(1);
      }
  div.addEventListener('click',click);
  div.removeEventListener('click',click);

  var div=document.getElementsByTagName('div');
  function click() {
      console.log(1);
  }
  div.attachEvent('onclick',click);
  div.detachEvent('onclick',click);
  ```



#### 事件对象

> 在事件发生的时候，和事件相关的所有信息，会存储在一个对象身上，这个对象，叫做事件对象。

> 在事件发生的时候，js会自动创建一个对象，用来保存事件发生的时候的所有信息，这个对象叫做事件对象

事件源：事件发生在谁身上，谁就是事件源

事件类型

事件处理程序

* altKey

- cancelBubble


- clientX：距离窗口左上角的距离
- clientY
- ctrlKey
- detail
- offsetX：距离事件源左上角的距离
- offsetY
- pageX：页面左上角（body/html）
- pageY
- screenX：屏幕左上角
- screenY
- shiftKey
- return Valve;
- srcElement
- target
- type
- which




#### 事件流

> 当页面中某个元素触发事件的时候，父元素乃至整个页面都会按照一定的顺序来依次触发这个事件，事件触发的顺序，叫做事件流

* 冒泡型事件流

  > 自当前元素向上级元素触发，直到根元素为止

* 捕获型事件流

  > 由根元素向下依次触发，直到当前元素为止

  ```js
  <body>

      <div class="pink">
          <div class="blue">
              <div class="yellow"></div>
          </div>
      </div>

  <script>
      let pink=document.querySelector('.pink');
      let blue=document.querySelector('.blue');
      let yellow=document.querySelector('.yellow');
      //冒泡型事件流
      pink.onclick=function () {
          console.log('pink冒泡');
      };
      blue.onclick=function () {
          console.log('blue冒泡');
      };
      yellow.onclick=function () {
          console.log('yellow冒泡');
      };
      document.body.onclick=function () {
          console.log('body冒泡');
      };
      //捕获型事件流
      pink.addEventListener('click',function () {
          console.log('pink捕获');
      },true);
      blue.addEventListener('click',function () {
          console.log('blue捕获');
      },true);
      yellow.addEventListener('click',function () {
          console.log('yellow捕获');
      },true);
      document.body.addEventListener('click',function () {
          console.log('body捕获');
      },true);
  </script>
  	//点击yellow时，输出结果为：
  	//body捕获
      //pink捕获  
      //blue捕获  
      //yellow冒泡
  	//yellow捕获  
      //blue冒泡  
      //pink冒泡
      //body冒泡
  </body>
  ```

  整体来说，事件流的顺序是先捕获，后冒泡。

* 阻止事件的传递

  * e.cancelBubble=true;
  * e.stopPropagation();
  * 通常写在第一句，冒泡和捕获都可以阻止

* 阻止默认动作

  * e.preventDefault()；
  * e.returnValue=false；

* 事件委托/事件委派

  > 将原本要添加在当前元素身上的事件，放到它的父元素身上代为执行

  * 什么时候需要
    * 如果新增加的大量元素需要事件处理时
    * 需要事件优化
    * ajax返回的数据处理的时候
  * 目标事件源：真正触发事件的元素，用e.target获取
  * 事件源：事件发生在谁身上，谁就是事件源

  ```js
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>事件委派</title>
  </head>

  <style>

      *{
          margin: 0;
          padding: 0;
      }
      .box{
          width: 200px;
          height: 200px;
          background: pink;
          margin: 10px;
      }

  </style>

  <body>

      <button>新增元素</button>
      <div class="box"></div>
      <div class="box"></div>

  <script>
      
      let btn=document.querySelector('button');
      let box=document.querySelectorAll('.box');
      btn.onclick=function () {
          let div=document.createElement('div');
          div.classList.add('box');
          div.innerHTML='这是新添加的元素';
          document.body.appendChild(div);
      };
      document.body.onclick=function (e) {
          if(e.target.nodeName==='DIV'){       		 //判断一
             console.log(1);
          }

          if(e.target.classList.contains('box')){		 //判断二
              console.log(1);
          }
      }
      
  </script>

  </body>
  </html>
  ```

* 可编辑表格

  ```js
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>可编辑表格</title>
  </head>
  <style>
      .box{
          text-align: center;
      }
      table{
          width: 1000px;
          table-layout: fixed;
          margin: 0 auto;
      }
      th,td{
          border-bottom: 1px solid #000;
          height: 40px;
          width: 20%;
          line-height: 40px;
      }
      .add{
          width: 200px;
          height: 30px;
          margin: 10px auto;
          background: pink;
          color: #333;
          text-align: center;
          line-height: 30px;
          border-radius: 5px;
      }
      .del{
          width: 50px;
          height: 30px;
          margin:5px auto;
          background: lightblue;
          border-radius: 5px;
          line-height: 30px;
      }
  </style>
  <body>

      <div class="box">
          <h3>学生管理系统</h3>
          <table cellspacing="0" cellpadding="0">
              <tr>
                  <th>学号</th>
                  <th>姓名</th>
                  <th>年龄</th>
                  <th>性别</th>
                  <th>操作</th>
              </tr>
              <tr>
                  <td>001</td>
                  <td>小明</td>
                  <td>30</td>
                  <td>男</td>
                  <td>
                      <div class="del">删除</div>
                  </td>
              </tr>
          </table>
          <div class="add">添加</div>
      </div>

  </body>
  <script>
      let add=document.querySelector('.add');
      let tbody=document.querySelector('tbody');
      let del=document.querySelectorAll('.del');
      add.onclick=function () {
          let tr=document.createElement('tr');
          tr.innerHTML=`
                  <td></td>
                  <td></td>
                  <td></td>
                  <td></td>
                  <td>
                      <div class="del">删除</div>
                  </td>`;
          tbody.appendChild(tr);
      };
      tbody.onclick=function (e) {
          let tarobj=e.target;
          if(tarobj.classList.contains('del')){
              let tr=tarobj.parentNode.parentNode;
              tbody.removeChild(tr);
          }
          else if(tarobj.nodeName==='TD'&&tarobj.children.length===0){
              let val=tarobj.innerText;
              tarobj.innerHTML=`<input type="text" value="${val}" />`;
              tarobj.firstElementChild.focus();
              tarobj.firstElementChild.onblur=function () {
                  tarobj.innerHTML=this.value;
              }
          }
      };

  </script>
  </html>
  ```





#### 时间

Date  

now

本地时间

let time=new Date(2015,10,1,12,0,0,0)

月份的表示是0-11

let time=new Date("4/2/2014 12:00:00")

getFullYear



#### cookie

> 存储的一个文件，以字符串的形式，以键值对的格式存储

* 存储量 4KB大小

* 不能跨浏览器访问

* 不可跨域访问

* 安全性低

* 分类

  * 有指定生命周期

    ```js
        let now = new Date();
        now.setTime(now.getTime()+20*1000);
        document.cookie='aa=bb;expires='+now.toGMTString();	//必须转换成GMT时间格式
        document.cookie='cc=dd';
        console.log(document.cookie);
    ```

  * 生命周期是浏览器的运行到关闭，只关闭窗口cookie还在，叫做临时cookie

    ```js
        document.cookie='aa=bb';
        document.cookie='cc=dd';
        console.log(document.cookie);
    ```

    ​



## 效果

* 轮播图

  * ```js
    //轮播图
        let banner=document.querySelectorAll('div img');
        let arrowLeft=document.querySelector('.arrowLeft');
        let arrowRight=document.querySelector('.arrowRight');
        let div=document.querySelector('div');
        let n=0;
        function move() {
            n++;
            if (n>=banner.length) {
                n=0;
            }
            banner.forEach(function (val,index) {
                val.classList.remove('bannerActive');
                banner[n].classList.add('bannerActive');
            })
        }
        let t=setInterval(move,2000);
        div.onmouseenter=function () {
            clearInterval(t);
        };
        div.onmouseleave=function () {
            t=setInterval(move,2000);
        };
        arrowLeft.onclick=function () {
            n--;
            if (n<0) {
                n=banner.length-1;
            }
            banner.forEach(function (val,index) {
                val.classList.remove('bannerActive');
                banner[n].classList.add('bannerActive');
            })
        };
        arrowRight.onclick=function () {
            move();
        };
    ```

  * ```js
        let n=0;
        let div=document.querySelector('div');
        let imgs=div.querySelectorAll('div img');
        let circles=div.querySelectorAll('.circle li');
        let arrowLeft=div.querySelector('.arrowLeft');
        let arrowRight=div.querySelector('.arrowRight');
        let flag=true;
        function move() {
            n++;
            if (n>=imgs.length) {
                n=0;
            }
            imgs.forEach(function (val,index) {
                animate(val,{opacity:0},1000);			//用动画来做
                imgs[index].classList.remove('z');
                circles[index].classList.remove('active');
            });
            animate(imgs[n],{opacity:1},1000,function () {
                flag=true;
            });
            circles[n].classList.add('active');
            imgs[n].classList.add('z');
        }
        let t=setInterval(move,3000);
        div.onmouseenter =function () {
            clearInterval(t);
        };
        div.onmouseleave=function () {
            t=setInterval(move,2000);
        };
        arrowLeft.onclick=function () {
            if(!flag){
                return;
            }
            flag=false;
            n--;
            if (n<0) {
                n=imgs.length-1;
            }
            imgs.forEach(function (val,index) {
                animate(val,{opacity:0},1000);
                circles[index].classList.remove('active');
                this.classList.remove('z');
            });
            animate(imgs[n],{opacity:1},1000,function () {
                flag=true;
            });
            circles[n].classList.add('active');
            imgs[n].classList.add('z');
        };
        arrowRight.onclick=function () {
            if(!flag){
                return;
            }
            flag=false;
            move();
        };
        circles.forEach(function (val,index) {
            val.onclick=function () {
                if(!flag){
                    return;
                }
                flag=false;
                circles.forEach(function (value,i) {
                    value.classList.remove('active');
                    animate(imgs[i],{opacity:0},1000);
                    imgs[i].classList.remove('z');
                });
                animate(imgs[index],{opacity:1},1000,function () {
                    flag=true;
                });
                val.classList.add('active');
                imgs[index].classList.add('z');
            }
        });
    ```

  * ```js
        let box=document.querySelector('div');
        let imgs=box.querySelectorAll('div img');
        let circles=box.querySelectorAll('.circle li');
        let arrowLeft=box.querySelector('.arrowLeft');
        let arrowRight=box.querySelector('.arrowRight');
        let flag=true;
        let n=0;
        function move() {
            if(!flag){
                return;
            }
            flag=false;
            n++;
            if(n>=imgs.length){
                n=0;
            }
            imgs.forEach(function (val,ind) {
                val.classList.remove('bannerActive');
                circles[ind].classList.remove('active');
            });
            imgs[n].classList.add('bannerActive');
            circles[n].classList.add('active');
        }
        let t=setInterval(move,2000);
        box.onmouseenter=function () {
            clearInterval(t);
        };
        box.onmouseleave=function () {
            t=setInterval(move,2000);
        };
        arrowRight.onclick=function () {
            move();
        };
        arrowLeft.onclick=function () {
            if(!flag){
                return;
            }
            flag=false;
            n--;
            console.log(n);
            if(n<0){
                n=imgs.length-1;
            }
            imgs.forEach(function (val,ind) {
                val.classList.remove('bannerActive');
                circles[ind].classList.remove('active');
            });
            imgs[n].classList.add('bannerActive');
            circles[n].classList.add('active');
        };
        circles.forEach(function (value,index) {
            value.onclick=function () {
                if(!flag){
                    return;
                }
                flag=false;
                circles.forEach(function (a,b) {
                    a.classList.remove('active');
                    imgs[b].classList.remove('bannerActive');
                });
                value.classList.add('active');
                imgs[index].classList.add('bannerActive');
                n=index;
            };
        });

        imgs.forEach(function (val1) {
            val1.addEventListener('transitionend',function () {      //检测transition结束时间
                flag=true;
            })
        })

    ```

  * ​

* 选项卡

```js
    tabs(tags,imgs);
    for(var i=0;i<tags.length;i++){
        (function (n) {
            tags[n].onclick=function () {
                (function (m) {
                    for(var j=0;j<tags.length;j++) {
                        tags[j].classList.remove('active');
                        imgs[j].classList.remove('active');
                    }
                })(n);
                tags[n].classList.add('active');
                imgs[n].classList.add('active');
            }
        })(i);
    }
```

* ​






# 作业

* 小米苏宁

* 企业站

* jQuery方法2遍

* 安装wamp

* 找一套出行类的app进行模仿

* 手写需求文档（为什么做这个app，背景，意义，用到的技术，负责的部分，收获，遇到的困难）


  要出发周边游 
  穷游锦囊
  坐车网
  微游记
  首旅如家
  懒猫旅行
  春秋旅游
  旅行自由行
  一家民宿
  逸民宿
  易酷
  面包旅行
  寻舍-精品民宿
  大鱼旅行
  蝉游记
  禅游攻略
  小猪短租

  ​

2.



