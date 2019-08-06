# 配置说明

## HTTPS 自签名证书

```
openssl req -x509 -nodes -days 36500 -newkey rsa:2048 -keyout ./nginx-conf/nginx/ssl/nginx.key -out ./nginx-conf/nginx/ssl/nginx.crt
```
参数说明：

-x509 指定使用X.509证书签名请求管理
-nodes openssl 生产证书时忽略密码环节
-days  证书有效时间
-newkey rsa:2048 产生一个新证书和一个新的SSL key
-keyout SSL输出文件名
-out   证书生成文件名

问题：
> 注意：Common Name 可以使用泛域名来生成二级域名可用的网站证书

## 配置注意事项

+ server_name 中定义的域名需要在本地 `hosts` 中配置
    > 127.0.0.1  mytest111.com
