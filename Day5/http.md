# 使用Request库进行http请求
## GET请求
r = requests.get(...)
返回结果在r中，例如r.content 返回内容，r.status_code返回状态码
* 不带参数
```
import requests
url = 'https://www.baidu.com/'
r = requests.get(url)
print(r.status_code)
```
* 带参数
```
import requests
url = 'https://www.baidu.com/'
dict1 = {'wd':'python','rn':'10'}   #wd查询内容，rn查询数目
r = requests.get(url,params=dict1)
print(r.status_code)
print(r.url)
```
## 发送POST请求
r = requests.post(...)
```
#!/usr/bin/python
import requests
url="http://my.os/api/notification/charm/"
payload={'message': "Opportunities and challenges together"}
r = requests.post(url, data=payload)
print r.status_code
print r.content
```
做法知道了，可是作用并不清楚啊，之前没弄过http，看了看资料，感觉是挺庞大的一块内容啊
