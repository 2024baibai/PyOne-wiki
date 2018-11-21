# 离线下载无法使用？

检查以下几点：

* 检查**Aria2是否安装**。

  运行下面命令，如果显示`/usr/bin/which:` **`no aria2c`** ``说明**没有安装aria2**。

  ```text
  which aria2c
  ```

* 检查**Aria2是否运行**。

  运行下面命令，如果**没有输出任何东西**，说明没有运行aria2。

  ```text
  pgrep -l aria2c
  ```

* 检查**PyOne是否正确配置Aria2信息**。

  登录**PyOne后台-&gt;基本设置-**&gt;**Aria2信息编辑，**检查：**协议、主机、端口、密钥**是否正确。



