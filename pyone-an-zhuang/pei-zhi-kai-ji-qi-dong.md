# 配置开机启动

网站源码下有个**supervisord.conf**，主要内容如下：

```text
[program:pyone]
command = gunicorn -k eventlet -b 0.0.0.0:34567 run:app
directory = /root/PyOne
autorestart = true
```

主要修改两个地方：

**端口号**：即34567那个端口号，修改为自己选的，或者不改动  
**源码目录**：directory修改为你选的网站目录

修改之后运行下面的命令（记得修改为正确的目录），设置开机启动

```text
echo "supervisord -c /root/PyOne/supervisord.conf" >> /etc/rc.d/rc.local
chmod +x /etc/rc.d/rc.local
```

**重启生效。**

本次不用重启生效的方法：

```text
supervisord -c /root/PyOne/supervisord.conf
```

