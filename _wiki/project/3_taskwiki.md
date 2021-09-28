---
layout  : wiki
title   : 업무 투입 준비 (3) - taskwiki
summary : GTD, 칸반을 위한 할일 관리 시스템
date    : 2021-09-25 22:56:28 +0900
updated : 2021-09-25 22:56:29 +0900
tag     : project env
toc     : true
public  : true
parent  : [[/project/index]]
latex   : true
---
* TOC
{:toc}

## 개요

* 개발자의 입장에서 애자일, 스크럼, 칸반과 업무 방법론 하에서 조직의 목표 달성에 기여하기 위해서는 아래의 두가지를 항상 염두에 두고 있어야 한다고 생각함

    * (1) 피쳐 중심 개발을 할 수 있는 구현 능력 + 유연한 설계 능력을 갖추는 것 

    * (2) 동료 구성원들과 스크럼 마스터가 개발 이슈와 업무 진척도를 확인할 수 있도록 적극적으로 정보를 공유하고 소통을 하는 것

* 이와 관련하여 개인적인 차원에서 개발 이슈는 vimwiki로, 업무 진행사항에 대한 공유는 taskiwiki를 활용하는 방안을 모색중임 (회사에도 물론 이슈 티케팅 시스템과 업무 관리 시스템이 있겠지만, 자신만의 편한 workflow로 먼저 1차 가공을 하는 것이 필요하다고 생각함)

* GTD, 칸반은 오랜 시간 업무와 일상생활에서 사용해온 도구이지만, 이번에 vimwiki로 cloud 지식 관리 시스템을 구축하면서 할일 관리도 vimwiki와 통합하여 관리해보고자 함.

* 기존에는 별도의 GTD 관련 모바일앱이나 데스크탑 콘솔, Trello와 같은 웹 서비스를 이용하였으나 vim 또는 여타 코드 편집기, 개발일지/지식관리 시스템와의 연계성이 좋지 않았음.

* vimwiki - taskiwiki의 연계를 통해, 업무 이슈와 진행사항이 자연스럽게 공유될 수 있는 workflow를 구축해 가고자 함.


## 구성 방법

```bash
$ brew install task
$ brew install taskd
$ brew install tasksh


$ cd ~/

$ mkdir .dotfiles

$ stow

```

## Links

* [johngrib-jekyll-skeleton](https://github.com/johngrib/johngrib-jekyll-skeleton):  프로젝트 위키 제작자(John Grib 기계인간)님의 프로젝트 저장소

