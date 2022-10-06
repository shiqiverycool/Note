### 1.利用margin与定位

```css
/*父级*/
position:relative;
/*子级*/
position:absolute;
top:0;
left:0;
bottom:0;
right:0;
margin:auto;
```

###### 详解：

设置margin自动适应,然后设置定位的上下左右都为0,就如四边均衡受力从而实现盒子的居中；

### 2.利用table-cell

```css
/*父级*/
display:table-cell;
text-align:center;
vertical-align: middle;
/*子级*/
display:inline-block
```

###### 详解：

将父盒子设置为table-cell(能够使元素呈单元格的样式显示)，并设置text-align: center(使内容水平居中)；vertical-align:middle(使内容垂直居中);。子盒子设置为inline-block可以使其内容变为文本格式，也可设置宽高；**此方法父级需设置指定高度和宽度，负责无效**

### 3.利用flex弹性盒子

```css
/*父级*/
display: flex;
justify-content: center;
align-items: center;
```

###### 详解：

 使用弹性盒子的时候需要给父级设置display:flex;

在父元素上设置水平justify-content:center;与垂直align-items:center;方向上的排列方式即可

### 4.利用定位+位移

```css
/*父级*/
position:ablative;
/*子级*/
position:absolute;
left:50%;
top:50%;
transform:translate(-50%,-50%)
```

###### 详解：

利用定位将子级进行向右下方向进行"驱逐"，使子级的左上角那一点相对于父级居中，然后使用transform(相对于自身的位移)进行反向位移

### 5.利用定位+margin(宽高的一半)

```css
/*父级*/
position:ralatiive;
/*子级*/
height:50px;
width:50px;
position：absolute;
top:50%;
left:50%;
margin-top:-25px;
margin-left:-25px;
```

###### 详解：

利用定位将盒子挤向右下方，再利用margin进行反向回推。

(原理和定位+位移的方法如同一辙)