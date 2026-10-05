# assets

[dsh-background-by-model](https://github.com/HarmlessFunny/dsh-background-by-model) 等项目的文档截图素材,按消费方项目分目录。

放在这里而不是插件仓库里,是为了不把二进制图片的长期历史塞进插件仓库的 `.git`。各项目的 README 用 jsDelivr 的绝对地址引用,这样 GitHub 和 npm 页面都能正常显示,而且比 `raw.githubusercontent.com` 在更多网络下可达:

```
https://cdn.jsdelivr.net/gh/HarmlessFunny/assets@main/<项目目录>/<文件名>
```

注意 jsDelivr 对分支引用(`@main`)有缓存,图片更新后可能要等缓存过期才生效 —— 所以**文件名别复用**:换图就换个名字(比如加版本后缀),比等缓存靠谱。

## dsh-background-by-model

一款让 DeepSeek Harness 的背景随当前模型切换的插件。

同一个界面、同一份配置 —— 只有当前模型不同:

<p align="center">
  <img src="dsh-background-by-model/wallpaper-deepseek.webp" alt="Appearance under DeepSeek" width="880">
  <br/>
  <em>DeepSeek V4.1 Flash · 命中 match 含 <code>deepseek</code> 的规则:浅色壁纸 + 配套主题色</em>
</p>

<p align="center">
  <img src="dsh-background-by-model/wallpaper-kimi.webp" alt="Appearance under Kimi" width="880">
  <br/>
  <em>Kimi K2.7 Code · 命中含 <code>kimi</code> 的规则:深色壁纸、深色主题,整个界面跟着换肤</em>
</p>

<p align="center">
  <img src="dsh-background-by-model/rule-editor.webp" alt="One rule's editor" width="660">
  <br/>
  <em>Model Background 页上的一条规则</em>
</p>

<p align="center">
  <sub>示例壁纸素材来自 bilibili 的 <a href="https://space.bilibili.com/4168597">ZipZipPipe</a></sub>
</p>
