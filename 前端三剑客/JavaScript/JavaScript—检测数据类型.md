### JavaScript中的数据类型

> javascript中的数据类型主要有两种分别为``基本数据类型``(简单数据类型或值类型)和``引用数据类型``(复杂数据类型)。

1. 简单数据类型：在存储时变量中存储的是值本身
   * Number(数字)、String(字符串)、undefined(未定义)、null(空)、Boolean(布尔值)、symbol。
2. 复杂数据类型：在存储时变量中存储的仅仅是地址(引用)
   * 通过new关键字创建的对象(系统对象、自定义对象)，如Object、Array、Date、function等

---

### 布尔值为false的条件(仅此五种)

```javascript
console.log('');   //false
console.log(0);    //false
console.log(NaN);  //false
console.log(undefined);//false
console.log();     //false
```

---

### 检测数据类型的方式（四种）

**公共声明**

```javascript
let str = '123';
let num = 456;
let bool = false;
let unde = undefined;
let fun = function(){};
let arr = [];
let vod = null;
let obj = {};
let date = new Date();
```



1. typeof

   > 只能检测基本数据类型，但无法检测引用数据类型，同时无法检测null这个基本数据类型。

   ```javascript
   console.log(typeof str); //string
   console.log(typeof num);  //number
   console.log(typeof bool);  //boolean
   console.log(typeof unde);  //undefined
   console.log(typeof fun);  //function
   console.log(typeof arr);  //object
   console.log(typeof vod);  //object
   console.log(typeof obj);  //object
   console.log(typeof date);  //object
   ```

   * typeof是直接在计算机里面基于二进制值进行检测的，也就是数据类型都是二进制值，对象存储在计算机中，二进制的值都是以000开头，而null值为000，所以typeof(null)为object

2. instanceof

   > 可以检测引用数据类型，但无法检测基本数据类型，同时无法检测null和undefined。

   ```javascript
   console.log(str instanceof String);  //false
   console.log(num instanceof Number);  //false
   console.log(bool instanceof Boolean);  //false
   console.log(unde instanceof undefined);  //error
   console.log(fun instanceof Function);  //true
   console.log(arr instanceof Array);  //true
   console.log(arr instanceof Object);  //true
   console.log(vod instanceof null);   //error
   console.log(obj instanceof Object);  //true
   console.log(date instanceof Date);  //true
   ```

   * instanceof的机制是，只要当前类出现在实例的原型对象上，结果都是true，因为这里arr.__proto__为Array.prototype，然后Array.prototype.__proto__为Object.prototype，也就是arr.__proto__.__proto__为Object.prototype，所以结果为true。也就是说，我们可以更改原型链的指向，导致检测数据类型不准确。

3. constructor

   > 可以检测基本数据类型与引用数据类型，但无法检测undefined与null。

   ```javascript
   console.log(str.constructor === String);  //true
   console.log(num.constructor === Number);  //true
   console.log(bool.constructor === Boolean);  //true
   console.log(unde.constructor === undefined);  //error
   console.log(fun.constructor === Function);  //true
   console.log(arr.constructor === Array);  //true
   console.log(arr.constructor === Object);  //false
   console.log(vod.constructor === null);  //error
   console.log(obj.constructor === Object);  //true
   console.log(date.constructor === Date);  //true
   ```

   * constructor的缺点是我们可以随意更改constructor

     ```javascript
     let a = []
     Array.prototype.constructor = 'a';
     console.log(a.constructor === Array);  //false
     ```

     

4. Object.prototype.toString.call()

   > 可以检测avascript中所有的数据类型，是最标准的。

   ```javascript
   console.log(Object.prototype.toString.call(str));  //[object String]
   console.log(Object.prototype.toString.call(num));  //[object Number]
   console.log(Object.prototype.toString.call(bool));  //[object Boolean]
   console.log(Object.prototype.toString.call(unde));  //[object Undefined]
   console.log(Object.prototype.toString.call(fun));  //[object Function]
   console.log(Object.prototype.toString.call(arr));  //[object Array]
   console.log(Object.prototype.toString.call(vod));  //[object Number]
   console.log(Object.prototype.toString.call(obj));  //[object Object]
   console.log(Object.prototype.toString.call(date));  //[object Date]
   ```

   