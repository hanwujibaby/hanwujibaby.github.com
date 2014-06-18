---
layout: post
title: python中执行sql语句
description: "python代码中向mysql中执行sql语句"
modified: 2014-06-18
tags: [python,mysql]
image:
  feature: abstract-3.jpg
comments: true
share: true
---
mysql中执行sql

{% highlight python%}
#coding: UTF-8
import os
import sys
import MySQLdb

htmls = []
widthes=[]
heights=[]
with open("htmls.txt", "r") as f:
     for line in f:
          htmls.append(line)

with open("widthes.txt", "r") as f:
     for line in f:
          widthes.append(line)

with open("heights.txt", "r") as f:
     for line in f:
          heights.append(line)

db = MySQLdb.connect("ip","dbname","dbuser","dbpwd",charset="utf8")
cursor = db.cursor()

for index in range(len(htmls)):
    sql="insert into wl_info(name,cate_id,contentcate_id,contentSubCate_Id,width,height,status,html) values ('黑名单第一季',29,48,26,"+widthes[index]+","+heights[index]+",1,'"+htmls[index]+"')"
    cursor.execute(sql)
db.close()

{% endhighlight %}
