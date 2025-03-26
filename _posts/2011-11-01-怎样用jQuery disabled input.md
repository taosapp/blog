---
title: 怎样用jQuery disabled input
date: 2011-11-01 10:51:33
---

以前只知道: 

添加 $input.attr('disabled','disabled'); 
移除 $input.removeAttr('disabled')

今天工作中发现ie6和ie7中input的颜色不对劲，removeAttr('disabled')之后，颜色显示仍然是disabled状态——淡灰色，后来查到，原来jQuery 1.6+以上版本，要使用： 

$input.prop('disabled', true) 添加
$input.prop('disabled', false) 移除

参考：http://stackoverflow.com/questions/1414365/how-to-disable-an-input-with-jquery