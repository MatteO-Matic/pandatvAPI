#PandatvAPI

##Requests

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
cate   | Game category. You can use "ename" from [cate.json](#retrive-game-categories)
pageno   | Page number. eg. pageno=1 will return first 10 and pageno=2 will return the next batch of 10.

```
http://static.api.m.panda.tv/android_hd/catelist_.json?cate=yzdr&pageno=1
```
[Sample output](/jsonsample/catelist_.json)

Another way:

Field  |Description
----|----
cate   | Game category. You can use "ename" from [cate.json](#retrive-game-categories)
pageno   | Page number. eg. pageno=1 will return first 10 and pageno=2 will return the next batch of 10.
pagenum  | Number of channels to retrive
__plat| (android, android_hd)
__version| "1.0.1.1303" from client

```
http://api.m.panda.tv/ajax_get_live_list_by_cate?cate=dota2&pageno=1&pagenum=4&__version=1.0.1.1303&__plat=android_hd
```
[Sample output](/jsonsample/ajax_get_live_list_by_cate.json)

###Retrive game categories
```
http://static.api.m.panda.tv/android_hd/cate.json
```
[Sample output](/jsonsample/cate.json)

Another way:

Same as cate.json + one extra category "cartoon". Might return different things depending on version and platform.

Field  |Description
----|----
__plat| (android, android_hd)
__version| "1.0.1.1303" from client
```
http://api.m.panda.tv/ajax_get_all_subcate
```
[Sample output](/jsonsample/ajax_get_all_subcate.json)

###Get channel info
Note: Seems like this response breaks the json RFC 4627 format. (At "details")

Field  |Description
----|----
roomid| Unique id. Same number in the url (eg. panda.tv/3331). Refered as "id" or "roomid" in the responses.
```
http://www.panda.tv/api_room?roomid=3331
```
[Sample output](/jsonsample/api_room.json)

###Get channel info2
Field  |Description
----|----
roomid| Unique id. Same number in the url (eg. panda.tv/3331). Refered as "id" or "roomid" in the responses.
method| (?)
__plat| (android, android_hd)
__version| "1.0.1.1303" from client
```
http://room.api.m.panda.tv/index.php?method=room.getinfo&roomid=3331&__plat=android_hd&&__version=1.0.1.1303
```
[Sample output](/jsonsample/getinfo_room.json)

###Search on roomid
Field  |Description
----|----
roomid| Unique id. Same number in the url (eg. panda.tv/3331). Refered as "id" or "roomid" in the responses.
```
http://api.m.panda.tv/ajax_search?roomid=3331
```
[Sample output](/jsonsample/ajax_search.json)

###Get account info

Field  |Description
----|----
option | Get option value (bamboos, .. (?) )
2Cishost|Check if you are host over given roomid
2Cisbanned| -
2Cexp| -
roomid| Unique id. Same number in the url (eg. panda.tv/3331). Refered as "id" or "roomid" in the responses.
```
http://www.panda.tv/ajax_get_myinfo?option=bamboos%2Cishost%2Cisbanned%2Cexp&roomid=3331
```
[Sample output](/jsonsample/ajax_get_myinfo.json)
