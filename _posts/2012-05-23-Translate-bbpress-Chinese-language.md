---
title: Translate bbpress Chinese language
date: 2012-05-23 11:59:35
---

I was looking for the latest 2.0 bbpress Chinese language package but not result. then I saw the page [http://translate.wordpress.org/projects/bbpress/plugin/zh-cn/default](http://translate.wordpress.org/projects/bbpress/plugin/zh-cn/default), showing the translate progress only complated 30%.

## bbpress translate steps

1.  there is a *Export* at the bottom of the above page, select the `all cuurent` and `po, mo` files, export them, download to the files `bbpress-plugin-zh-cn.mo` and `bbpress-plugin-zh-cn.po`
2.  rename to `bbpress-zh\_CN.mo, bbpress-zh\_CN.po`
3.  create a new `bbpress` folder in `wp-contentlanguages`
4.  upload the 2 files to `wp-contentlanguages/bbpress/`

After a half day in http://translate.wordpress.org/projects/bbpress/plugin/zh-cn/default, translated handred items, I found the translated items aren't show when they are `waiting for validation`. So make po files ourselves, refer to [this article](http://zmingcx.com/edit-mo-of-documents.html), there is a mo file editor. First, change some bad translation, such as `sticky` and `super sticky` in `topic type`, be translated `粘性, 超级粘性`, WT*. They are should be `分区置顶, 论坛置顶`.