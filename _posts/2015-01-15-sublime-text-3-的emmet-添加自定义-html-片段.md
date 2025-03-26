---
title: sublime text 3 的emmet 添加自定义 html 片段
date: 2015-01-15 17:21:00
---

比如想在html写 jquery 直接添加jquery地址，打开 &lsquo;首选项-&gt;Package Setting-&gt;Emmet-&gt;Settings - User&rsquo;，

css也可以如法炮制，代码如下

<pre>{
    "syntaxProfiles": {
        // Enable XHTML dialect for HTML syntax
        "html": "xhtml"
    },
    "snippets": {
        "html": {
            "abbreviations": {
                "jquery": "&lt;script src='http://localhost/static/js/jquery.js'&gt;&lt;/script&gt;"
            }
        },
        "css": {
            "filters": "html",
            "snippets": {
                "csdn":"taodesign.cnblogs.com"****
            }
        }
    }
}
</pre>

&nbsp;