---
layout  : wiki
title   : 업무 투입 준비 (6) - misc. settings 적용하기
summary : 기타 자동화하기 어려운 개발환경 설정들
date    : 2021-10-4 10:00:00 +0900
updated : 2021-10-4 10:00:00 +0900
tag     : project env
toc     : true
public  : true
parent  : [[/productivity/project/index]]
latex   : true
---
* TOC
{:toc}

![Miscetc](https://user-images.githubusercontent.com/65143458/135802066-e7f02b30-0c90-4e82-845d-7cab05a3856c.jpeg)

## 개요

* Mac (System Preferences)

    * locate 서비스 활성화 

    ```
    $ sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.locate.plist

    $ sudo /usr/libexec/locate.updatedb\n\n
    ```

    * 키보드 설정

        * 한영 전환 

            System Preferences > Keyboard > Shortcuts > Input Sources 
            Select the previous input source : ⌃ ⇧ Space
 
        * Capslock

            System Preferences > Keyboard > Keyboard > Modifier Keys > Apple Magic Keyboard

            CapsLock(⇪) -> Control(⌃)

        * Ctrl

            System Preferences > Keyboard > Keyboard > Modifier Keys > Apple Magic Keyboard

            Control(⌃) -> Control (⇪)


* 터미널(terminal emulator)

    * [Iterm2](https://iterm2.com/downloads.html)

        * 설치

            ```
            $ brew install --cask iterm2
            ```

        * 필수 설정

            *  iTerm2 > Preferences > Profiles > Keys

                * [alt backspace로 단어 지우기]

                    ※ 변경 후: Left option key (⎇) -> +Esc로 설정
                    
                        
                    ![preferences](https://user-images.githubusercontent.com/65143458/135802758-eef1c57b-f8ec-4690-81a7-3879454b6fd9.png)


                * [alt key + (←) 로 한 단어 뒤로 이동하기]  #e5adefda

                    ※ 변경 전: Send Hex Codes 0x1b 0x1b 0x5b 0x44  

                    ※ 변경 후: keyboard shortcuts 추가(+) > (⎇ ←) Send Escape Sequence (+Esc) 선택 후 b 입력

                    ![backward](https://user-images.githubusercontent.com/65143458/135805390-3d2971f0-a72d-4b71-964d-b2217cc78e30.png)

                * [alt key + (→) 로 한 단어 뒤로 이동하기]

                    ※ 변경 전: Send Hex Codes 0x1b 0x1b 0x5b 0x43  

                    ※ 변경 후: keyboard shortcuts 추가(+) > (⎇ →) Send Escape Sequence (+Esc) 선택 후 f 입력


                    ![forward](https://user-images.githubusercontent.com/65143458/135805377-dd5878f0-1783-45e3-b8e4-e7696dea666c.png)


        * 기타 설정

                * [ 비프음 제거 ]

                ※ 변경 후: Preferences  Profiles > Terminal > "Silence bell" check


## Links

* [Jump forwards, backwards and delete a word in iTerm2 on Mac OS
](https://medium.com/@jonnyhaynes/jump-forwards-backwards-and-delete-a-word-in-iterm2-on-mac-os-43821511f0a):  Jonny Haynes

