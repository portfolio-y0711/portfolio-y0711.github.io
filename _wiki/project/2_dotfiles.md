---
layout  : wiki
title   : 업무 투입 준비 (2) - dotfiles
summary : 협업 개발환경 조성을 위해 프로젝트 위키 구성 후 공유하기
date    : 2021-09-24 22:56:28 +0900
updated : 2021-09-24 22:56:29 +0900
tag     : project env
toc     : true
public  : true
parent  : [[/project/index]]
latex   : true
---
* TOC
{:toc}

## 개요

회사 업무용 pc와 개인 pc의 설정파일을 동기화하여 언제나 익숙한 환경에서 추가 비용없이 컨텍스트를 이어나가자

## 구성 방법

[homebrew formulae](https://formulae.brew.sh/formula/stow)의 페이지에서 제공하는 설명대로 아래와 같은 간단한 스크립트로 설치가 가능하다.

```bash
$ brew install stow

$ cd ~/

$ mkdir .dotfiles

$ stow

```

## Links

* [johngrib-jekyll-skeleton](https://github.com/johngrib/johngrib-jekyll-skeleton):  프로젝트 위키 제작자(John Grib 기계인간)님의 프로젝트 저장소

