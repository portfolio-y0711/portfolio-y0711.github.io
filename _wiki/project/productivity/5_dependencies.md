---
layout  : wiki
title   : 업무 투입 준비 (5) - dependencies 정리하기
summary : 회사 pc에 설치할 목록을 정리해보자
date    : 2021-09-28 22:56:28 +0900
updated : 2021-09-28 22:56:29 +0900
tag     : project env
toc     : true
public  : true
parent  : [[/productivity/project/index]]
latex   : true
---
* TOC
{:toc}

![dependencies](https://user-images.githubusercontent.com/65143458/135738127-46c9e454-2d15-4e1e-8252-f5f8189c2560.jpeg)

## 개요

* 버전 관리자 (runtime version managers)

  * [nvm (alternatives: volta, n)](https://github.com/nvm-sh/nvm)

     ```shell
    $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
    ```

  * [pyenv (alternatives: pipenv, poetry)](https://github.com/pyenv/pyenv)

     ```shell
    $ brew install pyenv

    ```

  * [rbenv (alternatives: rvm)](https://github.com/rbenv/rbenv)

     ```shell
    $ brew install rbenv

    ```
<br/> 

* 문서 편집기 (editors)

  * [intellij IDEA](https://www.jetbrains.com/ko-kr/idea/download/#section=mac)

  * [vscode](https://code.visualstudio.com/download)

  * [neovim](https://github.com/neovim/neovim/wiki/Installing-Neovim)

     ```shell
    $ brew install neovim
    ```
    
<br/> 

* 개발환경/가상환경 구성 툴 (Provision / VM Tool)

  * [virtualbox](https://www.virtualbox.org/wiki/Downloads)

     ```shell
    $ brew install --cask virtualbox
    ```
    
  * [vagrant](https://www.vagrantup.com/downloads)

     ```shell
    $ brew install vagrant
    ```

  * [ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-macos)

     ```shell
    $ pip install ansible
    ```

  * [docker](https://docs.docker.com/desktop/mac/install/)

<br/> 

* 앱 (application)

  * [magnet](https://apps.apple.com/us/app/magnet/id441258766?mt=12)

  * [~~soundflower~~](https://soundflower.softonic.kr/mac/download)

  * [appcleaner](https://freemacsoft.net/appcleaner/)

  * [beyond compare](https://www.scootersoftware.com/download.php)

  * [Zoom](https://zoom.us/support/download?os=mac)

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
    
<br/> 

* ssh 프로토콜을 이용한 git clone

    ```shell
    $ git clone git@github.com-user1:user1/your-repo-name.git your-repo-name_user1
    ```
    
<br/> 

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


