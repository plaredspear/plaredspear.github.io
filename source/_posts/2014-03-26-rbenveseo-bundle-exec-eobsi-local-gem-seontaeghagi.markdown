---
layout: post
title: "rbenv에서 bundle exec 없이 local gem 선택하기"
date: 2014-03-26 15:33:47 +0900
comments: true
categories: Ruby On Rails
---

- ###rvm의 gem version 관리

프로젝트가 늘어감에 따라, 프로젝트별로 gem version들을 관리해야할 필요가 생겼습니다.
rvm에서는 어떻게 gem version을 관리하는지 확인을 해보니, gem list를 그룹화한 gemset을 통해서 version을 관리하고 있더라구요.
그래서 작업할 프로젝트를 전환할 때는 gemset을 전환해줘야 합니다. (* gemset이 다를 경우)


- ###rbenv의 gem version 관리

rbenv에서는 rvm처럼 gemset을 따로 관리해주는게 아니라 프로젝트별로 관리를 하고 있습니다.
그렇기 때문에 프로젝트 전환시, 따로 gemset을 변환해줄 필요가 없습니다.

**(추정)** rbenv가 gem path를 프로젝트별로 등록해서 관리를 해주는 것 같습니다.


- ###rbenv 설치 후, bundle exec 요청

(rbenv 사용) bundle install을 통해서 gem을 설치한 후, rake 명령을 실행하였더니, bundle exec를 넣어달라고 요청을 하였습니다.
기존 rake(10.2.1)와 추가로 설치된 rake(0.9.6) 중에서 최신 버전을 선택하여 실행한 듯 보였습니다.

**(추정)** bundler를 통해 프로젝트별로 gem version을 세팅해주지만, rake 명령 자체는 global로 인식해서 최신 버전을 실행하는 것이 아닌가 합니다.
그래서 bundle exec 구문을 통해 local gem version을 선택하여 rake 명령을 실행하는 것이 아닌가 하는 추정입니다.


- ###rbenv-bundler, rbenv plug-in

rbenv plug-in : [rbenv-bundler](https://github.com/carsomyr/rbenv-bundler)

위의 플러그인을 활용하면, 초기 설정 후 bundle exec 구문없이 실행할 수 있습니다.
