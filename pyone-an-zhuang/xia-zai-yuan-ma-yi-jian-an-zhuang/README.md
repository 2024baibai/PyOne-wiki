# 下载源码&一键安装

2018.11.19更新之后，新增了一键配置脚本。

一键脚本主要配置以下内容：

1. **自动安装依赖包**；
2. 配置**config.py**和**supervisord.conf**；
3. 配置**开机启动**；
4. **自动安装aria2**；

### 开始安装

{% hint style="info" %}
默认在**/root**目录下进行操作！
{% endhint %}

#### 下载源码

```text
git clone https://github.com/abbeyokgo/PyOne.git
```

#### 使用一键安装脚本

```text
cd PyOne
sh install.sh
```

然后按照提示进行操作！

安装完成提示

![](../../.gitbook/assets/snipaste_2018-11-19_11-05-14.png)

### 运行网站

使用一键安装脚本，并检查文件无误之后，运行下面的命令运行网站

```text
supervisord -c supervisod.conf
```

然后看看是否可以访问：`http://ip:34567`

确保已经开启`34567`端口。

