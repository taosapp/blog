---
title: hammerjs jquery的选项使用方法，以给swipe设置threshold和velocity为例
date: 2015-11-17 16:14:00
---

先包含hammer.min.js和 jquery.hammer.js，然后：

<pre>var $ele = $('#ele'); //复用jquerydom对象，建个变量
$ele.hammer().on("swipeleft", swipeLeftHandler).on("swiperight", swipeRightHandler); //添加左划右划事件

//设置选项
$ele.data('hammer').get('swipe').set({
    threshold: 1,
    velocity: 0.50
});

function swipeLeftHandler () {
    //左划之后的功能
}

function swipeRightHandler () {
    //右划之后的功能
}</pre>

&nbsp;