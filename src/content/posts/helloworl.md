---
title: helloworl
published: 2024-07-09
description: ''
image: ''
tags: [Markdown, Blogging]
category: ''
draft: false 
---
## 基于astro和vercel的博客创建
> 一开始因为什么都不同走了许多弯路，将这个方案搞复杂了，后面发现其实这个方案部署博客也是很方便的，本质上将astro工程托管到github，再通过vercel导入对应github仓库，然后便是vercel进行构建部署静态网页。现将主要步骤作下记录。
### 确定主题模板
本博客选用的是Fuwari主题
### 将主题的相关文件存放到github仓库
1. fork对应的主题仓库
2. 以主题仓库为模板创建新的仓库
3. astro 命令本地工程
### 更改配置文件
主要更改astro.config.mjs中的url映射，此处改为自已的vercel域名设置
```js
// https://astro.build/config
export default defineConfig({
  site: "https://xxx.vercel.app/",
```
### 添加新文章
```bash
pnpm new-post <filename>
```
### 内容编辑
src/content/posts/路径下会生成对应的markdown文件，直接在该文件中添加对应内容
### 预览
```bash
pnpm run dev
```
### 提交更新
正常github仓库提交