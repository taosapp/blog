---
title: 微信JSSDK，internal error 500
date: 2021-01-04 15:33:00
---

微信JS-SDK官方文档下载的PHP示例代码 https://developers.weixin.qq.com/doc/offiaccount/OA_Web_Apps/JS-SDK.html#67

sample.php填好自己公众号的AppID和AppSecret，并且公众号后台已经设置了安全域名和服务器IP白名单，结果访问链接后出现 Internal error 500错误，这其实是服务器没有安装php-curl及新版curl的php语法问题，解决方法如下：

1. 找到错误，服务器的php.ini里找到 “display_errors = Off” 改成 “display_errors = On”
   - 刚开始也不太确定是nginx还是php的错误，看了nginx的conf配置，而且上传了一个普通php文件，访问没有问题，所以再找PHP的问题，由于 php.ini 里设置了“display_errors = Off”，访问页面除了500错误，不会显示任何错误信息，设为 On 后页面会显示PHP错误

2. PHP错误显示之后，发现是 curl_init 函数未定义，在服务器端安装curl
```bash
    apt install php-curl
    service php7.4-fpm restart // 重启php服务，因为该网站服务器安装的是php7.4
```

3. 修改jssdk.php代码，curl语法升级
```php
# curl_setopt($curl, CURLOPT_SSL_VERIFYHOST, true);
curl_setopt($curl, CURLOPT_SSL_VERIFYHOST, 2);
```
    - \*参考：libcurl早期版本中这个变量是boolean值，为true时作用同目前设置为2，后来出于调试需求，增加了仅校验是否有CN字段的选项，因此两个值true/false就不够用了，升级为0/1/2三个值。（ https://segmentfault.com/q/1010000002396283/a-1020000002396308 ）

再用微信开发工具查看，OK解决！