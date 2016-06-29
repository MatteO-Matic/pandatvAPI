#PandatvAPI

##Json android_hd requests

###Retrive frontpage'ish channels
Returns two lists containing channels data.

adsdata - List with premium/paid channels(?)

hotdata - Lists the channels with most views

```
http://static.api.m.panda.tv/android_hd/androidhdindex.json
```
[Sample output](/jsonsample/androidhdindex.json)

###Retrive channels from all categories
Returns a list with 10 channels

Field  |Description
----|----
pageno   | Page number. eg. pageno=1 will return first 10 and pageno=2 will return the next batch of 10.
pagenum  | (?)

```
http://static.api.m.panda.tv/android_hd/alllist_.json?pageno=1
```
[Sample output](/jsonsample/alllist_.json)

###Retrive channels from a "game" category
Returns a list with 10 channels from a category.

Field  |Description
----|----
cate   | Game category
pageno   | Page number. eg. pageno=1 will return first 10 and pageno=2 will return the next batch of 10.
pagenum  | (?)


```
http://static.api.m.panda.tv/android_hd/catelist_.json?cate=yzdr&pageno=1&pagenum=20
```
[Sample output](/jsonsample/catelist_.json)

###Retrive game categories
```
http://static.api.m.panda.tv/android_hd/cate.json
```
[Sample output](/jsonsample/cate.json)

