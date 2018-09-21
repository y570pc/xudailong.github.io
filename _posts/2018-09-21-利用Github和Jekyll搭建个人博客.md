---
layout: post
title:  "利用Github和Jekyll搭建个人博客"
categories: 网站搭建
tags: Jekyll markdown 
author: y570pc
---

* content
{:toc}

## 站在巨人的肩膀上
Fork [xudailong.github.io](https://github.com/xudailong/xudailong.github.io)（博客模板）到我的仓库（repository）。

![01](/img/2018-09-21-01.jpg)

到我的对应仓库，点击Settings，rename仓库名。

![02](/img/2018-09-21-02.jpg)

## 本地编辑
将仓库文件copy到本地。

{% highlight js%}
git clone https://github.com/y570pc/y570pc.github.io
{% endhighlight %}

其中本地_posts文件夹下的md文件即为创建的博文，用mardown语言编写而成。显然md文件的编写难度远小于html文件的编写难度。而Jekyll可将md文件转变成html文件。

将本地文件push到github仓库
{% highlight js%}
git commit -m "message”
git push -u origin master
{% endhighlight %}

## 搭建本地调试环境
1. 安装Ruby 
2. 安装RubyGems
3. 用RubyGems安装Jekyll
4. 开启服务器，jekyll serve
5. 浏览器访问http://localhost:4001/ 

## 样式微调
代码高亮
* 安装pygments
{% highlight ruby%}
gem install pygments.rb
{% endhighlight %}

* 修改配置文件_config.yml
{% highlight js%}
//修改前
markdown: kramdown
kramdown:
  input: GFM
  syntax_highlighter: rouge
  
//修改后
markdown: kramdown
highlighter: pygments
{% endhighlight %}

* md文件实现代码高亮的语法
![03](/img/2018-09-21-03.jpg)

* 显示效果
{% highlight python%}
import speech_recognition as sr
r = sr.Recognizer()
harvard = sr.AudioFile('harvard.wav')
with harvard as source:
    audio =r.record(source)
text = r.recognize_ibm(audio, username='b1c2ce4f-1420-4f49-82c5-ed73cfb320ec', password='BMLcTYAuPCdA', language='zh-CN')
{% endhighlight %}

博文中添加图片
* 在本地仓库的根目录下新建图片文件夹img。将所需的图片保存至该文件夹下。
![04](/img/2018-09-21-04.jpg)

* md文件引用图片的语法
{% highlight js%}
![03](/img/2018-09-21-03.jpg) //[]内可以任意取名，()内即为图片路径
{% endhighlight %}



