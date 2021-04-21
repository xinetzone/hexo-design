## 从零开始构建 Hexo 博客

一步步从零开始构建 Hexo 博客。

### Hexo 初始化

1. 创建 Hexo 基底：

```shell
$ hexo init book
$ cd book
```

2. 创建自己专属的主题：
    - 为你专属的主题命名，比如我的是 `live`，接着创建空文件夹 `themes/live`，并且
    - 重命名 `themes/_config.landscape.yml` 为 `themes/_config.live.yml`
    - 修改网站配置文件 `_config.yml` 的 `theme` 为 `live`
    - 移除默认是主题：

```shell
npm uninstall hexo-theme-landscape
```

3. 填写网站的配置文件 `_config.yml` 的相关信息
4. 为了保证网页的网址是唯一的，需要在网站配置文件 `_config.yml` 中添加并配置：

```yml
permalink: :layout/:lang/:hash/ # :year/:month/:day/:title/
permalink_defaults:
  lang: zh-CN # 设定默认 en，en-US
```

5. 为了图片等资源文件更好的支持 GFM，需要在网站配置文件 `_config.yml` 中添加并配置：

```yml
post_asset_folder: true # 启动 Asset 文件夹（资源（Asset）代表 source 文件夹中除了文章以外的所有文件，例如图片、CSS、JS 文件等。）
marked: # 保证资源的链接正确
  prependRoot: true
  postAsset: true
  gfm: true
```

6. 为了支持 RSS，需要在网站配置文件 `_config.yml` 中添加并配置：

```yml
# 添加 RSS 订阅支持
## https://github.com/hexojs/hexo-generator-feed
## npm install hexo-generator-feed
feed:
  # Generate both atom and rss2 feeds
  type:
    - rss2
  path:
    - rss2.xml
```

### 创建网站主页

