# HTTP Documentation 中文翻译

## 进度

| 文件    | 进度     | 翻译者 | 校对者 |
| :--     | :--      | :--    | :--    |
| rfc7234 | 正在翻译 | ADoyle |        |

## 依赖

- java
- [itstool](https://github.com/itstool/itstool)，官网 http://itstool.org/
- [msgfmt](https://www.gnu.org/software/gettext/manual/html_node/msgfmt-Invocation.html)
- [saxon](http://www.saxonica.com/documentation/#!about/gettingstarted/gettingstartedjava)

### itsool
用来将 .xml 转成 .po 文件，安装方法看[这里](http://itstool.org/documentation/install)

### msgfmt

用来将 .po 转换成 .mo 文件。

如果你是 mac 用户，可以通过 homebrew 来安装。具体如下

```sh
brew install gettext
ln -s /usr/local/opt/gettext/bin/msgfmt /usr/local/bin
```

### saxon

安装 saxon，只需要下载最新版 [saxon-HE](https://sourceforge.net/projects/saxon/files/Saxon-HE/) ，解压缩以后，将 `saxon9he.jar` 这个文件拷贝到 `specs/lib/saxon9.jar` 即可。


## Quick Start

### 目录

- `specs/` 目录存放源文档 (.xml) 和编译后的网页 (.html)。
- 中文 HTML 文件会输出到 `specs/zh-Hans/`
- 翻译文件在 `specs/po` 里

如果没有对应的 .po 文件，通过 `make po<文档号>` 来生成对应的 .po 文件。

### 🌰

假设你想翻译 rfc7234。只需要执行 `make po7234`。
然后你只需翻译对应的 `specs/po/rfc7234.po` 文件即可。

你可以随时编译浏览 html 文件。通过 `make zh7234` 命令会生成 `specs/zh-Hans/rfc7234.html` 文件。用你的浏览器打开这个文件即可。

## 编译

先切换到 specs 这个目录下 `cd specs`。以下命令提供编译功能：

- `make`: 生成所有英文 HTML 文件和中文 HTML 文件
- `make clean`: 清除编译后的文件
- `make zh<文档号>`: 只生成某个文档的中文 HTML 文件。如 `make zh7234`
- `make zh`: 生成所有中文 HTML 文件
- `make po/<文件名>.po`: 根据 xml 生成 po 文件，用于翻译中文文件。如 `make po/rfc7234.po`
- `make po<文档号>`: 别名。作用同 `make po/<文件名>.po`。如 `make po7234`

如果当前已经存在对应的 html，make 操作会认为文件没有改动，会显示`make: Nothing to be done for 'all' `，即不编译文件。

你需要手动删除对应的 html 文件。
或者执行 `make clean` 删除所有的 .html 文件。

## 版权与协议 (Copyright and License)

源文档版权归遵循源文档的版权协议。

翻译文档的版权遵循 CC 协议，具体如下： 

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" property="dct:title" rel="dct:type">HTTP Documentation 中文翻译</span> 由 <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/adoyle-h/httpwg.github.io" property="cc:attributionName" rel="cc:attributionURL">ADoyle</a> 创作，采用 <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">知识共享 署名-非商业性使用-相同方式共享 4.0 国际 许可协议</a>进行许可。<br />基于<a xmlns:dct="http://purl.org/dc/terms/" href="https://httpwg.github.io/" rel="dct:source">https://httpwg.github.io/</a>上的作品创作。

## 翻译共享者 (Contributors)

- ADoyle <adoyle.h@gmail.com>

