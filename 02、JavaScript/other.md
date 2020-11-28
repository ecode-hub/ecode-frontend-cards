### 1、npx 有什么用？

1、调用项目安装的模块

比如，项目内部安装了测试工具 Mocha：

```bash
npm install -D mocha
```

那么以下两个命令都能执行 macha 命令

```bash
# 项目的根目录下执行
node-modules/.bin/mocha --version

npx mocha --version
```

2、避免全局安装模块

比如，`create-react-app` 这个模块是全局安装，npx 可以运行它，而且不进行全局安装：

```bash
npx create-react-app my-react-app
```

上面代码运行时，npx 将 `create-react-app` 下载到一个临时目录，使用以后再删除。所以，以后再次执行上面的命令，会重新下载 `create-react-app`。

相关链接：
[npx 使用教程](https://www.ruanyifeng.com/blog/2019/02/npx.html)

### package.json 版本依赖中，~ 和 ^ 的区别是什么？

`~` 会匹配最近的小版本依赖包，比如 `~1.2.3` 会匹配所有 1.2.x 版本，但是不包括 1.3.0；
`^` 会匹配最新的大版本依赖包，比如 `^1.2.3` 会匹配所有 1.x.x 的包，包括 1.3.0，但是不包括 2.0.0；
