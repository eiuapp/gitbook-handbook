
gitbook build/serve 失败，Error: ENOENT: no such file or directory, stat ...

https://www.cnblogs.com/wenhui92/p/9482629.html

比如

gitbook serve 命令找不到 buttons.js 

出现了下面的错误。

```bash
DESKTOP-APB1HCJ% gitbook serve
Live reload server started on port: 35729
Press CTRL+C to quit ...

info: 25 plugins are installed
info: 23 explicitly listed
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
info: loading plugin "disqus"... OK
info: loading plugin "livereload"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 3 pages
info: found 0 asset files
warn: "options" property is deprecated, use config.get(key) instead
warn: "options.generator" property is deprecated, use "output.name" instead

Error: ENOENT: no such file or directory, stat '/mnt/c/Users/a/tom/wsl-handbook/_book/gitbook/gitbook-plugin-sharing/buttons.js'
```





vi ~/.gitbook/versions/3.2.3/lib/output/website/copyPluginAssets.js


文件中的 112 行

```
return fs.copyDir(
    assetsFolder,
    assetOutputFolder,
    {
        deleteFirst: false,
        overwrite: true,
        confirm: true
    }
);
```

中的  `confirm: true` 修改成 `confirm: false`

也就是修改成

```
return fs.copyDir(
    assetsFolder,
    assetOutputFolder,
    {
        deleteFirst: false,
        overwrite: true,
        confirm: false
    }
);
```

## ref
- https://www.cnblogs.com/wenhui92/p/9482629.html
