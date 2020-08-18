# PO18-txt-downloader

将 www.po18.tw 上的小说下载为 txt 文稿。

只能取得免费 / 已购章节内容。


开发环境：Python 3.7

参考了 [自制小说下载器](https://mp.weixin.qq.com/s/a0ORywWh1l0lHK5iG2PaUg)（Python 2.7）。


## import

BeautifulSoup

requests

lxml


## How to use

1. 找到要下载的书籍 ID（网址`/books/` 后面那串数字），赋值给 `book_number` 。

2. 找到章节内容总数（看目录里最新一章前面的【四位数字】，或者从 `狀態 未完結(目前xxx章回)` 这里看），赋值给 `chapter_sum`。

3. 登录后才可访问小说页面，把 `login()` 里的 `account` 和 `pwd` 赋值为自己的真实账号信息（此信息存在本地，只会发送给 po18 的服务器登录用）。

4. 更改 `txt = open('路径' + book_number + '.txt', 'a')`，随便找个文件夹路径，替换掉中文字符。

5. `login()` -> `data{}` 的 `client_ip` 换成自己的本机 IP（怎么查 IP 莫问我）。适度使用本脚本，网站服务器对访问过于频繁的 IP 将无响应。

6. 如果报错网站无响应，找到最后一次命令行输出 `xx https://www.po18.tw/books/---/articles/----- processing...` ，把数字 `xx` 赋值给 `start`。

   这里通常还需要再修改一下 `getContent(page)` 里的 `page` 参，自己算算。

   重新运行，就会继续下载。（此条可能重复操作数次）




