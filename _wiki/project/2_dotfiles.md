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

회사 업무용 pc와 개인 pc의 설정파일을 동기화하여 컨텍스트 스위칭 비용 없이 익숙한 환경에서 작업하기

## 구성 방법

[homebrew formulae](https://formulae.brew.sh/formula/stow)의 소개와 같이 아래와 같은 간단한 스크립트로 설치가 가능하다.

```bash
$ brew install stow

$ cd ~/

$ mkdir .dotfiles

$ cp ~/.any-config-files .

$ stow
```

## Links

* [stow workflow](https://www.youtube.com/watch?v=CFzEuBGPPPg&t=2010s): Sync your .dotfiles with git and GNU #Stow like a pro!

