---
layout  : wiki
title   : 업무 투입 준비 (4) - multiple git account 사용하기
summary : 회사 업무용 계정과 학습용 계정 분리하기
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

![setup-multiple-git-account-on-a-system](https://user-images.githubusercontent.com/65143458/135736307-4cdb2c71-16df-4a86-af07-16fee10719c0.png)

## 개요

* 회사에서 개발 장비를 지급하는 것으로 알고 있고, 회사 개발 pc에는 업무와 관련성 없는 작업을 하지 않을 예정이라 multiple git account를 사용할 일은 거의 발생하지 않을 거라 생각함

* 그럼에도 불구하고 별도의 개발 장비가 지급되지 않아 개인 장비로 회사 개발 업무를 수행해야 하거나, 휴가 중에 개인 pc에서 회사 업무를 급하게 처리해야하는 경우와 같이 일반적이지 않은 상황을 가정하여, 유사시 multiple git account 사용하는 방법을 정리하고자 함.

* 맥OS에서는 Keychain이란 비밀번호 관리 시스템을 사용하고 있는데, Keychain에 github 계정 접속을 위임할 경우 계정 변경 시마다 기존 Keychain을 삭제하고 다시 인증을 해야 하는 번거로움이 있음.

* 로컬 리포지토리 별로 ssh 접속을 위한 Host를 별도로 지정하고, Host 마다 다른 ssh 키를 사용하도록 설정을 변경해 주어야 함.

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


