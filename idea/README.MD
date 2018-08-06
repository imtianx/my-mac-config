
# IDEA active license server 

```
chmod +x IdeaLicenseServer
nohup ./IdeaLicenseServer  -u imtianx -prolongationPeriod 999999999999

```

nginx 配置反向代理：

```
server {
    listen 80;
    server_name idea.imtianx.cn;
    index  index.html index.htm index.php;

    location / {
        proxy_pass  http://127.0.0.1:1017;

        proxy_redirect     off;
        proxy_set_header   Host             $host;
        proxy_set_header   X-Real-IP        $remote_addr;
        proxy_set_header   X-Forwarded-For  $proxy_add_x_forwarded_for;
        proxy_next_upstream error timeout invalid_header http_500 http_502 http_503 http_504;
      }
}

```

> 注意去掉 nginx 默认 80 的 default相关配置。

原始配置：

```
listen       80 default_server;
listen       [::]:80 default_server;
```

改为：

```
listen       80;
```

最后，在 idea 中使用：
lisence server : [http://idea.imtianx.cn](http://idea.imtianx.cn)


