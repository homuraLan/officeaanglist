# docker

```shell
sudo docker network create officeaanglist  

# db  
sudo docker run -d --restart=always \  
--name officeaanglist-db --hostname db \  
--env-file .env \  
-v /path/to/officeaanglist/db:/var/lib/mysql \  
--network officeaanglist mariadb/server:10.3  

# redis  
sudo docker run -d --name officeaanglist-redis \      
--hostname redis --restart always \  
-v /path/to/officeaanglist/redis/redis.conf:/etc/redis/redis.conf \    
-v /path/to/officeaanglist/redis/data:/data \    
--network officeaanglist redis:7.2.1-alpine3.18 redis-server \   
/etc/redis/redis.conf --appendonly yes --requirepass 115099

# qbittorrent-nox  
sudo docker run -d --name qbittorrent-nox \    
--hostname qbittorrent-nox --env-file .env \    
-p 6901:6901/tcp -p 6881:6881/tcp -p 6881:6881/udp \   
-v "/path/to/qbittorrent/config:/config" \    
-v "/path/to/downloads/qbittorrent:/downloads/qbittorrent" \    
--network officeaanglist qbittorrentofficial/qbittorrent-nox:latest    

#officeaanglist  
sudo docker run -d --name officeaanglist --restart always \    
--privileged --hostname officeaanglist --env-file .env \   
-p 8088:80 -p 83:443 -v /path/to/officeaanglist/logs/onlyoffice:/var/log/onlyoffice \   
-v /path/to/officeaanglist/logs/nginx:/var/log/nginx \ 
-v /path/to/officeaanglist/aria2:/var/www/app/aria2 \   
-v /path/to/AList:/AList \ 
-v /path/to/downloads/aria2:/downloads/aria2 \  
-v /path/to/officeaanglist/lib:/var/lib/onlyoffice \     
--network officeaanglist homuras/officeaanglist:v0.3.1    

```


