# 上传文件

### 单文件上传

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

### 批量上传文件

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
   /root/PyOne/function.py UploadDir /home/test /测试/ A
  ```

