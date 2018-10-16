# HTTP

HTTP 是超文本传输协议（hypertext transfer protocol）的缩写。

(常见语病：「HTTP 协议」。「P」和「协议」同义重复了，只用「HTTP」即可)

HTTP 规定了客户端和服务器之间传输网页和文件的办法。

客户端：例如浏览器、爬虫、手机应用。
服务器：用网址定位，一般运行于一台电脑上的 80 或者 443 端口。

HTTP 请求由以下部分组成：

- 请求行，包含请求动作和请求路径，HTTP 的版本，例如 `GET /images/logo.gif HTTP/1.1`
- 多个请求头，例如告诉服务器我希望获得中文的响应 `accept-language: zh`
- 一个空行
- 可选的消息体 (body)

常用的 HTTP 请求动作有

- `GET`
- 

HTTP 响应由以下部分组成：

- 响应行，包含 HTTP 版本和响应代码，例如 `HTTP2 200`
- 多个响应头，例如告诉客户端消息体的格式 `content-type: image/gif`
- 一个空行
- 可选的消息体

常见的响应代码

- 2XX 正常工作，如 200 OK, 201 部分 OK
- 3XX 免传输，如 302 跳转，304 网页没变化
- 4XX 客户端出问题了，如 400 非法请求，404 资源没找到
- 5XX 服务器出问题了，如 500 服务器错误, 504 网关错误

使用 Chrome 开发者工具查看请求

(todo 截图)

# 处理 HTTP 的库

PyPI: [Python 包索引](https://pypi.org/)（Python Package Index) 是一个软件仓库，帮助你搜索、安装和分享 Python 软件。开放的 PyPI 上丰富的三方库是 Python 成功的要素之一。

Requests 是一个方便的 HTTP 请求库。在命令行使用 pip 从 PyPI 上安装 requests：

    pip install requests

注意：PyPI 上的库多数是开源的或者免费的，但是使用新的库时最好注意一下使用条款。

# Requests 的使用

    import requests
    response = requests.get('https://c.xkcd.com/random/comic/')
    response.text # 看到网页的源代码