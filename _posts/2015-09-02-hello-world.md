---
layout: post
title: "Hello World"
description: ""
category: 
tags: []
---
{% include JB/setup %}


음 .... 어떻게 하는건지.... 당췌....


## 안녕 여러분

### 이제 시작해요

뭘.... 이 블로그를

### 왜

????



### 자킬은 블로그 소프트웨어가 아니다??
**Jekyll is a parsing engine.**
그럼..?


**Developers like Jekyll because we can write content like we write code:**

- Ability to write content in markdown or textile in your favorite text-editor.
- Ability to write and preview your content via localhost.
- No internet connection required.
- Ability to publish via git.
- Ability to host your blog on a static web-server.
- Ability to host freely on GitHub Pages.
- No database required.



### 자킬 사용가이드

## Initial Setup

After [installing jekyll](/index.html#start-now) you'll need to format your website directory in a way jekyll expects.
Jekyll-bootstrap conveniently provides the base directory format.

### The Jekyll Application Base Format

Jekyll expects your website directory to be laid out like so:

    .
    |-- _config.yml
    |-- _includes
    |-- _layouts
    |   |-- default.html
    |   |-- post.html
    |-- _posts
    |   |-- 2011-10-25-open-source-is-good.markdown
    |   |-- 2011-04-26-hello-world.markdown
    |-- _site
    |-- index.html
    |-- assets
        |-- css
            |-- style.css
        |-- javascripts


- **\_config.yml**
	Stores configuration data.

- **\_includes**
	This folder is for partial views.

- **\_layouts**
	This folder is for the main templates your content will be inserted into.
	You can have different layouts for different pages or page sections.

- **\_posts**
	This folder contains your dynamic content/posts.
	the naming format is required to be `@YEAR-MONTH-DATE-title.MARKUP@`.

- **\_site**
	This is where the generated site will be placed once Jekyll is done transforming it.

- **assets**
	This folder is not part of the standard jekyll structure.
	The assets folder represents _any generic_ folder you happen to create in your root directory.
	Directories and files not properly formatted for jekyll will be left untouched for you to serve normally.

(read more: <https://github.com/mojombo/jekyll/wiki/Usage>)


