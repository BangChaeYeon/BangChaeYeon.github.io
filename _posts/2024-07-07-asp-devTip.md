---
title: Classic ASP 개발 가이드
author: BCY
date: 2024-07-07 12:29:27 +0900
categories: [asp, classic asp]
tags: [asp]
---

## 개요
Classic ASP를 사용하면서 알게 된 내용을 정리해보고자 글을 작성하게 되었습니다.

## 기초 문법
Classic ASP는 키워드의 대소문자를 구분하지 않습니다.

### 변수 선언
변수 선언은 타입 없이 `Dim` 키워드를 사용합니다.
> Dim foo

### 변수 대입
Classic ASP는 Object와 Object 이외의 값을 변수에 대입하는 방법이 다릅니다.

#### Object 값 대입의 경우
> Set foo = Server.CreateObject("bar")


#### Object 이외의 값 대입의 경우
> foo = "bar"


> 선언과 대입을 동시에 할 수 있습니다.
>
> Dim foo : Set foo = Server.CreateObject("bar")
{: .prompt-tip }

## HTTP Request
Post로 HTTP Request를 요청하는 방법입니다.
<img src="{{site.url}}/assets/img/blog/20240707/20240707_asp_devTip_1.png" width="600"/>

## QueryString Parsing
QueryString 데이터를 Java의 Map처럼 key, value 형태로 파싱하는 방법입니다.
<img src="{{site.url}}/assets/img/blog/20240707/20240707_asp_devTip_2.png" width="600"/>

## Execute exe
exe 파일을 실행하고 결과 값을 받아오는 방법입니다.
<img src="{{site.url}}/assets/img/blog/20240707/20240707_asp_devTip_3.png" width="600"/>
