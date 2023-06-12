# officeaanglist
onlyoffice+aria2+AriaNg+AList  
下载docker-compose.yml  
更改其中的数据库密码，路径等等，   
执行  
```   
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
删除映射目录app中的文件然后重启可以对容器达到重置效果，首次启动可能会失败重启一次就好了  
然后访问，  
AList: https://example.com/AList  
AriaNg: https://example.com/AriaNg  
aria2: https://example.com/aria2  
AriaNg配置：https://example.com/aria2/jsonrpc  
AList相同  
虽然日志会输出AList密码，但未必能看到
获取AList密码：  
```   
sudo docker exec -it officeaanglist bash
/var/www/app/alist admin
```   
      
已知在没有证书的情况下，无法使用，暂不准备解决  

