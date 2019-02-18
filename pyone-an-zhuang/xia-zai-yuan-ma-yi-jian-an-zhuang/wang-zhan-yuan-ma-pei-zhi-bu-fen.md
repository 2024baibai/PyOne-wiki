# 网站源码配置部分

## **如果使用了一键脚本，可跳过本章节。本章节仅供参考。**

**提示：全文默认是在`root`目录下运行。**

**下载脚本**：

```text
git clone https://github.com/abbeyokgo/PyOne.git
```

**安装依赖包**：

```text
cd PyOne
pip install -r requirements.txt
```

**准备文件**：

```text
cp self_config.py.sample self_config.py
cp supervisord.conf.sample supervisord.conf
touch .install
```

**tips:** 如果当前不是在`root`目录下，则需要修改**self\_config.py**的**`config_dir`**参数和**supervisord.conf**的**`directory`**参数为正确的目录！！！

**试运行**

```text
gunicorn -k eventlet -b 0.0.0.0:34567 run:app
```

如果没有问题，则可以访问到：`http://ip:34567`。如果不行，请确保已经开放端口！

