# 更新缓存

### 全量更新（默认）

即全量更新文件目录。推荐在**文件目录结构发生变化**的情况下才进行本操作。

**命令（确保目录正确）：**

```text
python /root/PyOne/function.py UpdateFile
```

### 增量更新

即只有当文件夹大小发生变化时才进行更新操作。推荐在文**件目录结构没有发生变化**的情况下进行操作。

**命令（确保目录正确）：**

```text
python /root/PyOne/function.py UpdateFile new
```

\*\*\*\*

