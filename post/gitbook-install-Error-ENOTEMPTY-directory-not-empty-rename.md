`gitbook install` 时出现 `Error: ENOTEMPTY: directory not empty, rename `

只需要把对应的这个文件，删除后，再重新安装就可以了。

```bash
DESKTOP-APB1HCJ% gitbook install

...
Error: ENOTEMPTY: directory not empty, rename '/mnt/c/Users/a/tom/gitbook-handbook/node_modules/gitbook-plugin-theme-default' -> '/mnt/c/Users/a/tom/gitbook-handbook/node_modules/.gitbook-plugin-theme-default.DELETE'
DESKTOP-APB1HCJ% pwd
/mnt/c/Users/a/tom/gitbook-handbook
DESKTOP-APB1HCJ% rm -rf node_modules/gitbook-plugin-theme-default
DESKTOP-APB1HCJ% gitbook install
```
