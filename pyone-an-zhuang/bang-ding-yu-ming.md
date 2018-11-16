# 绑定域名

1. 先确保域名已经解析到你的服务器ip
2. 打开宝塔-**网站-添加站点**
3. 设置反代：**宝塔-网站-点击域名-反向代理**，设置值`http://127.0.0.1:34567`然后勾选`启用反向代理`
4. 添加nginx配置：**宝塔-网站-点击域名-配置文件**。找到以下内容，添加**标红**的两行。

```text
location / 
    {
        ...
        
        proxy_buffering off;
        proxy_cache off;
                
        ...
    }
```

**如图**

![](https://i.loli.net/2018/09/13/5b9a468084b14.png)

![](https://i.loli.net/2018/09/13/5b9a47830cb37.png)

做完以上操作，应该就可以访问你的域名了！

![](http://wx1.sinaimg.cn/large/0060lm7Tly1fx8tvab27ij31gq09pq3b.jpg)

