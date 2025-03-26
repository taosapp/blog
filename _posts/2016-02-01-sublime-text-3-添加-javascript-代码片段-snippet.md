---
title: sublime text 3 添加 javascript 代码片段 ( snippet )
date: 2016-02-01 16:43:00
---

例如：新建console.log();的快捷键为 co

环境：windows 7

**step1:**

Tools -&gt; New Snippet

<pre>
1 &lt;snippet&gt;
2     &lt;content&gt;&lt;![CDATA[consloe.log(${1:this});]]&gt;&lt;/content&gt;
3     &lt;!-- Optional: Set a tabTrigger to define how to trigger the snippet --&gt;
4     &lt;tabTrigger&gt;co&lt;/tabTrigger&gt;
5     &lt;!-- html file --&gt;
6     &lt;!-- &lt;scope&gt;text.html&lt;/scope&gt; --&gt;
7     &lt;!-- css file --&gt;
8     &lt;!-- &lt;scope&gt;source.css, source.less, source.scss, source.stylus&lt;/scope&gt; --&gt;
9     &lt;!-- js file --&gt;
10     &lt;scope&gt;source.js&lt;/scope&gt;
11     &lt;description&gt;console.log&lt;/description&gt;
12 &lt;/snippet&gt;</pre>

*   第二行里的${1:this} 代表光标1所在位置，多个值：比如css的padding:${1:this}${2:this}${3:this}${4:this};
*   tabTrigger：触发词
*   scope：文件格式，多个用半角逗号隔开
*   description：显示在提示右边的描述



**step2：**

保存文件为C:\Users\**_yourname_**\AppData\Roaming\Sublime Text 3\Packages\User\test.sublime-snippet

这个文件夹即package所在文件夹，Preferences -&gt; Browse Packages 然后下面的user文件夹，一定要存为**.sublime-snippet** 后缀



**step3:测试**

打开或新建一个js文件，输入"co"，然后按tab键，即可快捷输入console.log();

注意：html和css、js的snippet 在&lt;scope&gt;&lt;/scope&gt;中的写法不一样，html是&lt;scope&gt;text.html&lt;/scope&gt;，而js、css是&lt;scope&gt;source.js&lt;/scope&gt;和&lt;scope&gt;source.css&lt;/scope&gt;

