---
layout  : wiki
title   : 온보딩 (1) - 인증(authentication)과 인가(authorization) 받기
summary : 구성원임을 인증(authenticate)받고, 권한(authorization)을 부여받기
date    : 2021-10-07 09:00:00 +0900
updated : 2021-10-07 09:00:00 +0900
tag     : project env
toc     : true
public  : true
parent  : [[/productivity/project/index]]
latex   : true
---
* TOC
{:toc}

![auth_auth](https://user-images.githubusercontent.com/65143458/136174321-6cb83cab-4274-45e8-a0a3-6ba05bfaea16.png)

## 개요

* 훗날 다른 동료의 온보딩을 돕게 되었을 때 참조하고자, 입사 후 설정했던 인증과 인가 과정을 정리하고자 함

## 인증

* 조직의 구성원임을 확인하는 가장 확실한 수단은 회사 도메인 주소가 담긴 이메일임

    * 인사팀에서 가장 먼저 전달해주는 것이 바로 이메일이고, 모든 인증의 기반이 됨

    * 구글 이메일의 Oauth 인증을 통해 아래의 서비스들에 기본적인 인증이 해결됨

        * Slack 

        * Jira 

        * Mongo Cloud
<br/>

* 그 외 조직 차원에서 관리되는 ID / Password는 1 Password로 관리함

    * 수 많은 계정들이 관리되고 있으나 온보딩 과정에서는 개인 계정에 대해서만 인증 수단을 부여받고, 나머지는 업무를 진행하며 조금씩 알아가면 됨

<br/>

* Multifactor

    * 회사의 중요 자산이 안전하게 보호될 수 있도록 아래 항목/서비스들에는 2 factor-authentication이 설정되어야 함 

        * 구글 계정 로그인
        
        * 깃헙 계정 로그인 

        * Mongo Cloud 계정 로그인

        * AWS 계정 로그인

<br/>

* VPN 설정
    
    * 회사 네트워크 접근이 필요한 경우 VPN을 이용해야 하며, VPN Server 설정 및 비번 설정이 필요함

## 역할(role)과 인가(authorization)

* 인증(authentication)이 구성원임을 증명하는 수단이라면, 인가(authorization)는 어떠한 일들을 할 수 있는가를 정하는 과정임

* 조직에서 어떠한 역할(role)을 수행하느냐에 따라 인가의 내용과 수준이 달라짐

* 권한에는 책임이 따르고, 이를 수행하기 위한 능력이 요구되니 역할에 맞는 능력을 갖춰 나가자

## Links

* [identity-101](https://www.okta.com/identity-101/authentication-vs-authorization/): Authentication vs. Authorization



