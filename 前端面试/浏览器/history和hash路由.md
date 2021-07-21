hash模式、history模式

​    1、hash：浏览器地址后面增加#号；

​        特点：

​        1、hash是不会随请求发送到服务器端的，所以改变hash，不会重新加载页面；

​        2、监听 window 的 hashchange 事件

​        3、 location.hash 来获取和设置hash值

​    2、history模式

​        特点：

​         1、window.history 属性指向 History 对象

​        2、back go forward pushState   replaceState

​        3、每当 history 对象出现变化时，就会触发 popstate 事件。