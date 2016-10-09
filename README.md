# Docker-NodeJS-MySQL

* sudo docker run -d -P -e MYSQL_USER=node -e MYSQL_PASSWORD=node -e MYSQL_DATABASE=nodejs --name mysqlnode orchardup/mysql

* sudo docker run -ti --rm --link mysqlnode:mysql -v $(pwd):/host --entrypoint /bin/bash orchardup/mysql -c "sleep 4; mysql -u node --password=node -h mysqlnode nodejs < /host/customer.sql; exit 0"

* sudo docker build -t nodejs .

* sudo docker run -p 49165:4300 -d --link mysqlnode:mysqlnode nodejs
