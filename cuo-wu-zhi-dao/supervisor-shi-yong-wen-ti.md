# supervisor使用问题

1. `supervisord -c supervisord.conf`出现以下错误： `Error: Another program is already listening on a port that one of our HTTP servers is configured to use. Shut this program down first before starting supervisord. For help, use /usr/bin/supervisord -h` 这种情况一般是因为你已经运行过这个命令了，重复运行就会出现这个错误，可运行： `supervisorctl -c supervisord.conf restart pyone`
2. `supervisorctl -c supervisord.conf restart pyone`出现以下错误： `pyone: ERROR (not running) pyone: ERROR(spawn error)` 可手动运行网站查看是什么问题导致，手动运行命令： `gunicorn -keventlet -b 0:34567 run:app`
3. 手动运行网站常见错误：

```python
ConnectionError: Error 111 connecting to localhost:6379. ECONNREFUSED
```

**6379端口有问题，6379是什么服务？redis！说明你可能没有安装或者运行redis**

```text
ServerSelectionTimeoutError: localhost:27017: [Errno 111] ECONNREFUSED
```

**27017端口有问题，27017是什么服务？MongoDB！说明你可能没有安装或者运行MongoDB**

