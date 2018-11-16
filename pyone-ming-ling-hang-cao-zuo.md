# PyOne命令行操作

本文介绍一下PyOne的命令行操作，大部分在PyOne的后台都能操作，但是假如你需要写脚本自动上传文件之类的，就可能需要用到命令行啦。

### 重启网站

这里说的重启网站，是在你配置了开机启动后的网站重启。

如果你还是使用`gunicorn -k eventlet -b 0:34567 run:app`这类手动运行的网站，则只需要`ctrl+C`停止网站后再运行。

**重启命令（确保目录正确）：**

```text
supervisorctl -c /root/PyOne/supervisord.conf restart pyone
```

### 上传文件

#### 单文件上传

**命令（确保目录正确）：**

```text
python /root/PyOne/function.py Upload 服务器文件绝对路径 onedrive路径 盘符
```

**说明：**

* **服务器文件绝对路径**：服务器下存在的一**个文件绝对路径**。比如：**/home/test.mp4**。
* **onedrive路径**：即**onedrive下的路径**。这里分两种情况：

  * 上传后不用重命名，比如我直接上传到`测试`目录下，onedrive路径为：`/测试/`。**目录最后面必须带`/`。**
  * 上传后重命名，比如我上传到`测试`目录下，并重命名为`new.mp4`，onedrive路径为：`/测试/new.mp4`。**最后面不能带`/`。**

  **看出区别了吗？带`/`和不带`/`的区别！**

* **盘符**：默认为`A`。如果需要上传到其他网盘，或者你修改过盘符，则修改这个盘符参数。

**示例：**

* 上传服务器的**`/home/test.mp4`**到盘符**`A`**的onedrive的**`测试`**目录下：

  ```text
   /root/PyOne/function.py Upload /home/test.mp4 /测试/ A
  ```

* 上传服务器的`/home/test.mp4`到盘符`A`的onedrive的`测试`目录下，并重命名为`new.mp4`：

  ```text
  python /root/PyOne/function.py Upload /home/test.mp4 /测试/new.mp4 A
  ```

#### 批量上传文件

上传服务器某个**目录下的所有文件**到onedrive。

**命令（确保目录正确）：**

```text
python /root/PyOne/function.py UploadDir 服务器目录绝对路径 onedrive路径 盘符
```

**说明：**

* **服务器目录绝对路径**：服务器下存在的**目录绝对路径**。比如：**/home/test**
* **onedrive路径**：即**onedrive下的路径**。比如：**/test/**
* **盘符**：默认为`A`。如果需要上传到其他网盘，或者你修改过盘符，则修改这个盘符参数。

**示例：**

* 上传服务器的**`/home`**下的所有文件到盘符**`A`**的onedrive的**`测试`**目录下：

  ```text
   /root/PyOne/function.py Upload /home/test /测试/ A
  ```

### 更新缓存

#### 全量更新（默认）

即全量更新文件目录。推荐在**文件目录结构发生变化**的情况下才进行本操作。

**命令（确保目录正确）：**

```text
python /root/PyOne/function.py UpdateFile
```

#### 增量更新

即只有当文件夹大小发生变化时才进行更新操作。推荐在文**件目录结构没有发生变化**的情况下进行操作。

**命令（确保目录正确）：**

```text
python /root/PyOne/function.py UpdateFile new
```

\*\*\*\*

