1.docker-compose build  
2.docker-compose run rails-container rails new . --force --database=mysql --skip-bundle  
3.database.ymlの内容を修正  
  default: &default  
    adapter: mysql2  
    encoding: utf8  
    pool: 5  
    username: root  
    password: <%= ENV['MYSQL_ROOT_PASSWORD'] %>  
    host: mysql-container  
4.rails/unicorn.rbをapplication/configにコピー  
5.docker-compose run rails-container rake db:create  
6.docker-compose up  
7.http://localhost:3000にアクセス  
