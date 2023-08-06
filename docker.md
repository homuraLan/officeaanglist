# docker

docker run -d --restart=always --name officeaanglist-db --env-file .env -v /path/to/officeaanglist/db:/var/lib/mysql --network officeaanglist mariadb
