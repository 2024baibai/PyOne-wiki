# 错误指导

* 502 Bad Gateway
  * 一般是网站没有运行导致的。在网站目录运行

    ```text
    supervisord -c supervisord.conf
    ```

  * 如果运行上面的命令出现类似`Error:Another program is alright listening on a port`的错误，说明已经运行过这个命令，可以运行以下命令重启网站

    ```text
    supervisorctl -c supervisord.conf restart pyone
    ```
* 500 Internal Server Error

  一般是因为服务器内部出现问题，可检查

  * Redis、MongoDB是否安装？是否运行？
  * 如果上诉没问题，可清空Redis缓存：

    ```text
    redis-cli #进入redis命令行
     > FLUSHALL
    ```

  * 如清空Redis缓存还有问题，可手动运行网站查看错误

    ```text
    supervisorctl -c supervisord.conf stop pyone && gunicorn -k eventlet -b 0:34567 run:app
    ```

    然后再访问页面，查看ssh的错误提示









