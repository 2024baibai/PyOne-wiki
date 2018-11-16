# PyOne更新

由于PyOne会经常进行更新（修复bug、优化性能、增加功能）等，当PyOne源码更新之后，可以按照以下步骤进行更新操作：

* PyOne旧版本升级到3.0：**请重装！！！**
* PyOne3.0内小版本更新：

  **拉最新代码**

  ```text
  git pull
  ```

  **重新安装依赖，看是否有新增的依赖包：**

  ```text
  pip install -r requirements.txt
  ```

  **重启网站：**

  ```text
  supervisorctl -c supervisord.conf restart pyone
  ```

  **最好更新一下文件缓存：**

  ```text
  python function.py UpdateFile
  ```

