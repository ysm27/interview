BFC 是页面中的一块渲染区域，并且有一套渲染规则，它决定了其子元素将如何定位，以及和其他元素的关系和相互作用。



**触发BFC**

只要元素满足下面任一条件即可触发 BFC 特性：

1. body 根元素
2. 浮动元素：float 除 none 以外的值
3. 绝对定位元素：position (absolute、fixed)
4. display 为 inline-block、table-cells、flex
5. overflow 除了 visible 以外的值 (hidden、auto、scroll)



**BFC的特性和应用**

BFC特性的元素可以看作是隔离的独立容器，容器里面的元素不会在布局上影响到外面的元素，BFC具有普通容器没有的一些特性。

1、外边距折叠（放在不同的BFC容器中）

2、可以包含浮动元素（清除浮动）（父级overflow: hidden）

3、阻止元素被浮动元素覆盖（第二个元素overflow: hidden）