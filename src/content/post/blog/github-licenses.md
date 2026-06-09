---
title: "GitHub 开源许可证（Licenses）完全指南"
description: "详解 GitHub 上常见的开源许可证，帮助你为项目选择合适的 License"
publishDate: "2026/6/9"
tags: ["github", "open-source", "license"]
category: '博客'
---

在 GitHub 上创建一个新的开源项目时，你可能会注意到添加 License 的选项。许可证（License）是开源项目中非常重要但又常被忽略的一部分。本文将带你了解 GitHub 上常见的开源许可证及其区别。

## 什么是开源许可证？

开源许可证是一种法律许可协议，它规定了其他人可以如何使用、修改和分发你的代码。没有许可证的代码默认受版权保护，其他人无法合法使用。

简单来说：

- **没有 License** → 别人不能使用你的代码（默认保留所有权利）
- **有 License** → 你明确告诉别人可以在什么条件下使用你的代码

## GitHub 上常见的开源许可证

### 1. MIT License

MIT 许可证是最宽松、最受欢迎的开源许可证之一。

**核心特点：**

- 几乎没有任何限制
- 允许商业使用、修改、分发、私有使用
- 只需保留原始版权声明和许可证
- 不提供任何担保

**适用场景：** 希望代码被广泛使用，不在乎别人如何使用。

**知名项目：** jQuery、React、Node.js、Vue.js

```
MIT License

Copyright (c) [year] [fullname]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...
```

### 2. Apache License 2.0

Apache 2.0 是一个较为宽松但提供了专利保护的许可证。

**核心特点：**

- 允许商业使用、修改、分分发
- 要求保留版权声明和变更说明
- **提供专利授权保护**（MIT 没有）
- 要求标注修改过的文件

**适用场景：** 企业级项目，需要专利保护。

**知名项目：** Android、Kubernetes、TensorFlow

### 3. GNU General Public License (GPL)

GPL 是一种 **"copyleft"** 许可证，要求衍生作品也必须开源。

**主要版本：**

| 版本 | 特点 |
|------|------|
| GPL v2 | 经典版本，Linux 内核使用 |
| GPL v3 | 增加了反专利条款和反 Tivoization |

**核心特点：**

- 允许商业使用和修改
- **衍生作品必须使用相同的 GPL 许可证**
- 修改后的代码必须开源
- 传染性强：使用了 GPL 代码的项目也需要开源

**适用场景：** 希望确保代码永远开源，防止被闭源使用。

**知名项目：** Linux Kernel (v2)、WordPress、GCC

### 4. GNU Lesser General Public License (LGPL)

LGPL 是 GPL 的宽松版本，主要用于库/框架。

**核心特点：**

- 库本身遵循 copyleft（修改库需要开源）
- **使用库的应用不需要开源**
- 适合做开源库

**适用场景：** 开发库/框架，希望被广泛引用，包括闭源项目。

**知名项目：** Qt、FFmpeg

### 5. BSD License

BSD 许可证家族有几个变体，都很宽松。

**主要变体：**

- **BSD 2-Clause**（Simplified BSD）：类似 MIT，非常简洁
- **BSD 3-Clause**：在 2-Clause 基础上增加"不得用作者名义推广"条款

**核心特点：**

- 与 MIT 类似，非常宽松
- 允许闭源使用
- BSD 3-Clause 额外禁止使用原作者名义做推广

**知名项目：** FreeBSD、Nginx (部分)

### 6. Mozilla Public License 2.0 (MPL)

MPL 是一种介于 MIT 和 GPL 之间的"弱 copyleft"许可证。

**核心特点：**

- **文件级别的 copyleft**：修改的 MPL 文件需要开源
- 但可以与闭源代码组合使用
- 有专利授权条款

**适用场景：** 希望保护代码本身的开源性，但允许与闭源集成。

**知名项目：** Firefox、Thunderbird

### 7. The Unlicense

这是一种将代码放入**公共领域（Public Domain）**的方式。

**核心特点：**

- 放弃所有版权
- 任何人可以做任何事
- 无需保留任何声明

**适用场景：** 真正不想对代码施加任何限制。

## 许可证对比速查表

| 许可证 | 商业使用 | 修改 | 分发 | 专利授权 | 衍生作品开源 | 传染性 |
|--------|---------|------|------|---------|------------|--------|
| MIT | ✅ | ✅ | ✅ | ❌ | ❌ | 无 |
| Apache 2.0 | ✅ | ✅ | ✅ | ✅ | ❌ | 无 |
| GPL v3 | ✅ | ✅ | ✅ | ✅ | ✅ | 强 |
| LGPL | ✅ | ✅ | ✅ | ✅ | 部分 | 弱 |
| BSD 3-Clause | ✅ | ✅ | ✅ | ❌ | ❌ | 无 |
| MPL 2.0 | ✅ | ✅ | ✅ | ✅ | 部分 | 文件级 |
| Unlicense | ✅ | ✅ | ✅ | ❌ | ❌ | 无 |

## 如何选择合适的许可证？

选择许可证时，可以考虑以下几个问题：

1. **你是否在乎别人闭源使用你的代码？**
   - 不在乎 → MIT / BSD / Apache
   - 在乎 → GPL / MPL

2. **你的项目是否涉及专利？**
   - 是 → Apache 2.0 / GPL v3
   - 否 → MIT / BSD 都可以

3. **你开发的是库还是应用？**
   - 库 → MIT / Apache / LGPL（方便被引用）
   - 应用 → GPL（保护开源性）

4. **你是否希望代码进入公共领域？**
   - 是 → Unlicense
   - 否 → 选择上述任一许可证

## 如何在 GitHub 上添加 License

### 方法一：创建仓库时添加

在 GitHub 上创建新仓库时，页面下方有 "Add a license" 下拉选项，选择你需要的许可证即可。

### 方法二：手动添加

在项目根目录创建一个 `LICENSE` 文件，将许可证全文粘贴进去：

```bash
# 在项目根目录创建 LICENSE 文件
touch LICENSE

# 使用 GitHub CLI 添加
gh repo view --json licenseInfo
```

### 方法三：使用 choosealicense.com

GitHub 推荐使用 [choosealicense.com](https://choosealicense.com) 网站来帮助选择许可证，该网站提供了交互式的选择工具。

## 常见误区

### ❌ "不加 License = 开源"

没有 License 的代码默认保留所有权利，其他人不能合法使用。

### ❌ "加了 License 就不能收费"

开源许可证不限制你对代码收费，它只规定了使用条件。你可以同时对代码收费并开源（虽然不太常见）。

### ❌ "GPL 代码不能商用"

GPL 允许商用，但要求衍生作品也必须开源。这意味着你很难将 GPL 代码用于闭源商业产品。

### ❌ "MIT 和 BSD 一样"

虽然都很宽松，但 BSD 3-Clause 额外有"不得用作者名义推广"的限制，MIT 没有。

## 总结

| 你的需求 | 推荐许可证 |
|---------|-----------|
| 简单宽松，随便用 | MIT |
| 需要专利保护 | Apache 2.0 |
| 必须保持开源 | GPL |
| 做开源库，允许闭源引用 | LGPL / MIT |
| 折中方案 | MPL 2.0 |
| 完全放弃权利 | Unlicense |

选择合适的许可证是开源项目的重要一步。希望这篇文章能帮助你为项目做出正确的选择！
