# 绘图与批注 {#drawing-annotations}

> 自 v0.23 起可用

我们基于 [drauu](https://github.com/antfu/drauu) 实现了绘图和批注的功能，可用进一步增强你的演示效果。

你可以通过点击工具栏上的 <carbon-pen class="inline-icon-btn"/> 图标来启用。它也可以在 [演讲者模式](/guide/presenter-mode) 中使用。你创建的绘图和批注都会实时**自动同步**起来。

<TheTweet id="1424027510342250499" />

## 与触控笔一同使用 {#use-with-stylus-pen}

当在平板电脑上使用触控笔时（例如，带有 Apple Pencil 的 iPad），Slidev 可以智能地检测输入类型。你可以直接用笔在幻灯片上绘图，而无需打开绘图模式，同时你的手指或鼠标可以控制导航。

## 对绘图进行持久化 {#persist-drawings}

frontmatter 中的配置可以把你得到绘图作为 SVG 保存在 `.slidev/drawings` 目录下，并把它们放入你导出的 pdf 或者部署的网站中。

```md
---
drawings:
  persist: true
---
```

## 禁用绘图 {#disable-drawings}

完全禁用：

```md
---
drawings:
  enabled: false
---
```

仅在开发环境可用：

```md
---
drawings:
  enabled: dev
---
```

仅在演讲者模式可用：

```md
---
drawings:
  presenterOnly: true
---
```

## 绘图同步 {#drawing-syncing}

默认情况下，Slidev 会在所有实例中同步你的绘图。如果你在和他人共享幻灯片，你可能会需要通过以下方式禁用同步：

```md
---
drawings:
  syncAll: false
---
```

<<<<<<< HEAD
通过这个配置，只有来自演讲者实例的绘图会和其他实例同步。


=======
With this config, only the drawing from the presenter instance will be able to sync with others.
>>>>>>> ee683ae81a2021c44b278d720a418ee0c6ddb537
