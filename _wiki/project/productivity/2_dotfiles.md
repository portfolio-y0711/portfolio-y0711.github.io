---
layout  : wiki
title   : 업무 투입 준비 (2) - dotfiles
summary : manage 개발환경 without tears & fears
date    : 2021-09-25 22:56:28 +0900
updated : 2021-09-25 22:56:29 +0900
tag     : project env
toc     : true
public  : true
parent  : [[/productivity/project/index]]
latex   : true
---
* TOC
{:toc}

![dev-env-gilbert](https://user-images.githubusercontent.com/65143458/135712697-bcadb539-efba-4947-9939-81b7e81df66a.gif)

## 개요

개발과 관련한 설정파일을 코드화 하여 언제 어디서나 빠르게 개발 환경을 구축하고, 컨텍스트 스위칭 비용 없이 익숙한 환경에서 작업을 이어나가기


## 구성 방법

Mac 기준으로 아래와 같은 간단한 스크립트로 설치가 가능하다.

```bash
$ brew install stow
```

## 사용법

* stow는 구성 파일이 있어야 할 위치에 심볼릭 링크를 위치시키는 방식으로 동작함

  * 응용 프로그램이 읽어야 할 실제 설정은 사용자가 지정한 폴더(예를 들어 ~/.dotfiles/)에 모아두고, 응용 프로그램이 실제로 설정 파일을 읽도록 예정된 장소에는 설정 파일에 대한 참조(심볼릭 링크)를 남겨두는 방식으로 동작함

  * 이를 위해 사용자 지정 폴더(예를 들면 ~/.dotfiles/)에 실제 구성 파일이 존재하는 경로와 동일한 상대경로를 구성하고 아래와 같이 stow에 타겟 경로를 파라미터로 전달함 

  * 일반적으로 ~ 경로 아래에 설정 파일이 위치하는 경우가 많으므로, 타겟 경로는 ~를 생략하기도 함

* 주로 사용하는 옵션은 아래와 같음

  * --adopt : 타겟 폴더에 있는 구성 파일의 변경 내용이 사용자 지정 폴더에 갱신됨

  * -v, --verbose : 처리 과정 관련 로그 출력 

  * -t, --target=DIR : 타겟 폴더 지정 (초기값은 사용자 지정 폴더의 상위 폴더)

  * -d, --dir=DIR : 사용자 지정 폴더 (초기값은 현재 폴더)

## 사용 예시

```shell
$ cd ~

$ mkdir .dotfiles && cd .dotfiles

$ mkdir -p vim/.vim

$ cp ~/.vim/init.vim vim./vim/init.vim

$ stow --adopt -vt ~ -d vim
```


## Links

* [stow workflow](https://www.youtube.com/watch?v=CFzEuBGPPPg&t=2010s): Sync your .dotfiles with git and GNU #Stow like a pro!

