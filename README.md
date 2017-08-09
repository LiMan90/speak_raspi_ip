# 让树莓派说出自己的IP地址

当亲爱的树莓派没有显示器时如何控制它？对，就是ssh，但是ssh需要IP地址啊，树莓派的IP地址是多少？这个问题问的好，目前大约有这样几种解决方案：、

- 获取到IP地址后将地址发到邮箱：前提是树莓派能上网
- 通过串口连接树莓派后查看IP地址：需要USB转串口设备，还要连线，小白用户表示鸭梨山大
- 从路由器上查看：如果没有路由器或者没法登上路由器咋办？
- 固定IP地址：假设换到别的网络，网段不一样咋办？地址冲突咋办？
- 通过某些工具扫描整个网段：你确定能扫出来吗？
- 一个一个尝试：如果是A类IP岂不泪奔？

所以嘛，上面的解决方案是有局限性的！有木有更好的方案？`小码哥`告诉你，有！

原理很简单，当树莓派获取到IP地址之后，让它自己说出自己的IP地址就是了。

获取IP地址比较容易，`ifconfig`之类的命令大家也应该听说过。关键是“说”！

其实这个问题也挺简单的，去网上下载`0～9`的数字发音，然后对应着获取的IP地址，依次按顺序读出来就行啦。
树莓派里面是有播放器的，`omxplayer`就是一个。其他的播放器比如`mpg123`也可以的。

你需要做的，就是让树莓派开机自动执行这个程序，然后找个耳机插到树莓派的音频孔里面（表告诉我你木有耳机），
竖起你的耳朵，仔细听就是了～～～

为了方便大家安装，一键脚本已经写好了，大家只要在树莓派上执行这个命令就好了：

```bash
curl "https://github.com/LiMan90/speak_raspi_ip/master/setup.sh" | bash
```
