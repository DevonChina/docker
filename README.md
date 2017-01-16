## 服务列表如下
```
- db：使用 mariadb 作为应用的数据库
- php：解释 php 脚本，使用 php-fpm
- web：使用 NGINX 作为应用的 web 服务器
- console：我们把开发中需要的所有工具放在此处进行构建
- redis：缓存
- phpmyadmin：管理数据库的 web 界面(方便我们本地对数据库进行管理)
```

1 → 克隆仓库到本地

```
git clone https://github.com/DevonChina/docker.git
```
2 → 进入项目所在目录
```
cd devon
```
3 → 创建并启动服务
```
docker-compose build
docker-compose up -d
```

构建完成相关服务之后，我们需要把的 PHP 应用比如 laravel 或 phpcms 放到 /var/www/htmnl 这个目录里面，然后去安装一下就行了。注意在安装的时候，数据库主机的名字应该是 `db`，而不是 `localhost` 。


4 → 在浏览器里打开
```
http://localhost:80   ```注意：如果你本地已经构建过开发环境，那么服务应该是已经占用了80端口，可以考虑使用8080端口，因为我本地环境是干净的，所以我直接使用了80端口```

```
我们来看看phpinfo是否能正常输出

![image](http://devon.oss-cn-hangzhou.aliyuncs.com/others/phpinfo.png)

再看看我们构建的Laravel服务是否成功
![image](http://devon.oss-cn-hangzhou.aliyuncs.com/others/hello.png)
