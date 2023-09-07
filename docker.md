# docker

```shell
sudo docker network create officeaanglist  

# db  
sudo docker run -d --restart=always \ <br>  
--name officeaanglist-db --hostname db \ <br>  
--env-file .env \ <br>  
-v /path/to/officeaanglist/db:/var/lib/mysql \ <br>  
--network officeaanglist mariadb <br>  

# redis  
sudo docker run --name officeaanglist-redis \ <br>     
--hostname redis --restart always \ <br>   
-v /path/to/officeaanglist/redis/redis.conf:/etc/redis/redis.conf \ <br>   
-v /path/to/officeaanglist/redis/data:/data \ <br>   
--network officeaanglist redis redis-server \ <br>   
/etc/redis/redis.conf --appendonly yes --requirepass 115099 <br>   

# qbittorrent-nox  
sudo docker run --name qbittorrent-nox \ <br>   
--hostname qbittorrent-nox --env-file .env \ <br>   
-p 6901:6901/tcp -p 6881:6881/tcp -p 6881:6881/udp \ <br>   
-v "/path/to/qbittorrent/config:/config" \ <br>   
-v "/path/to/downloads/qbittorrent:/downloads/qbittorrent" \ <br>   
--network officeaanglist qbittorrentofficial/qbittorrent-nox:latest <br>   

#officeaanglist  
sudo docker run --name officeaanglist --restart always \ <br>   
--privileged --hostname officeaanglist --env-file .env \ <br>   
-p 8088:80 -p 83:443 -v /path/to/officeaanglist/logs/onlyoffice:/var/log/onlyoffice \ <br>   
-v /path/to/officeaanglist/logs/nginx:/var/log/nginx \ <br>   
-v /path/to/officeaanglist/aria2:/var/www/app/aria2 \ <br>   
-v /path/to/AList:/AList \ <br>   
-v /path/to/downloads/aria2:/downloads/aria2 \ <br>   
-v /path/to/officeaanglist/lib:/var/lib/onlyoffice \ <br>   
--network officeaanglist homuras/officeaanglist:v0.3.1 <br>   

```


