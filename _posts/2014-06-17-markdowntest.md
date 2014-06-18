---
layout: post
title: python刷web接口
description: "AIO例子"
modified: 2014-06-18
tags: [python]
image:
  feature: abstract-3.jpg
comments: true
share: true
---


{% highlight python%}
```python
import os
import sys
import MySQLdb
import urllib2                                                                                                                          
 
starIds=[]
ups=[]
 
with open("startid.txt", "r") as f:
     for line in f:
          starIds.append(line)
 
with open("up.txt", "r") as f:
     for line in f:
          ups.append(line)
 
 
 
for i in range(len(starIds)):
    url='http://10.10.52.214:8060/digg/set.do?type=442&vid='+str(starIds[i].rstrip())+'&up='+str(ups[i].rstrip())+'&down=1'
    response=urllib2.urlopen(url);
    print response
{% endhighlight %}
