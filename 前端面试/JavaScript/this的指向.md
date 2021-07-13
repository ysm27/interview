this 是 JavaScript 的一个关键字，它的使用方法类似于一个变量，它会随着执行环境的改变而改变。

this 可分为以下几种情况：

1. 严格模式下，如果this没有被执行环境定义，那this为undefeated；

2. 方法调用下，this 总是指向调用它所在方法的对象（谁调用的就指向谁）；

   ```javascript
    var obj = {
      fn: function () {
        console.log(this); // obj
      }
    }
    obj.fn();
   ```

3. 在函数调用下(直接调用函数），this 指向 window。调用方法没有明确对象的时候，this 指向 window，如 setTimeout、匿名函数等；

   ```javascript
     function fn() {
        console.log(this);   // window
     }
   	fn();  //  window.fn（),此处默认省略window
   ```

4. 在构造函数调用模式下，this 指向被构造的对象（即实例对象）；

   ```javascript
   function Person(age, name) {
     this.age = age;
     this.name = name
     console.log(this)  // 此处 this 分别指向 Person 的实例对象 p1 p2
   }
   var p1 = new Person(18, 'zs')
   var p2 = new Person(18, 'ww')
   ```

5. 通过事件绑定的方法（DOM事件绑定）， 此时 this 指向 绑定事件的对象；

   onclick和addEventerListener中 this 默认指向绑定事件的元素。

   ```javascript
   <body>
       <button id="btn">hh</button>
   <script>
       var oBtn = document.getElementById("btn");
       oBtn.onclick = function() {
           console.log(this); // btn
       }
   </script>
   </body>
   ```

6. 箭头函数，在声明的时候绑定this，而非取决于调用的位置；

   箭头函数没有this，因此不能绑定。里面的this会指向当前最近的非箭头函数的this，找不到就是window（严格模式是undefined）。

   ```javascript
   let obj = {  a: function() {    let do = () => {      console.log(this);    }    do();  } } obj.a(); // 找到最近的非箭头函数a，a现在绑定着obj, 因此箭头函数中的this是obj
   ```

7. call、apply、bind 调用模式下，this指向第一个参数；



**优先级: new > call、apply、bind > 对象.方法 > 直接调用。**

