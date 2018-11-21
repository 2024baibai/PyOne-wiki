# 502 Bad Gateway

* 一般是网站没有运行导致的。在网站目录运行

  ```text
  supervisord -c supervisord.conf
  ```

* 如果运行上面的命令出现类似`Error:Another program is alright listening on a port`的错误，说明已经运行过这个命令，可以运行以下命令重启网站

  ```text
  supervisorctl -c supervisord.conf restart pyone
  ```

