# 更新缓存

### 更新命令格式：

```text
python /root/PyOne/function.py UpdateFile [可选:更新方式] [可选:网盘选择]
```

两个可选的参数：

1. **更新方式**：可选"new"、"all"，new代表增量更新，all代表全量更新。默认是all
2. **网盘选择**：默认全部网盘一起更新。如果更新特定网盘，则改为对应网盘的**盘符**。

### 示例

#### 全部网盘全量更新（默认）

即全量更新文件目录。推荐在**文件目录结构发生变化**的情况下才进行本操作。

**命令（确保目录正确）：**

```text
python /root/PyOne/function.py UpdateFile
```

#### 全部网盘增量更新

即只有当文件夹大小发生变化时才进行更新操作。推荐在文**件目录结构没有发生变化**的情况下进行操作。

**命令（确保目录正确）：**

```text
python /root/PyOne/function.py UpdateFile new
```

#### 网盘A全量更新

```text
python /root/PyOne/function.py UpdateFile all A
```

#### 网盘A增量更新

```text
python /root/PyOne/function.py UpdateFile new A
```

