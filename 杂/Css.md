HTML 定义了网页内容的含义和结构
CSS 网页的表现与展示效果
JAVASCRIPT 网页的功能与行为

- <!doctype html>——文档类型。这是必不可少的开头。 保证文档正常读取.
- html标签 —— 整个页面的所有内容，有时候也称作根元素。它还包含 lang 属性，设置页面的主要语种。
- head HTML 页面中包含但不想向用户显示的内容的容器 设置页面样式的 CSS、字符集声明 
- 

<p> <!-- 段落-->
  At Mozilla, we're a global community of technologists, thinkers, and builders
  working together…
</p>
<h1>主标题</h1> <!-- 共有1-6级别的标题-->
<h2>顶层标题</h2>
<h3>子标题</h3>
<h4>次子标题</h4>

<p>At Mozilla, we're a global community of</p>
<ul><!-- 无序列表 <li> 引导每一项-->
  <li>technologists</li>
  <li>thinkers</li>
  <li>builders</li>
</ul>

<ol> <!-- 有序列表-->
  <li>777</li>
  <li>888</li>
  <li>999</li>
</ol>
<p>working together…</p>

<!-- 超链 不能省略协议部分 https-->
<a href="https://www.mozilla.org/zh-CN/about/manifesto/">
  Mozilla Manifesto
</a>