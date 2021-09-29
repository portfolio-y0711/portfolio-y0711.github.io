---
layout  : wiki
title   : 업무 투입 준비 (3) - taskwarrior + timewarrior + taskwiki
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

* 애자일, 칸반을 사용하는 스타트업에서 개발자가 조직의 목표 달성에 효과적으로 기여하기 위해서는 아래의 두가지가 필요함

    * (1) 피쳐 중심의 스크럼 개발을 할 수 있는 full-cycle 개발 능력 + 유연한 설계 능력을 갖추는 것 

    * (2) 스크럼 마스터 또는 PM이 백로그와 번다운 차트 관리를 통해 우선순위에 기반한 개발 계획을 수립해 나갈 수 있도록 개발 이슈와 진척도를 실시간으로 공유하는 것

* 두번째 항목과 관련하여 개발 이슈는 vimwiki로, 업무 진척도는 taskwarrior + timewarrior + taskwiki 를 활용하는 workflow에 익숙해지고자 함 (회사의 이슈 티케팅 시스템과 프로젝트 관리 툴에 맞춰야겠지만, 일단 이슈 관리/진척도 관리를 습관화할 수 있는 workflow를 수립하는 것이 중요하다 생각됨)

* GTD, 칸반은 오랜 시간 업무와 일상생활에서 사용해온 도구이지만, 별도의 GTD 관련 모바일앱이나 데스크탑 콘솔, Trello와 같은 웹 서비스를 이용하였기에 vim 또는 여타 코드 편집기, 개발일지/지식관리 시스템와의 연계성이 좋지 않았음.

* vimwiki + taskwiki로 cloud로 지식 관리 시스템과 할일 관리 시스템을 통합하여 관리할 수 있을 것으로 기대되며, 이를 통해 개발 과정 중에 업무 이슈와 진행사항이 자연스럽게 공유될 수 있는 workflow를 만들어 가고자 함.


## 구성 방법

* taskwarrior와timewarrior를 아래의 순서로 설치

    ```bash
    # taskwarrior 

    $ brew install task
    $ brew install taskd
    $ brew install tasksh

    # timewarrior 

    $ brew install timewarrior	
    ```

* Vim Plug 설정에 tbabej/taskwiki 플러그인 추가

    ```bash
    # timewiki 
    # ~/.vimrc 또는 ~/config/.vim/init.vim

    Plug 'tbabej/taskwiki'

    ```

## 사용법

* taskwarrior로 할일 목록 CRUD하기 

    * 쓰기:

        * task add '할일1'

            ```shell
            Created task 1.
            ```

        * task 1 done 

            ```shell
            Completed task 1 '할일1'.
            Completed 1 task.
            ```
    * 쓰기(우선순위):

        * task add pri:H '할일2'

            ```shell
            task add pri:H 할일2
            ```

    * 쓰기(날짜):

        * task add '할일3' due:2021-01-03

            ```shell
            task add 
            ```

        * task add 

            ```shell
            task add 
            ```

        * task add 

            ```shell
            task add 
            ```

        * task add 

            ```shell
            task add pri:H 할일2
            ```


    * 읽기: 

        * task (남은 할일 목록)

            ```shell
            [task next]

            ID Age  Description Urg
             1 3min Make Bed       0
             ```

        * task all (전체 할일 목록)

            ```shell
            # St (Status): Pending 대기 / Active 작업중 / Completed 완료 / Deleted 삭제
            ID St UUID     Age   Done Description
             1 P  3233605f 3s         Make Bed
             - D  7dbd827e 16s   6s   Clean the sink
             - C  37490e3e  3min 2min Throw out the trash
            ```

    * 수정: 

    * 삭제: 

        * task 1 delete (할일 삭제)

            ```shell
            $ task 1 delete 
            Deleted task 1.
            ```

        * task purge (할일 완전 삭제)

            ```shell
            $ task purge
            This command has no filter, and will modify all (including completed and deleted) tasks.  Are you sure? (yes/no)
            Permanently remove task .....?
            Purged 1 task.
            ```

        * 초기화

            ```shell
            rm  ~/.task/*.data
            ```

* timewarrior로 작업 시작/종료 하기

    * 훅 설정하기

        ```shell
        $ cd ~/.task/hooks

        $ wget https://raw.githubusercontent.com/GothenburgBitFactory/timewarrior/dev/ext/on-modify.timewarrior

        $ sudo chmod +x on-modify.timewarrior
        ```



    * 수동 시작

        * timew start '할일1' 태그이름

    * 일람하기

        * timew summary

        * timew summary :ids

* dashboard와burndown chart로 할일 목록과 진척도 그래프를 실시간(3초 지연)으로 확인하기

    * dashboard (할일 목록)

        ```shell
        # ~/.zshrc에 아래와 같은 프로시져를 등록해두고 호출하여 사용

        dsh() {
            while true; do clear && task next limit:3; sleep 3;done
        }

        # 터미널에서 프로시져 실행

        $ dsh
        ```
    
    * burndown chart

        ```shell
        # ~/.zshrc에 아래와 같은 프로시져를 등록해두고 호출하여 사용

        bdn() {
            while true; do clear && task burndown.daily; sleep 3; done
        }

        # 터미널에서 프로시져 실행

        $ bdn
        ```


## Links

* [taskwarrior workflow](https://www.youtube.com/watch?v=tijnc65soEI&t=2517s): A Dive into Taskwarrior Ecosystem with Tomas Babej


* [timewarrior workflow](https://www.youtube.com/watch?v=f_Be0CUVvA4): Taskwarrior + Timewarrior = Freelancing Bliss!!

* [taskwarrior tips](https://www.youtube.com/watch?v=8ECTOOWy9RY&list=PLDbCr4bKmB2ll9wBIUlVs4WdXPsA6GYlR&index=4) : More Taskwarrior Magic

* [taskwiki workflow](https://www.youtube.com/watch?v=UuHJloiDErM): Productivity Setup with Vimwiki, Part 2: Taskwarrior Integration


