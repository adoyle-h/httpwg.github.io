# HTTP Documentation 中文翻译

## 进度

| 文件    | 进度     | 翻译者 | 校对者 |
| :--     | :--      | :--    | :--    |
| rfc7234 | 正在翻译 | ADoyle |        |

## Quick Start

`specs/` 目录存放源文档 (.xml) 和编译后的网页 (.html)。


### 依赖

java 与 [saxon](http://www.saxonica.com/documentation/#!about/gettingstarted/gettingstartedjava)

安装 saxon，只需要下载最新版 [saxon-HE](https://sourceforge.net/projects/saxon/files/Saxon-HE/) ，解压缩以后，将 `saxon9he.jar` 这个文件拷贝到 `specs/lib/saxon9.jar` 即可。

### 编译

先切换到 specs 这个目录下 `cd specs`。

执行 `make` 编译所有文件，或者 `make <文档名>.html` 编译某个文件。

如果当前已经存在对应的 html，make 操作会认为文件没有改动，会显示`make: Nothing to be done for 'all' `，即不编译文件。

你需要手动删除对应的 html 文件。
或者执行 `make clean` 删除所有的 .html 文件。

## 版权与协议

源文档版权归遵循源文档的版权协议。

翻译文档的版权遵循 CC 协议，具体如下： 

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" property="dct:title" rel="dct:type">HTTP Documentation 中文翻译</span> 由 <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/adoyle-h/httpwg.github.io" property="cc:attributionName" rel="cc:attributionURL">ADoyle</a> 创作，采用 <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">知识共享 署名-非商业性使用-相同方式共享 4.0 国际 许可协议</a>进行许可。<br />基于<a xmlns:dct="http://purl.org/dc/terms/" href="https://httpwg.github.io/" rel="dct:source">https://httpwg.github.io/</a>上的作品创作。

## 翻译共享者 (Contributors)

- ADoyle <adoyle.h@gmail.com>
