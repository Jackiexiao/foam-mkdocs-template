# Foam-mkdocs-template
* 通过github/gitee page生成网页，分享你的foam/obsidian/markdown笔记！
* 省事一点可以用obsidian publish，8美刀/月

[English Version](https://github.com/Jackiexiao/foam-mkdocs-template/blob/master/README.md)

弄好之后你的网站长这个样子：
![foam-mkdocs-template-png](demo-mkdocs.png)


## 样例

* [github page](https://jackiexiao.github.io/foam-mkdocs-template/)
* 国内访问[gitee page](https://jackiegeek.gitee.io/foam-mkdocs-template/)

## 使用方法：部署到github page生成博客网站

1. 复制Fork或者下载这个仓库
2. 复制 `.github  mkdocs.yml requirements.txt` 到你的仓库下面，新建一个 docs 文件夹
3. 将你的文档添加到`docs`下面（原来的文件可以全部删掉），在`docs`吓添加一个`index.md`作为网站主页（必须有）
4. 进入`mkdocs.yml`修改`site_name`为你的网站名称，这个文件包含了你网站的配置，具体配置教程见（可以先使用默认配置，够用了，有时间再自己折腾）：
* [mkdocs-material](https://squidfunk.github.io/mkdocs-material/)
* [mkdocs](https://www.mkdocs.org/user-guide/configuration/)
5. push提交修改到github
6. 到你的github仓库-setting中设置github page，选择分支-gh-pages，等一小会，就会有网址啦，比如我的是`jackiexiao.github.io/blog/`
7. 大功告成！

之所以git push就可以自动部署网页，生成博客，是因为github action在起作用！感兴趣可以自己搜索一下。

## 同步发布到Gitee page加速国内访问

步骤很简单，比如这个[博客](https://jackiegeek.gitee.io/blog/)，在Gitee的首页下新建仓库，在页面下方选择`导入已有仓库`, 填写你的github仓库地址，然后点击`服务`->`Gitee Page`->`部署分支`->选择`gh-pages`，点击`更新`就完成啦！几秒后刷新你就可以看到自己gitee apge的链接了。不过要注意的是，每次更新Gitee page，你需要3个步骤

1. 更新你的github仓库
2. 在Gitee中手动点击同步github
3. 按前面的步骤，再次部署Gitee Page 

## 本地部署

经常性的，我们需要本地部署文档，来进行频繁的修改和预览。最简单的方法是进入你的文件夹（仓库本地地址，也就是`docs`文件夹的上一级），你的python需要3.6以上
```
pip install -U -r requirements.txt
mkdocs serve 
```
然后访问`http://127.0.0.1:8000/`就可以了

## 其他

这个模板使用的库
* [mkdocs](https://www.mkdocs.org/user-guide/configuration/)
* [mkdocs-material](https://squidfunk.github.io/mkdocs-material/)
* [mkdocs-roamlinks-plugin](https://github.com/Jackiexiao/mkdocs-roamlinks-plugin)

## 支持的语法
这个模板会将markdown中的链接解析成网页支持的格式，支持的格式如下

| 原始                  | 转换后                             |
| ----------------------- | ----------------------------------- |
| `[Git Flow](git_flow.md)` | `[Git Flow](../software/git_flow.md)` |
| `[[Git Flow]]`            | `[Git Flow](../software/git_flow.md)` |
| `![[image.png]]`           | `![image.png](../image/imag.png)`      |
| `[[#Heading identifiers]]` | `[Heading identifiers in HTML](#heading-identifiers-in-html)`
| ` [[Git Flow#Heading]]` | `[Git Flow](../software/git_flow.md#heading)` |
