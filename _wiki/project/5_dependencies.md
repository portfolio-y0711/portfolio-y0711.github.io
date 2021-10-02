---
layout  : wiki
title   : 업무 투입 준비 (5) - dependencies 정리하기
summary : 회사 pc에 설치할 목록을 정리해보자
date    : 2021-09-29 22:56:28 +0900
updated : 2021-09-29 22:56:29 +0900
tag     : project env
toc     : true
public  : true
parent  : [[/project/index]]
latex   : true
---
* TOC
{:toc}

## 개요

* 버전 관리자 (runtime version managers)

  * nvm (alternatives: volta, n)

  * pyenv (alternatives: pipenv, poetry)

  * rbenv (alternatives: rvm)

* 문서 편집기 (editors)

  * intellij IDEA

  * vscode

  * neovim

* 앱 (application)

  * magnet

  * ~~soundflower~~

  * virtualbox

  * vagrant

  * ansible

  * docker

  * appcleaner

  * beyond compare 


## 구성 방법

* ssh 설정 파일 구성

    ```shell
    #config file at ~/.ssh

    #user1 account
    Host github.com-user1
       HostName github.com
       User git
       IdentityFile ~/.ssh/github-user1
       IdentitiesOnly yes

    #user2 account
    Host github.com-user2
       HostName github.com
       User git
       IdentityFile ~/.ssh/github-user2
       IdentitiesOnly yes
    ```

* ssh 프로토콜을 이용한 git clone

    ```shell
    $ git clone git@github.com-user1:user1/your-repo-name.git your-repo-name_user1
    ```

* 아래의 명령어로 로컬의 .git/config 파일을 수정하거나, 직접 경로 접근하여 수정함

    ```shell
    $ git config --local -e 

    .git/config

    [remote "origin"] 
    url = git@github.com-user1:user1/your-repo-name.git
    fetch = +refs/heads/*:refs/remotes/origin/*

    [user]
    name = user1
    email = user1@gmail.com
    ```
## Links

* [Handling Multiple Github Accounts on MacOS](https://gist.github.com/Jonalogy/54091c98946cfe4f8cdab2bea79430f9):  Jonalogy/handling_multiple_github_accounts.md


