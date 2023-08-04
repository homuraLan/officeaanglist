# officeaanglist
onlyoffice+aria2+AriaNg+AList  
可以在AList获得对onlyoffice的支持，含用户权限，支持多人编辑  
下载docker-compose.yml  
更改其中的数据库密码，路径等等，   
执行  
```
touch /path/to/officeaanglist/redis/redis.conf
sudo docker-compsoe up -d
```   
启动后要等待很长时间，  
```   
ds:docservice: stopped  
ds:docservice: started  
ds:converter: stopped  
ds:converter: started  
* Reloading nginx configuration nginx  
   ...done.  
```  
出现以上内容代表成功，如果提示失败可以执行  
```   
sudo docker restart officeaanglist
```   
删除映射目录app中的文件，以及数据库目录然后可以达到对容器重置的效果。
然后访问，  
AList: https://example.com/AList  
AriaNg: https://example.com/AriaNg  
aria2: https://example.com/aria2  
Edier：https://example.com/viewer  
AriaNg配置：https://example.com/aria2/jsonrpc  秘钥：QQ943384135
AList相同  
AList账号，
账号：admin
密码：admin
```   
sudo docker exec -it officeaanglist bash
/var/www/app/alist admin
```   
编写了外部alist逻辑，暂未测试
![image](https://github.com/alist-org/alist/assets/96775034/30eb1b28-bd80-41ca-965b-9fff6e37cfe3)
