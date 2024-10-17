---
title: Hexo主题cactus的改修
description: "This post is for testing the draft post functionality"
publishDate: "2024/10/14"
tags: ["hexo-theme"]
---

    在使用Hexo中遇到了主题的问题，也遇到了不熟悉Hexo命令等问题，都记录在此。

主题选择了一款轻量型主题[cactus](https://github.com/probberechts/hexo-theme-cactus)，比较简单明确。

不过该主题不支持中文，需要自己将代码clone下来进行更改。
选择此主题时，按照github的教程是将其作为git的submodule来使用，所以无法更改。

若要进行自定义，需删除submodule，再将clone下来的项目放进`themes`中
```shell
git rm --cached themes/cactus 
git rm .gitmodules
rm -rf themes/cactus/.git
```

* 修改nav字号
```stylus
// themes/cactus/source/css/_partial/header.styl
#nav
    color: $color-accent-1
    letter-spacing: .01em
    font-weight: 200
    font-style: normal
    font-size: 1.2rem
```

* 追加字体 
在 `cactus/source/lib` 中创建 `fonts` 文件夹，并加入[JetBrains Mono](https://www.jetbrains.com/lp/mono/)字体
如果需要支持中文请将字体替换为中文字体
`themes/cactus/source/css/_fonts.styl`
```stylus
@font-face
  font-style: normal
  font-weight: normal
  font-family: "JetBrains Mono"
  src: url("../lib/fonts/JetBrainsMono-Regular.ttf") format("truetype")
```

* 修改字体 
`themes/cactus/source/css/_variables.styl`
```stylus
// 
// Fonts
$font-family-body = "JetBrains Mono", monospace
$font-family-mono = "JetBrains Mono", monospace
$font-size = 1rem
...
```