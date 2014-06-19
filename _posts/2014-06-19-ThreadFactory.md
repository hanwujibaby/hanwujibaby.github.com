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
java.util.concurrent.ThreadFactory

/*
An object that creates new threads on demand. Using thread factories removes hardwiring of calls to 
 new Thread, enabling applications to use special thread subclasses, priorities, etc. 
The simplest implementation of this interface is just: 
 class SimpleThreadFactory implements ThreadFactory {
   public Thread newThread(Runnable r) {
     return new Thread(r);
   }
 }
 The Executors.defaultThreadFactory method provides a more useful simple implementation, that sets 
  the created thread context to known values before returning it.
Since:
     1.5
Author:
     Doug Lea

*/

package java.util.concurrent;
public interface ThreadFactory {
    Thread newThread(Runnable r);
}

{% endhighlight %}


