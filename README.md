# lerna_test

lerna 试验

## lerna

当一个大的项目库代码量剧增之后，管理起来就是一件比较麻烦的事情，为了方便代码的共享，就需要将代码库拆分成独立的包。这个时候 lerna 就是一个不错的选择。

[lerna](https://github.com/lerna/lerna)是 GitHub 上面开源的一款 js 代码库管理软件， 用来对一系列相互耦合比较大、又相互独立的 js git 库进行管理。解决各个库之间修改混乱、难以跟踪的问题。lerna 可以优化这种情形下的工作流。

对于一些功能比较全的库，我们往往会把各个小功能拆分成独立的 npm 库，他们直接有比较强的依赖关系。比如：Babel、React 等开源代码都是按照这种方式进行处理的。

lerna 管理的库文件结构类似如下这样

```doc
my-lerna-repo/
  package.json
  packages/
    package-1/
      package.json
    package-2/
      package.json
```

### lerna 主要做了什么

通过 lerna 的命令 lerna bootstrap 将会把代码库进行 link。通过 lerna publish 发布最新改动的库

### 初始化

```shell
npm i -g lerna
mkdir my-lerna-repo
cd my-lerna-repo
lerna init
```

生成文件路径如下：

```doc
lerna-repo/
  packages/
  package.json
  lerna.json
```

默认情况下，packages/下即保存多包地址。

### 安装依赖

```shell
lerna bootstrap
```

默认是 npm i,因为我们指定过 yarn，so,run yarn install,会把所有包的依赖安装到根 node_modules.

在 根目录的 `lerna.json` 内 配置 `"npmClient": "yarn"`
