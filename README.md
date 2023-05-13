# Hack Scanner

本项目实现一个Web应用程序，集成常见web漏洞扫描和网页爬虫，支持多线程扫描和中英文。

平台依照页面提示输入url和线程数，脚本会开始爬取网站前端代码资源。资源爬完后存储到本地。然后软件开始扫描路径下文件。扫描完毕返回结果，删除过期的下载资源。

可以点击`Download report`下载扫描结果报告。点击`Clean`清除扫描报告的打印结果。

### 1. 依赖安装
本项目涉及的技术包括Redis、Django框架、Channels和Websocket。

建议创建虚拟环境，然后执行以下命令：
```
pip install -r requirements.txt
```



### 2. 启动项目

本平台使用Django架构，使用ASGI服务器Daphne，启动需要切换到`hackScannerWeb/`目录下，在终端输入

```
daphne -e ssl:8001:privateKey=7586419_www.i-test.com.cn.key:certKey=7586419_www.i-test.com.cn.pem hackScannerWeb.asgi:application
```

Django会在本地`https://127.0.0.1:8001`启动服务



### 3. 自定义扫描规则

扫描器，多线程扫描指定url的项目代码，根据正则表达式判断类型。

扫描文件内容，使用正则匹配，匹配模式默认写在`pattern.xml`，可通过修改`pattern.xml`文件修改或增加漏洞特征






