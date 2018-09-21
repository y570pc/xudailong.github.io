---
layout: post
title:  "利用Github和Jekyll搭建个人博客"
categories: 网站搭建
tags: Github Jekyll 
author: y570pc
---

* content
{:toc}

## Fork https://github.com/xudailong/xudailong.github.io（博客模板）到我的仓库（repository）

{% highlight ruby %}
def foo
  puts 'foo'
end
{% endhighlight %}


## 找到我的相应仓库，点击Settings，rename仓库名。

这里我将pycharm下载并解压到了/home/snakeson/developer文件夹下

这里的pycharm.sh是批处理执行文件，prcharm.png是快捷方式图标

## 终端打开

使用Ubuntu终端进行打开：
方法一（使用vim）：
```js
sudo vi  /usr/share/applications/pycharm.desktop
```

方法二（使用gedit）：
	
```js
sudo gedit  /usr/share/applications/pycharm.desktop
```
![有帮助的截图]({{ site.url }}/aa.jpg)



然后就会弹出一个新框：
## 张贴
我们将下面的内容贴上去：
```js

[Desktop Entry]
Type=Application
Name=Pycharm
GenericName=Pycharm3
Comment=Pycharm3:The Python IDE
Exec="/home/snakeson/developer/pycharm-community-2017.2.3/bin/pycharm.sh" %f
Icon=/home/snakeson/developer/pycharm-community-2017.2.3/bin/pycharm.png
Terminal=pycharm
Categories=Pycharm;

```
---
注意一定要将Desktop Entry复制进去，也就是上面的全部都要复制进去，这里我们需要替换掉两个地方：**Exec="xx"**和**Icon=**,这里要替换掉我们的pycharm解压的目录，当然了，我已经替换好了，如果你的目录跟我的目录不一样的话，你得把路径给换了，不管你是pycharm2017还是pycharm2016,，例如Comment什么的都不要改变，只变上面提到的两个路径就可以了。


## 添加可执行权限
```js
sudo chmod +x /usr/share/applications/pycharm.desktop
```

## 拷贝到桌面
```js
将/usr/share/applications/pycharm.desktop文件拷贝到桌面，双击即可运行。
```