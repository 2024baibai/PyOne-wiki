# 500 Internal Server Error

* 一般是因为服务器内部出现问题，可检查
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

