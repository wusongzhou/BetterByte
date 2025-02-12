---
# 文章发布日期和时间 (ISO 8601 格式，+08:00 表示北京时间)
date: '2025-02-05T10:58:25+08:00'

# 草稿模式：true 时 Hugo 默认不渲染，可通过 hugo server -D 预览
draft: true

# 文章标题（显示在页面和浏览器标签）
title: 'Test2'

# 文章标签（用于分类）
tags: ["first"]

# 作者信息（单作者写法）
author: "Me"
# 多作者写法（取消注释即可使用）：
# author: ["Me", "You"]

# 目录控制：是否显示目录
showToc: true

# 目录默认状态：true=展开 / false=折叠
TocOpen: false

# 隐藏元数据（日期、作者、标签等）
hidemeta: false

# 是否开启评论区（需配置评论系统如 Utterances）
comments: false

# 文章摘要（SEO 和摘要显示用）
description: "Desc Text."

# 规范链接（SEO 防重复，填写最终正式 URL）
canonicalURL: "https://canonical.url/to/page"

# 禁用代码高亮（Highlight.js）
disableHLJS: true

# 禁用社交分享按钮
disableShare: false

# 隐藏文章摘要
hideSummary: false

# 是否在站内搜索中隐藏
searchHidden: true

# 显示阅读时间估算
ShowReadingTime: true

# 显示面包屑导航（如：主页 > 分类）
ShowBreadCrumbs: true

# 显示上一篇/下一篇文章链接
ShowPostNavLinks: true

# 显示字数统计
ShowWordCount: true

# 在分类/标签页显示 RSS 按钮
ShowRssButtonInSectionTermList: true

# 使用 Hugo 内置的目录生成逻辑
UseHugoToc: true

# 封面图配置
cover:
    image: "<image path/url>"  # 图片路径或 URL
    alt: "<alt text>"          # 图片无法加载时的替代文本
    caption: "<text>"          # 图片下方说明文字
    relative: false           # true=路径相对于文章目录（Page Bundles 专用）
    hidden: true               # true=仅在当前页隐藏封面图

# 编辑链接配置（指向 GitHub 等）
editPost:
    URL: "https://github.com/<path_to_repo>/content"  # 文章源文件链接
    Text: "Suggest Changes"   # 链接显示的文字
    appendFilePath: true      # 是否在链接后追加文件路径
---