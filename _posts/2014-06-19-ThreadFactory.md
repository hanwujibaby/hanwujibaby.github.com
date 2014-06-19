--- 
layout: post
title: ThreadFactory
description: "java threadFactory接口"
modified: 2014-06-19
tags: 
  java
  concurrent
  threadFactory
image:
  feature: abstract-5.jpg
comments: true
share: true
---

java threadFacotry接口，可以避免对线程的hard writing,比如

{% highlight java%}
    Thread t=new Thread(new Runnable(){
            do someting...
        });
{% endhighlight%}

可以指定thread的优先级等

{% highlight java %}
package java.util.concurrent;

public interface ThreadFactory {

    Thread newThread(Runnable r);
}

{% endhighlight %}


