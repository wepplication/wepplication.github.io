---
layout: page-fullwidth
subheadline:  "애널리틱스"
title:  "애널리틱스를 이용해서 웹사이트 분석하기"
teaser: "웹 사이트 운영시 참고가 될 데이터를 무료로 만들어 주는 구글 애널리틱스를 사용하는 방법"
categories:
    - programming
tags:
    - Blog
header: no
image:
    title: "post/2020/05/analytics/analytics.jpg"
    thumb: "post/2020/05/analytics/analytics-thumb.png"
    homepage: "post/2020/05/analytics/analytics.jpg"
---
<!--more-->

## analytics란?

애널리틱스란 웹 사이트 트래픽을 추적하여 웹사이트의 실적을 돕는 도구로 사이트에 방문한 이용자 수, 유입 검색어, 방문자들이 어떤 유입채널을 통해 내 사이트에 방문하는지, 각 페이지에 방문자가 머무르는 시간은 얼마나 되는지 등을 추적하여 사이트 운영시 참고 할 수 있다.



## 구글 애널리틱스 가입하기

구글 계정으로 [[구글 애널리틱스]](https://analytics.google.com/analytics/web/) 페이지에 접속 후 가입을 한다.  

| ![계정 생성 화면]({{ site.urlimg }}post/2020/05/analytics/analytics-new-account.jpg) |
|사이트 정보 등을 입력한 후 [추적ID 가져오기] 버튼을 클릭 한다.|


| ![추적 코드 화면]({{ site.urlimg }}post/2020/05/analytics/analytics-gtag.jpg) |
|가입을 완료하면 내 고유 ID가 있는 추적 코드를 받을 수 있다.|


## 애널리틱스 코드 삽입하기

발급받은 추적 코드 스크립트를 분석을 할 모든 웹사이트 페이지에 붙여 넣으면 데이터 수집이 시작된다. 

{% highlight html %}
<html>
  <head>
  	...
	
    <!-- Global site tag (gtag.js) - Google Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=UA-?????????-1"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
    
      gtag('config', 'UA-?????????-1');
    </script>
  </head>
  <body>
  	...
  </body>
</html>
{% endhighlight %}



## TIP: 구글 애널리틱스 상세 유입 경로 보기

기본적으로 보이는 유입 경로에는 대표 URL로 나오고 있어 유입 페이지의 상세한 URL정보를 알 수 없다. 필터 설정을 통해 상세 URL 정보를 알 수 있다.

[관리] > [보기] > [필터] > [+필터추가] 버튼을 눌러 필터 추가 화면으로 이동한다.  


| ![필터 설정 화면]({{ site.urlimg }}post/2020/05/analytics/analytics-filter-setting.png) |
 
"필드 A -> 추출 A": [추천] 선택, "(.*)" 입력  
"출력대상 -> 생성자": [맟춤설정] 선택,  "$A1" 입력  
"입력란 A는 필수 항목입니다.", "출력 입력란 덮어쓰기" 체크  

설정 후 다음날 [잠재고객] > [맞춤] > [맞춤설정] 메뉴에서 상세 URL을 확인할 수 있다.


### 관련글
{: .t60 }

{% include list-posts %}