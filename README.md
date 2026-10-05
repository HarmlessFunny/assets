# assets

[dsh-background-by-model](https://github.com/HarmlessFunny/dsh-background-by-model) 等项目的图片素材,按消费方项目分目录。

## 两类内容,引用方式不同

| 类别 | 例子 | 裂了会怎样 | 引用方式 |
|---|---|---|---|
| **文档截图** | `dsh-background-by-model/*.webp` | 顶多难看 | jsDelivr **分支**引用,跟着 `main` 自动更新 |
| **运行时素材** | `dsh-background-by-model/holiday/*.webp` | 插件在节日当天静默降级,彩蛋直接消失、无任何报错 | jsDelivr **commit** 引用,不可变 |

放在这里而不是插件仓库里,是为了不把二进制图片的长期历史塞进插件仓库的 `.git`,也不让它们占 npm 包的体积。

### 文档截图 —— `@main`

```
https://cdn.jsdelivr.net/gh/HarmlessFunny/assets@main/<项目目录>/<文件名>
```

GitHub 与 npm 页面都显示得出来,而且比 `raw.githubusercontent.com` 在更多网络下可达。jsDelivr 对分支引用有缓存,图片更新后要等缓存过期才生效 —— 所以**文件名别复用**:换图就换个名字(比如加版本后缀)。

### 运行时素材 —— `@<commit>`

```
https://cdn.jsdelivr.net/gh/HarmlessFunny/assets@<40 位 commit sha>/<项目目录>/<文件名>
```

插件代码里写死的是 **commit sha**,不是 `main`。运行时引用必须是不可变的:哪天整理截图、挪个目录,分支引用会让线上的功能静默失效,而 commit 引用不会。jsDelivr 对 commit 引用永久缓存;代价是换素材要重新提交一次 sha(动代码)。

> **改这里的文件之前,先确认没有人在运行时读它。** 删掉或改名不会报错,只会让对应功能在某一天悄悄不出现。

## dsh-background-by-model

一款让 DeepSeek Harness 的背景随当前模型切换的插件。

```
dsh-background-by-model/
├── *.webp              文档截图
└── holiday/            运行时素材 —— 节日内置壁纸
```

### 截图

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

### 节日素材(运行时)

| 文件 | 生效窗口 | 大小 |
|---|---|---|
| `holiday/mid-autumn.webp` | 农历八月十五(中秋) | 228 KB |
| `holiday/national-day.webp` | 公历 10 月 1–7 日(国庆) | 500 KB |

插件在**节日当天**才去下载对应的那一张,落进 `~/.dsh/.dsh-background-by-model-data/holiday-cache/`,之后永久离线可用。平时零流量。

<p align="center">
  <img src="dsh-background-by-model/holiday/mid-autumn.webp" alt="Mid-Autumn wallpaper" width="420">
  <img src="dsh-background-by-model/holiday/national-day.webp" alt="National Day wallpaper" width="420">
</p>

<p align="center">
  <sub>截图里的示例壁纸素材来自 bilibili 的 <a href="https://space.bilibili.com/4168597">ZipZipPipe</a></sub>
</p>
