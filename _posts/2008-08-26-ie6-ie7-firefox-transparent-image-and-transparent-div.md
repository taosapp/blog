---
title: ie6 ie7 firefox transparent image and transparent div
date: 2008-08-26 17:40:00
---

for image:

```html
<style type="text/css">
.flower {
   .flower {background:url(flower.png) no-repeat; height:100px; width:100px}
}
</style>
<!--[if IE 5 ]>

<style type="text/css">

.flower {
   background:none;
   filter:progid:DXImageTransform.Microsoft.AlphaImageLoader(src='flower.png', sizingMethod='crop');
}
</style>
<![endif]-->
```

from http://parandroid.com/how-to-make-transparent-picture-of-the-png-format-in-ie6-under-normal-display/

for div:

```css
opacity: 0.6;
filter: alpha(opacity=60);
```