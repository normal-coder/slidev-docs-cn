---
title: Vue 全局上下文
---

# Vue 全局上下文 {#vue-global-context}

Slidev 注入了一个 [全局的 Vue 上下文](https://v3.vuejs.org/api/application-config.html#globalproperties) `$slidev`，它用于高级的条件判断或导航控制。

## 用法 {#usage}

你可以在你的 markdown 文件以及 Vue 模板的任何位置使用 ["Mustache" 语法](https://v3.vuejs.org/guide/template-syntax.html#interpolations) 访问它。

```md
<!-- slides.md -->

# Page 1

Current page is: {{ $slidev.nav.currentPage }}
```

```html
<!-- Foo.vue -->

<template>
  <div>Title: {{ $slidev.configs.title }}</div>
  <button @click="$slidev.nav.next">Next Page</button>
</template>
```

## 属性 {#properties}

<<<<<<< HEAD
### `$slidev.nav` {#slidev-nav}
=======
### `$clicks`

`$clicks` hold a number of clicks on the current slide. Can be used conditionally to show different content on clicks.

```html
<div v-if="$clicks > 3">Content</div>
```

### `$page`

`$page` holds the number of the current page, 1-indexed.

```md
Page: {{ $page }}

Is current page active: {{ $page === $slidev.nav.currentPage }}
```

### `$renderContext`

`$renderContext` holds the current render context, can be `slide`, `overview`, `presenter` or `previewNext`

```md
<div v-if="$renderContext === 'slide'">
  This content will only be rendered in slides view
</div>
```

### `$slidev.nav`
>>>>>>> 285da456fee4e267e3d19c2fb5b19ebef4d1f909

一个响应式对象，它拥有幻灯片导航的属性以及控制权。例如：

```js
$slidev.nav.next() // 执行下一步

$slidev.nav.nextSlide() // 跳转下一张幻灯片 (忽略 v-clicks)

$slidev.nav.go(10) // 去到幻灯片的第 10 页
```

```js
$slidev.nav.currentPage // 获取当前幻灯片的页数

<<<<<<< HEAD
$slidev.nav.currentLayout // 当前的布局 id

$slidev.nav.clicks // 目前的点击次数
=======
$slidev.nav.currentLayout // current layout id
>>>>>>> 285da456fee4e267e3d19c2fb5b19ebef4d1f909
```

欲了解更多可用属性，请参阅 [nav.ts](https://github.com/slidevjs/slidev/blob/main/packages/client/logic/nav.ts) 的 exports。

<<<<<<< HEAD
### `$slidev.configs` {#slidev-configs}
=======
> Note: `$slidev.nav.clicks` is a global state while `$clicks` is local to each slide. It's recommended to **use `$clicks` over `$slidev.nav.clicks`** to avoid clicks changed been triggered on page transitions.

### `$slidev.configs`
>>>>>>> 285da456fee4e267e3d19c2fb5b19ebef4d1f909

一个响应式对象，它存储着你 `slides.md` 中解析后的 [第一个 frontmatter 中的配置](/custom/#frontmatter-configures)。例如：

```yaml
---
title: My First Slidev!
---
```

```
{{ $slidev.configs.title }} // 'My First Slidev!'
```

### `$slidev.themeConfigs` {#slidev-themeconfigs}

一个响应式对象，它存储着解析后的主题配置。

```yaml
---
title: My First Slidev!
themeConfig:
  primary: #213435
---
```

```
{{ $slidev.themeConfigs.primary }} // '#213435'
```

### `$nav`

> Available since v0.43.0

A shorthand of `$slidev.nav`.
