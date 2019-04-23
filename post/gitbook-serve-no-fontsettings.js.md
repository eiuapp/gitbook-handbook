
gitbook serve命令找不到fontsettings.js


### 方法1

```bash
DESKTOP-APB1HCJ% gitbook serve
Live reload server started on port: 35729
Press CTRL+C to quit ...

info: 24 plugins are installed
info: 22 explicitly listed
info: loading plugin "github"... OK
info: loading plugin "codesnippet"... OK
info: loading plugin "splitter"... OK
info: loading plugin "page-toc-button"... OK
info: loading plugin "editlink"... OK
info: loading plugin "back-to-top-button"... OK
info: loading plugin "search-plus"... OK
info: loading plugin "github-buttons"... OK
info: loading plugin "favicon"... OK
info: loading plugin "tbfed-pagefooter"... OK
info: loading plugin "3-ba"... OK
info: loading plugin "prism"... OK
info: loading plugin "prism-themes"... OK
info: loading plugin "sitemap-general"... OK
info: loading plugin "lightbox"... OK
info: loading plugin "adsense"... OK
info: loading plugin "ga"... OK
info: loading plugin "livereload"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 9 pages
info: found 0 asset files
warn: "options" property is deprecated, use config.get(key) instead
warn: "options.generator" property is deprecated, use "output.name" instead

Error: ENOENT: no such file or directory, stat '/mnt/c/Users/a/tom/vagrant-handbook/_book/gitbook/gitbook-plugin-fontsettings/fontsettings.js'
DESKTOP-APB1HCJ%
```

先找到

https://github.com/GitbookIO/gitbook-cli/issues/55

无效果(但是后面的方法2就是这里面提到的，却又有效果了，我也是无语了)

通过 

https://segmentfault.com/q/1010000009569245

修改 book.json，加入以下内容

```json
{
        "plugins": [
                "fontsettings",
                "sharing",
                "lunr",
                "search",
                "highlight",
                "livereload"
        ]
}
```

### 方法2

gitbook serve 报 `no such file or directory`

[gitbook serve/build找不到文件](./post/gitbook-serve-no-such-file-or-directory-stat.md)

## ref

- https://segmentfault.com/q/1010000009569245
- https://github.com/GitbookIO/gitbook-cli/issues/55

