---
title: Classic ASP 개발 환경 구성
author: BCY
date: 2024-07-05 23:35:00 +0900
categories: [asp, classic asp]
tags: [asp]
---
## 개요
업무로 인해 Classic ASP를 사용해보게 되었습니다.

Classic ASP는 자료가 별로 없어서 어떻게 개발 환경을 구성했는지 정리해보려고 합니다.

## ASP란?
ASP는 `Active Server Pages` 의 약자로, 웹 페이지를 구축하는 개발 프레임워크입니다.

ASP는 Classic ASP, ASP.NET(Web Forms, Web Pages, API, ...) 등 다양한 개발 모델을 지원하고 있습니다.


## Classic ASP란?
Classic ASP는 1998년 Microsoft의 첫 번째 서버 사이드 스크립팅 언어로 출시되었습니다.

Classic ASP 페이지는 파일 확장자가 .asp 이고 일반적으로 VBScript로 작성됩니다.

## Windows 개발 환경 구성
> OS: Windows 11
{: .prompt-info }

1. 시작에서 Windows 기능 켜기/끄기 검색
  <br/><img src="{{site.url}}/assets/img/blog/20240705/20240705_asp_devEnv_1.png" width="600"/>
2. Windows 기능 켜기/끄기에서 ASP 관련 기능 활성화
   <br/><img src="{{site.url}}/assets/img/blog/20240705/20240705_asp_devEnv_2.png" width="400"/>
  > [활성화 필요 항목]
  > - 인터넷 정보 서비스 > World Wide Web 서비스 > 보안, 상태 및 진단, 성능 기능
  > - 인터넷 정보 서비스 > World Wide Web 서비스 > 응용 프로그램 개발 기능 > ASP, ISAPI 확장
  > - 인터넷 정보 서비스 > 웹 관리 도구 > IIS 관리 콘솔
3. 시작에서 IIS(인터넷 정보 서비스) 관리자 검색
  <br/><img src="{{site.url}}/assets/img/blog/20240705/20240705_asp_devEnv_3.png" width="600"/>
4. IIS 관리자 페이지에서 ASP 항목 선택
  <br/><img src="{{site.url}}/assets/img/blog/20240705/20240705_asp_devEnv_4.png" width="600"/>
5. 컴파일 디버깅 속성 활성화
  <br/><img src="{{site.url}}/assets/img/blog/20240705/20240705_asp_devEnv_5.png" width="600"/>
  > [활성화 필요 항목]
  > - 브라우저에 오류 전송: True
  > - 서버 쪽 디버깅 사용: True
  > - 클라이언트 쪽 디버깅 사용: True
6. ASP 파일을 `C:\inetpub\wwwroot` 경로에 업로드
> ASP 업로드 경로를 변경하고 싶다면 [ASP 경로 변경하는 방법](#asp-경로-변경하는-방법) 참고
7. IIS 우측의 다시 시작 클릭
   <br/><img src="{{site.url}}/assets/img/blog/20240705/20240705_asp_devEnv_8.png" width="600"/>
8. 브라우저에 localhost/`asp 파일명`를 입력하여 확인

## ASP 경로 변경하는 방법
  업로드 경로는 Default Web Site > 모듈 우클릭 > 기본 설정에서 변경할 수 있습니다.
  <br/><img src="{{site.url}}/assets/img/blog/20240705/20240705_asp_devEnv_6.png" width="600"/>
  <br/><img src="{{site.url}}/assets/img/blog/20240705/20240705_asp_devEnv_7.png" width="600"/>

## 참고
> * [W3Schools](https://www.w3schools.com/asp/default.ASP)
> * [Tistory - Classic ASP 개발환경 세팅 (include, import, 디버깅)](https://gogoonbuntu.tistory.com/99)
