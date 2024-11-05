---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: CSS Basic
info: |
  ## Share basic knowledge of CSS
  including the history and the writing methods, and how to build up the world in mind
  
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# take snapshot for each slide in the overview
overviewSnapshots: true
---

# CSS Share: Am I writing it right?

For None-Web Developers.

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
# 需要一个热场的内容, 讲个冷笑话看看:
+ 为什么CSS不喜欢和HTML一起玩?
+ 因为HTML总是在说: 我是谁, 我在哪里, 我要去哪里, 我要干什么.

# 然后提问: 怎么让CSS和HTML一起玩的开心呢?
-->

---
transition: fade-out
---

# What is CSS?

- <span class="text-bold" v-mark.circle.red="1">C</span>ascading <span class="text-bold" v-mark.circle.red="2">S</span>tyle <span class="text-bold" v-mark.circle.red="3">S</span>heets
- A style sheet language used for describing the presentation of a document written in HTML or XML
- CSS describes how elements should be rendered on screen, on paper, in speech, or on other media. The Origin Data will been transformed into the UI by CSS.
- CSS was first proposed by Håkon Wium Lie on October 10, 1994

<br>
<br>

[MDN](https://developer.mozilla.org/en-US/docs/Web/CSS)

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
+ 其实不用太过于关心CSS的定义, 写CSS就像写DataFrame, 将HTML变成UI 
+ 一开始HTML是没有CSS这个概念的, 本来是给CERN他们的科学家用的, 但是用着好像不太好看, 做浏览器的人就开始设计自己的Style Language, 有篇文章是讲述Style Language的历史的, 但是网址被Cloudflare收购了, 看不到了.
-->


---
transition: slide-up
level: 2
---

# GOOD CSS, BAD CSS

- With great HTML structure comes great CSS
- HTML construct from top to bottom, left to right

<!--
- 我也不知道什么是好的CSS...
- 但是想要有好的CSS, 需要有好的HTML结构与内容
-->

---
layout: two-cols
layoutClass: gap-16
---

# Table of contents

- Old Days: Table(Dream Weaver), UPPER CASE TAG
- Modern: flex(grid)
- Enginering: Tailwind, CSS In JS, CSS Modules

::right::

<Toc minDepth="1" maxDepth="2"></Toc>

<!--
- 我们会从CSS的历史开始, 来一步步看怎么来写一个网页
-->

---
layout: image-right
image: https://www.webdesignmuseum.org/uploaded/timeline/steam/steam-2002.png
---

# Old Ages: Steam in 2002

```html {all|8|16|all} twoslash
<table cool="" width="800" height="159" showgridx="" showgridy="" gridx="16" gridy="16" border="0" cellpadding="0" cellspacing="0" bgcolor="black">
				<tbody><tr height="16">
					<td width="799" height="16" colspan="5"><spacer type="block" width="799" height="16"></spacer></td>
					<td width="1" height="16"><spacer type="block" width="1" height="16"></spacer></td>
				</tr>
				<tr height="35">
					<td width="16" height="35"><spacer type="block" width="16" height="35"></spacer></td>
					<td width="770" height="35" colspan="3" valign="top" align="left" xpos="16"><img src="/web/20020321021820im_/http://steampowered.com/Images/Type_steampowered.gif" width="770" height="29" border="0"></td>
					<td width="13" height="142" rowspan="3"><spacer type="block" width="13" height="142"></spacer></td>
					<td width="1" height="35"><spacer type="block" width="1" height="35"></spacer></td>
				</tr>
				<tr height="14">
					<td width="310" height="14" colspan="3"><spacer type="block" width="310" height="14"></spacer></td>
					<td width="476" height="107" rowspan="2" align="left" xpos="310" content="" valign="top" csheight="92">
						<div align="right">
							<font size="2" face="Arial,Helvetica,Geneva,Swiss,SunSans-Regular" color="white"><b><a href="https://web.archive.org/web/20020321021820/http://steampowered.com/html/betasignup.html" target="_self">Try Steam Now!</a></b></font><font color="white"> </font><font size="2" color="white"><b><font face="Arial,Helvetica,Geneva,Swiss,SunSans-Regular">| </font></b></font><font face="Arial,Helvetica,Geneva,Swiss,SunSans-Regular" size="2" color="white"><a href="https://web.archive.org/web/20020321021820/http://steampowered.com/support/index.html" target="_self">Steam Support Site</a> |
                            <a href="https://web.archive.org/web/20020321021820/http://www.valvesoftware.com/" target="_new">Valve Home</a></font></div>
			  ...
```

<!--
[click] 左上角的图片

[click] 右上角的链接

[click] 被浏览器拖累的布局
-->
---
layout: two-cols
---

# Why

+ display: inline, block
+ float: left, right

+ put them in line

```html
<div class="bg-red-600 w-64 h-64"></div>
<div class="bg-green-600 w-64 h-64"></div>
```

::right::

<div class="p-8" v-click>

<div class="bg-red-600 w-64 h-64"></div>
<div class="bg-green-600 w-64 h-64"></div>

</div>

<!--
+ 首先是块级元素和行内元素这些概念
+ div是块级元素, span是行内元素
+ 块级元素会占据一整行, 行内元素会在一行内显示
+ 那么怎么让块级元素在一行内显示呢? float, position
+ 即使float在1997年已经在CSS1标准, 但是直到2000年才被IE支持, 2005年才被Firefox支持
+ 那怎么办, 那就用table来模拟
+ 实操: 如何让两个div在一行内显示

-->

---
layout: two-cols
---
# Modern, CSS3

- Flex, Grid
	- Control Self -> Parent Control Children
- Animation, transform, translation
	- Empower Web UI

::right::

<v-click>

![Main Axis](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox/basics1.svg)

</v-click>

<v-click>


![Cross Axis](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox/basics3.svg)

</v-click>


<v-click>
<div
  v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0, y: 0 }"
  :click-1="{ x: 0, y: 30 }"
  :click-2="{ y: 60 }"
  :click-2-4="{ x: 40 }"
  :leave="{ y: 0, x: 80 }"
>
  Animation
</div>
</v-click>

<!--
- 我们跳过了CSS2.1的内容, 直接来看CSS3相关的特性, 随着UI布局的变化要求, 从远古的, 每个元素自己控制自己的位置, 演变成了现代的, 通过父元素属性控制子元素位置.
- 容器只关心布局, 元素依靠内容决定大小
- [click] Flex的基本概念就是主轴交叉轴, 内容物大小自适应
- [click] 默认是横向主轴
- [click] 纵向交叉轴
- [click] justify, align分别控制主轴和交叉轴上的布局
- [click] Translation
-->
---
layout: image-left
image: https://www.webdesignmuseum.org/uploaded/timeline/steam/steam-2018.jpg
---
# Compose Own Website(FlexBox)

+ Just focus on One item in the <span v-mark.circle.red="1"> New And Trending </span>

<div v-click="1" class="absolute outline outline-red w-70 h-7.5 top-83.5 left-30"></div> 

<div v-click="2">

- Determine which element is controled by content and which are not: Fixed, Hug, Fill, Auto

- Fixed: Image, Discount
- Hug: Price, Discount, ...
- Fill: Info ...

</div>

<div v-click="3">
</div>

<!--
+ 在实现一个网页时, 我会从以下几点开始设计布局
[click]: 只关注 New and Trending
[click]: 那些宽高是不会变化的, 那些宽高是根据内容改编的
[click]: 那些是容器, 那些是元素
-->
---
layout: two-cols
---
# Engineer Efforts

<div v-click="1">

+ TailwindCSS

```html
<div
  v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0, y: 0 }"
  :leave="{ y: 0, x: 80 }"
>
	<div class="relative w-72 h-48 outline">
	</div>
</div>
```

</div>

<div v-click="2">

+ CSS in JS

```ts
const Root = styled`
display: flex;
``
```

</div>

::right::

<div v-click="1">
<div
  v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 30, y: 0 }"
  :leave="{ y: 0, x: 80 }"
>
	<div class="relative w-72 h-48 outline">
	  <div class="absolute p-1 t-4 left-4 w-24 h-32 bg-red-300">CSS</div>
	  <div class="absolute p-1 top-8 left-8 w-24 h-32 bg-green-300">HTML</div>
		<div class="absolute p-1 top-16 left-34">
			<carbon-arrow-right />
		</div>
	  <div class="absolute p-1 top-8 left-42 w-24 h-32 bg-green-300">HTML</div>
	</div>
</div>
</div>

<div v-click="2">
<div
  v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 30, y: 80 }"
  :leave="{ y: 0, x: 80 }"
>
	<div class="relative w-72 h-48 outline">
	  <div class="absolute p-1 t-4 left-4 w-24 h-32 bg-red-300">CSS</div>
	  <div class="absolute p-1 top-8 left-8 w-24 h-32 bg-green-300">React</div>
		<div class="absolute p-1 top-16 left-34">
			<carbon-arrow-right />
		</div>
	  <div class="absolute p-1 top-8 left-42 w-24 h-32 bg-green-300">React</div>
	</div>
</div>
</div>


<!--
+ Tailwind和CSS in JS 解决了一个什么问题
+ 过去写CSS需要与HTML分开, 用了Tailwind或者CSS IN Js, 就只需要在一个文件中修改
-->
---
layout: center
class: text-center
---

# Thank you!

<PoweredBySlidev mt-10 />
