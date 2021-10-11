---
layout  : wiki
title   : 협업의 기술 (1) - pull request 보내기 전에 커밋 메시지 squash하기 
summary : 단일 브랜치에서 rebase를 사용하기
date    : 2021-10-09 09:00:00 +0900
updated : 2021-10-09 09:00:00 +0900
tag     : project env
toc     : true
public  : true
parent  : [[/productivity/project/index]]
latex   : true
---
* TOC
{:toc}

![squash](https://user-images.githubusercontent.com/24386223/136682557-be733d2e-c800-47b4-8e69-5c82d0269859.jpeg)


## 개요

master에 pull request 요청을 보내 merge를 하는 협업 Flow를 사용하는 경우 feature-branch의 commit한 내역이 많으면 master
의 커밋 히스토리가 매우 복잡해지게 됨

## 메시지 정리

pull request 요청을 보내고 git merge할 때 squash merge를 할수도 있겠지만, pull request 보내기 전에 로컬 브랜치에서 rebase를 통해 git commit을 통합할 수도 있음

## 예시

* squash

    ```shell
    $ git rebase -i HEAD~3

    # 변경전
    pick 6993eaf [LUKE-559] unit, i11 테스트 스캐폴딩
    pick 5a08c42 [LUKE-559] feature 테스트 스캐폴딩
    pick 8e227f1 [LUKE-559] mongodb 테스트 스캐폴딩

    # 변경후
    r 6993eaf [LUKE-559] unit, i11 테스트 스캐폴딩
    s 5a08c42 [LUKE-559] feature 테스트 스캐폴딩
    s 8e227f1 [LUKE-559] mongodb 테스트 스캐폴딩
    ```

    * 변경 전

        * 8e227f1 - (HEAD -> feature/559-project-setup, origin/feature/559-project-setup) [LUKE-559] mongodb 테스트 스캐폴딩 (64 minutes ago) <portfolio-y0711>
        * 5a08c42 - [LUKE-559] feature 테스트 스캐폴딩 (77 minutes ago) <portfolio-y0711>
        * 6993eaf - [LUKE-559] unit, i11 테스트 스캐폴딩 (82 minutes ago) <portfolio-y0711>
        * 44ca663 - (origin/main, main) Initial Commit (2 days ago) <portfolio-y0711>

    <br/>

    * 변경 후

        * 1023391 - (HEAD -> feature/559-project-setup) [LUKE-559] 프로젝트 스캐폴딩 (2 hours ago) <portfolio-y0711>
        * 44ca663 - (origin/main, main) Initial Commit (2 days ago) <portfolio-y0711>

## Links

* [git --squash merge](https://blog.dnsimple.com/2019/01/two-years-of-squash-merge/): Two years of squash merge



