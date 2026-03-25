---
title: "这是书名"
author: "这是作者名"
subtitle: "副标题 / 主题演示"
---

<!-- 手动封面页（浅色文艺版），展示 .title-page 样式 -->
<div class="title-page">
  <div class="subtitle">主题样式演示</div>
  <h1 class="title">这是书名</h1>
  <div class="author">这是作者名</div>
  <div class="botanical-decoration"></div>
</div>

<div class="blank-page"></div>

<!-- 版权页 -->
<div class="copyright-page">
  <div class="publisher">演示出版社</div>
  <div class="info">
    © 2025 演示版权信息<br>
    本文件用于展示 CSS 主题样式，无实际内容。
  </div>
  <div class="isbn">（演示）ISBN 000-0-000-00000-0</div>
</div>

<div class="blank-page"></div>

<!-- 题词页 / 献词页 -->
<div class="dedication">
  <p>
    “演示引用文字，展示 .dedication 样式。”<br>
    ——《演示文献》
  </p>
  <p>
    这是第二行题词，展示段落的间距与居中对齐效果。
  </p>
</div>

<!-- 目录将由 Pandoc 的 --toc 参数自动生成，无需手动添加 -->
<!-- 如果使用 --toc，会在题词页后自动插入目录，样式由 CSS 中的 #TOC 控制 -->

# 第一章 · 演示章节

这是正文段落。样式展示了首行缩进、行距、字体等。中文排版使用宋体，英文使用衬线体。段落之间有间距。

这是第二个段落，展示连续段落的样式。

## 1.1 子章节

### 1.1.1 三级标题

正文继续，这里展示标题的层级与居中样式。标题下方有装饰横线。

> 这是一个引用块。展示引用样式：左侧竖线，缩进，较小字号，灰色文字。
> 可以多行引用，展示引用段落效果。

*无序列表：*
- 列表项一
- 列表项二
  - 嵌套列表
  - 另一项

1. 有序列表第一项
2. 有序列表第二项
   - 混合嵌套
3. 有序列表第三项

**粗体文本**，*斜体文本*（这里斜体使用楷体样式），`行内代码`，[超链接示例](https://example.com)。

---

### 表格演示

| 列标题 1 | 列标题 2 | 列标题 3 |
| :------- | :------- | :------- |
| 单元格 A | 单元格 B | 单元格 C |
| 单元格 D | 单元格 E | 单元格 F |

表格边框、居中对齐、字体大小均已定义。



### 脚注演示

这里有脚注的示例。¹

¹ 这是脚注内容，展示脚注样式。脚注文字较小，带灰色边框。

------

<div class="divider"></div>

装饰分隔符展示。

# 第二章 · 另一个演示章节

展示更多元素，如内嵌图片占位（无实际图片）等。

![图片占位符](data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect width='100' height='100' fill='%23eee'/%3E%3Ctext x='50%25' y='50%25' text-anchor='middle' dy='.3em' fill='%23999' font-size='12'%3E演示图%3C/text%3E%3C/svg%3E)

*图片样式居中，有最大宽度限制，可配图注。*

------

### 竖排文字工具类

<div class="vertical-text"> 竖 排 文 字 演 示 </div>

------

### 侧边装饰

<div class="margin-note"> 侧 边 装 饰 </div>

------

# 第三章 · 特殊区块演示

## 尾声区块

<div class="epilogue"> <div class="epilogue-title">尾声</div> <p>这是尾声区块，用于结尾陈述或总结。</p> </div>

## 致谢区块

<div class="acknowledgments"> <div class="ack-title">致谢</div> <p>感谢主题设计者，感谢演示。</p> </div><!-- 末页封底（黑色） --><div class="end-page"> <div class="ending-text">样式演示完毕</div> <div class="copyright">感谢使用本主题</div> </div>

