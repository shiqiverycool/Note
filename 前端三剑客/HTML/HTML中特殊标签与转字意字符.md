@[toc]

### 表单标签
> 一个完整的表单通常由表单域、表单控件、提示信息3个部分组成

#### 基本使用
1. input
	```html
	<form action='url地址|www.baidu.com' method='提交方式|get/post' name='表单域名称|loginForm'>
	    <input type='定义属性值'
	       name='定义input元素的名字'
	       value='定义input元素的值'
	       checked='规定此input元素首次加载时是否被选中|checked'
	       maxlength='规定input元素中输入的字符的最大长度|number'
	       placeholder='为用户提供提示信息'
	       />
	</form>
	```


   其他事项：

     		1.	name和value是每个表单元素都应必有的属性值，主要给后台人员使用
     		2.	单选框和复选框要有相同的name值
     		3.	checked针对于checkbox与radio，作用是默认选中

2. select 下拉框表单元素

   ```html
   <select>
       <option selected='selected'></option>
   </select>
   ```

3. textarea 文本域变淡元素

   ```html
   <textarea clos='每行中的字符数' rows='显示的行数'></textarea>
   ```

4. label标签

	```html
	<label for='input对应的id'></label> <!-- 用于绑定当前的input元素，当点击label中的内容时，会自动将焦点转到input元素上。 -->
	```





#### input中type的属性值

|  属性名  | 描述                                              |
| :------: | :------------------------------------------------ |
|  button  | 定义可点击按钮                                    |
| checkbox | 定义复选框                                        |
|   file   | 定义输入字段和浏览按钮，供文件上传                |
|  hidden  | 定义隐藏的输入字段                                |
|  image   | 定义图像形式的提交按钮                            |
| password | 定义暗文输入框                                    |
|  radio   | 定义单选框 通过相同的name获得互斥效果             |
|  submit  | 定义提交按钮 提交按钮会把表单中的数据发送到服务器 |
|  reset   | 定义重置按钮 重置按钮会清空表单中的所有数据       |
|   text   | 定义单行的输入字段                                |

[HTMl5新增表单控件](https://blog.csdn.net/shiqina/article/details/114819300)

### a 超链接
#### 链接的多种使用方式
```html
<a href='http://www.baidu.com'></a>   <!--外部链接-->

<a href='./index.html'></a>   <!--内部链接-->

<a href='./ting.zip'></a>   <!--下载链接-->

<a href='#'></a>   <!--空链接-->

<a><img src='./tinghua.jpg' /></a>   <!--网页元素链接-->

<a href='#title'>XXX</a>
<h3 id='title'>XXX</h3>   <!--锚点链接-->
```
#### 链接伪类选择器
>为了确保生效，请按照LVHA的顺序声明
>* ``a:link``   未被访问的链接
>* ``a:-visited``   已被访问的链接
>* ``a:hover``   鼠标指针位于其上
>* ``a:active``   鼠标按下未弹起
### 转字义字符

| 特殊字符 |     描述     |   字符代码   |
| :------: | :----------: | :----------: |
|  `` ``   |     空格     |  ``&nbsp;``  |
|  ``<``   |     小于     |   ``&lt;``   |
|  ``>``   |     大于     |   ``&gt;``   |
|  ``&``   |      和      |  ``&amp;``   |
|  ``￥``  |    人民币    |  ``&yen;``   |
|  ``©``   |     版权     |  ``&copy;``  |
|  ``®``   |   注册商标   |  ``&reg;``   |
|  ``°``   |      度      |  ``&deg;``   |
|  ``±``   |    正负号    | ``&plusmn;`` |
|  ``X``   |     乘号     | ``&times;``  |
|  ``÷``   |     除号     | ``&divide;`` |
|  ``²``   | 平方（上标） |  ``&sup2;``  |
|  ``³``   | 立方（上标） |  ``&sup3;``  |

### script标签中的属性
| 属性    | 作用                                                         |
| ------- | ------------------------------------------------------------ |
| async   | 表示立即下载该脚本，但不妨碍页面中的其他操作，只对外部文件有效 |
| charset | 告诉浏览器用来编码这个 javascript 程序的字符集(由于大多数浏览器会忽略它的值，因此这个属性很少有人用。) |
| defer   | 表示脚本可以延迟到文档完全被解析和显示后再执行。只对外部文件有效。 |
| src     | 表示包含要执行代码的外部文件。                               |
| type    | 表示编写代码使用的脚本语言的内容类型。默认值为text/javascript。 |

### String HTML 包装方法
| 方法                                                         | 描述                         |
| :----------------------------------------------------------- | :--------------------------- |
| [anchor()](https://www.runoob.com/jsref/jsref-anchor.html)   | 创建 HTML 锚。               |
| [big()](https://www.runoob.com/jsref/jsref-big.html)         | 用大号字体显示字符串。       |
| [blink()](https://www.runoob.com/jsref/jsref-blink.html)     | 显示闪动字符串。             |
| [bold()](https://www.runoob.com/jsref/jsref-bold.html)       | 使用粗体显示字符串。         |
| [fixed()](https://www.runoob.com/jsref/jsref-fixed.html)     | 以打字机文本显示字符串。     |
| [fontcolor()](https://www.runoob.com/jsref/jsref-fontcolor.html) | 使用指定的颜色来显示字符串。 |
| [fontsize()](https://www.runoob.com/jsref/jsref-fontsize.html) | 使用指定的尺寸来显示字符串。 |
| [italics()](https://www.runoob.com/jsref/jsref-italics.html) | 使用斜体显示字符串。         |
| [link()](https://www.runoob.com/jsref/jsref-link.html)       | 将字符串显示为链接。         |
| [small()](https://www.runoob.com/jsref/jsref-small.html)     | 使用小字号来显示字符串。     |
| [strike()](https://www.runoob.com/jsref/jsref-strike.html)   | 用于显示加删除线的字符串。   |
| [sub()](https://www.runoob.com/jsref/jsref-sub.html)         | 把字符串显示为下标。         |
| [sup()](https://www.runoob.com/jsref/jsref-sup.html)         | 把字符串显示为上标。         |