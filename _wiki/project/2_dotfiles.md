---
layout  : wiki
title   : 업무 투입 준비 (2) - dotfiles
summary : manage 개발환경 without tears & fears
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

![dev-env-gilbert](https://user-images.githubusercontent.com/65143458/135712697-bcadb539-efba-4947-9939-81b7e81df66a.gif)

## 개요

개발과 관련한 설정파일을 코드화 하여 언제 어디서나 빠르게 개발 환경을 구축하고, 컨텍스트 스위칭 비용 없이 익숙한 환경에서 작업하자


## 구성 방법

Mac 기준으로 아래와 같은 간단한 스크립트로 설치가 가능하다.

```bash
$ brew install stow
```

## 사용법

```bash
$ cd ~

$ mkdir .dotfiles && cd .dotfiles

$ mkdir -p vim/.vim

$ cp ~/.vim/init.vim vim./vim/init.vim

$ stow --adopt -vt ~ vim

```


## Links

* [stow workflow](https://www.youtube.com/watch?v=CFzEuBGPPPg&t=2010s): Sync your .dotfiles with git and GNU #Stow like a pro!

