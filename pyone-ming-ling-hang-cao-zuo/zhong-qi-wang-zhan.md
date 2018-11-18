# 重启网站

这里说的重启网站，是在你配置了开机启动后的网站重启。

如果你还是使用`gunicorn -k eventlet -b 0:34567 run:app`这类手动运行的网站，则只需要`ctrl+C`停止网站后再运行。

**重启命令（确保目录正确）：**

```text
supervisorctl -c /root/PyOne/supervisord.conf restart pyone
```

