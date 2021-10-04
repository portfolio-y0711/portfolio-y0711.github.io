---
layout  : wiki
title   : 업무 투입 준비 (1) - project wiki 구축하기
summary : 협업 개발환경 조성을 위해 프로젝트 위키 구성 후 공유하기
date    : 2021-09-24 22:56:28 +0900
updated : 2021-09-24 22:56:29 +0900
tag     : project env
toc     : true
public  : true
parent  : [[/productivity/project/index]]
latex   : true
---
* TOC
{:toc}

![library](https://user-images.githubusercontent.com/65143458/135736524-c8d6257b-9ec1-453e-b2d5-97e7a56179b3.jpeg)

## 개요

개발과정 중에 발생한 이슈와 문제 해결 사례를 기록하고 추후 개선 방향을 공유하기 위해 프로젝트 위키를 구성한다. 

## 구성 방법

빠른 스캐폴딩을 위해 [wiki-skeleton-template](https://github.com/portfolio-y0711/wiki-skeleton-template) 을 클론합니다.

```shell
$ git clone https://github.com/portfolio-y0711/wiki-skeleton-template

$ cd wiki-skeleton-template
```

루비 및 jekyll이 설치되어 있지 않다면, 루비 버전 매니저인 [rbenv](https://github.com/rbenv/rbenv)를 설치하고, 
아래 스크립트를 순차적으로 실행합니다.

```shell
$ brew install rbenv

$ eval "$(rbenv init -)"

$ rbenv install -l
2.6.8
2.7.4
3.0.2
...

$ rbenv install 3.0.2

$ rbenv global 3.0.2

$ gem install jekyll

$ gem install bundler

$ bundle add webrick
(why? https://github.com/jekyll/jekyll/issues/8523)

```

필수는 아니지만 vim 사용자라면, vimwiki(https://github.com/vimwiki/vimwiki) 플러그인을 설치하여 위키 작성 워크플로우를 개선할 수 있습니다.

자세한 내용은 링크 동영상 및 관련 블로그글를 참고하시기 바랍니다. 

## 주요 설정 변경

* about.md

    * 자기소개 페이지입니다.

    * 마크다운 형식을 따라 쉽게 수정 가능합니다 

* index.html

    * 첫 화면을 구성하는 html 파일로 제목, 항목명 등을 수정하고, 해당 페이지에서 사용되는 주요 메타 데이터는 _config.yml에서 불러옵니다. 
    

* _config.yml

    * 모르는 설정은 건드리지 않는 것을 원칙으로, #Site settings와 #My information을 변경합니다.

    * disqus

    * utterance

    * google_analytics

    * google_adsense

    * blame

    * edit

    * issue

* css/main.scss

    * 자신만의 색을 찾으세요!

    * 저는 따뜻함과 활동성과 호기심을 상징하는 오렌지색을 선택했습니다.



## Links

* [johngrib-jekyll-skeleton](https://github.com/johngrib/johngrib-jekyll-skeleton):  프로젝트 위키 제작자(John Grib 기계인간)님의 프로젝트 저장소

* [vimwiki workflow](https://www.youtube.com/watch?v=A1YgbAp5YRc): Productivity Setup with Vimwiki, Taskwarrior and MDwiki: Part 1


