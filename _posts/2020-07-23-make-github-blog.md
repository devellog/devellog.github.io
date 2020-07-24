---
layout: post
title:  "Github 블로그 만들기"
date:   "2020-07-23 00:00:00"
author: Sean
categories: jekyll
tags:	jekyll github-page centrarium
---

## 사전 지식

Git + VSCode 쪼금

Markdown + VSCode 쪼금

HTML 쪼금


<br/>
## 테마

**_Centrarium_** [link to jekyllthemes.org](http://jekyllthemes.org/themes/centrarium)


<br/>
## 참고

[[GitHub Pages] 01 - Repository 생성](https://luke7102.github.io/dev/2019/12/09/dev-create-blog-01.html)

[[GitHub Pages] 02 - 블로그 로컬 개발환경 설정](https://luke7102.github.io/dev/2019/12/09/dev-create-blog-02.html)

[[GitHub Pages] 03 - Jekyll Theme 적용하기](https://luke7102.github.io/dev/2019/12/10/dev-create-blog-03.html)

[[GitHub Pages] 04 - Post 작성하기](https://luke7102.github.io/dev/2019/12/10/dev-create-blog-04.html)

[[GitHub Pages] 05 - Travis CI 연동 및 배포](https://luke7102.github.io/dev/2019/12/10/dev-create-blog-05.html)

[Travis-ci를 이용해 배포 자동화 시키기](https://imreplay.com/blogging/Travis-ci%EB%A5%BC-%ED%86%B5%ED%95%B4-%EB%B0%B0%ED%8F%AC%EC%9E%90%EB%8F%99%ED%99%94/)


<br/>
## 적용기

* '[GitHub Pages] 05 - Travis CI 연동 및 배포' 에서 막힘

  -- Ruby 버전 문제  
&nbsp;&nbsp; '.travis.yml 파일 작성' 에 'rvm: 2.3.3' 을 'rvm: **_2.6.6_**' 으로 변경

  -- Rakefile 없음  
&nbsp;&nbsp; 'Travis-ci를 이용해 배포 자동화 시키기' 에 '**_Rakefile 작성_**' 참고 (아래는 수정한 부분) 

{% highlight ruby %}
#USERNAME = CONFIG["username"]
#REPO = CONFIG["repo"]
#SOURCE_BRANCH = CONFIG["branch"]
#DESTINATION_BRANCH = "gh-pages"
USERNAME = "devellog"
REPO = "devellog.github.io"
SOURCE_BRANCH = "source"
DESTINATION_BRANCH = "master"

cache: bundler
{% endhighlight %}

* 삽질기간  

  -- 2주


<br/>
