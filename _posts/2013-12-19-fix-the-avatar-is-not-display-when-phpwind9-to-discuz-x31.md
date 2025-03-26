# fix the avatar is not display when phpwind 9 to discuz x 3.1
2013-12-19 16:13:00

phpwind 9 转换到 discuz x 3.1后，按照discuz转换程序的步骤做，头像仍然不显示，后来登录后重新上传头像发现，是文件名的原因，如下操作改名即可（还好我的论坛会员不多，不然手改累死人，当然强大的linux肯定有的批量改文件名的方法，我还没掌握）：

转换好的dx下的头像目录在：**uc_server\data\avatar\000\00**，此目录下又有**00、01、02&hellip;&hellip;13、14**等目录，

我们**拿&lsquo;13&rsquo;这个目录来说事**，为什么会有13这个目录呢，那是因为你的论坛有一千三百多号会员啦，恭喜你~

我的论坛纯粹是因为中间无数垃圾机器注册成的会员，话说很早以前用的是discuz，后来转换到phpwind9，现在又转到discuz&mdash;&mdash;折腾。

打开目录你会发现一个会员头像图片的文件名是这样的:&nbsp;**1314.jpg、1314_middle.jpg、1314_small.jpg**，分别为1314号会员的大中小号头像，我们只要分别改名为**14_avatar_big.jpg、14_avatar_middle.jpg、14_avatar_small.jpg**就行啦，完工，其他的<span>以此</span>类推！**注意，要去掉<strong>文件名里的**目录名，1314只留14就行</strong>。

插个表格，看得清楚一点：
以目录uc_server\data\avatar\000\00\13为例：

phpwind|discuz
--|--
1314.jpg - &gt;|14_avatar_big.jpg
1314_middle.jpg -&gt;|14_avatar_middle.jpg
1314_small.jpg -&gt;|14_avatar_small.jpg


另外还要注意的是每个目录里的1-9的文件名，前面要加'0'，如：**07_avatar_big.jpg、07_avatar_middle.jpg、07_avatar_small.jpg**