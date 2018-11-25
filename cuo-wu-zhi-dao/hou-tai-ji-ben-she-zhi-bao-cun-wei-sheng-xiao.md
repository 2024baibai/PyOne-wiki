# 后台-基本设置-保存未生效。

1. 如果是手动运行的网站。即通过以下命令运行的网站，可通过`ctrl+c`结束运行网站，再运行以下命令运行网站。

   ```text
   gunicorn -k eventlet -b 0:34567 run:app
   ```

2. 如果已经配置了开机启动，则可按以下步骤检查：
   * 检查config.py文件，是否对应变量是否生效。
   * 通过运行以下命令重启网站。

     ```text
     supervisorctl -c supervisord.conf restart pyone
     ```



