+++
title = "A Happy New Years"
description = ""
date = "2015-01-01T00:42:45+09:00"
tags = ["雑感"]
categories = ["雑感"]
menu = "main"
+++

## A Happy New Years !
テストとして新年早々書いてみる。
新しくブログを始めるにあたり、HugoというGo言語で作られたサイトジェネレータを使って、GitHubでホストしてみた。

ブログに限り、エディタはAtom.ioを使って書く予定。
普段はSublimeTextやIntelliJを使っているけど、フロントエンドエンジニアのデファクトスタンダードであるJS（Coffee）で拡張できる良さを感じたくて、ブログで慣れていこうと思う。

コードスタイリングのテストとして、以下Hugoをデプロイするときに使っている公式に載っている`deploy.sh`

```html
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="A layout example that shows off a blog page with a list of posts.">

<title>{{ .Title }} &middot; {{ .Site.Title }}</title>
<link href='http://fonts.googleapis.com/css?family=Source+Sans+Pro:400,700|Oxygen:400,700' rel='stylesheet' type='text/css'>
<link rel="stylesheet" href="http://yui.yahooapis.com/pure/0.5.0/pure-min.css">
<!--[if lte IE 8]>
<link rel="stylesheet" href="http://yui.yahooapis.com/pure/0.5.0/grids-responsive-old-ie-min.css">
<![endif]-->
<!--[if gt IE 8]><!-->
<link rel="stylesheet" href="http://yui.yahooapis.com/pure/0.5.0/grids-responsive-min.css">
<!--<![endif]-->

<!--[if lte IE 8]>
<link rel="stylesheet" href="/css/layouts/blog-old-ie.css">
<![endif]-->
<!--[if gt IE 8]><!-->
<link rel="stylesheet" href="/css/blog.css">
<!--<![endif]-->
<link href="//netdna.bootstrapcdn.com/font-awesome/4.1.0/css/font-awesome.min.css" rel="stylesheet">
<link href="/css/highlight/tomorrow-night.css" rel="stylesheet">
<script src='/js/highlight.pack.js'></script>
<script>hljs.initHighlightingOnLoad();</script>
</head>
<body>
```

```sh
#!/bin/bash

echo -e "\033[0;32mDeploying updates to GitHub...\033[0m"

# Build the project.
hugo -t hyde-x

# Go To Public folder
cd public
# Add changes to git.
git add -A

# Commit changes.
msg="rebuilding site `date`"
if [ $# -eq 1 ]
then msg="$1"
fi
git commit -m "$msg"

# Push source and build repos.
git push origin master

# Come Back
cd ..
```
