#python中字符串去除\n
@(python)[python|urllib2|字符串|折行]

python字符串不折行

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
```
