@[toc]

> 分支语句：根据不同的条件，执行不同的路径代码，从而得到不同的结果。

### if语句

> if 如果 ; else if 或者 如果 ; else 或者。

```javascript
if(条件表达式){
    //条件语句
}else if(条件表达式){   //...可以为多个
    //条件语句
}else{
    //条件语句
}
```

### switch语句

> switch 开关 ; case 选项 ；break 跳出 ; default  默认。 应用场景：特定值。
>
> 利用表达式的值与case后面的选项值相匹配，若匹配成功，就执行case里的语句；若都没有匹配上，则会执行default里面的语句。

```javascript
switch(表达式){   //表达式的值与value的匹配是全等('===');实际应用中表达式通常为变量;
    case value1:
        //执行语句
    	break;   //如果匹配成功，没有break跳出，则会继续执行下一个case，直到遇到break为止，才会跳出
    case value2:
        //执行语句
        break;
    default:
        //执行最后的语句
}
```
**switch 与 if  语句的区别**：

* switch case语句通常处理比较确定的值，而if语句则更加灵活(可以判断大于小于等)。
* switch语句进行条件判断后直接执行到程序的条件语句，if语句则是依次判断，相比之下switch效率更高。
  * 当分支比较少时，if语句更为合适(效率相对较高)；
  * 当分支比较多时，switch语句更为合适(效率相对较高),结构更为清晰。

### 三元表达式

> 语法：条件表达式 ? 表达式1 : 表达式2 
> 若条件表达式为真，则返回表达式1的值，若表达式为假，则返回表达式2的值

```javascript
let day=5;
day=day<10?'0'+day:day;  //数字补零
let time=hour < 9 ? '早上好' : (hour <= 11 ? '上午好' : (hour <= 13 ? '中午好' : (hour < 20 ? '下午好' : (hour<22?'晚上好':'晚好呀'))))
```

**扩展**

一元表达式：列：num++，只有一个变量

二元表达式：列：1-1，有两个变量

三元表达式：列：flag?num=100:num=99，有三个变量

### continue break关键字

1. continue 用于立即跳出本次循环，继续下一次循环。
	```javascript
	for(let i=1;i<=10;i++){
	    if(i<=5){
	        continue;
	    }
	    console.log(i);   //6 7 8 9 10;
	}
	```

2. break 用于立即跳出整个循环（循环结束）。
	```javascript
	for(let i=1;i<=5;i++){
	    if(i==3){
	        break;
	    }
	    console.log("我吃了"+i+"个包子");   //1 2;
	}
	```