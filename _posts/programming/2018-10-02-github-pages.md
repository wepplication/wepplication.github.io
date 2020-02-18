---
layout: page-fullwidth
subheadline:  "정적 웹호스팅"
title:  "GitHub Pages를 이용한 무료 홈페이지 만들기"
teaser: "정적 웹 사이트 호스팅을 해주는 깃허브 페이지를 이용해 나만의 웹 페이지를 무료로 만들 수 있다. GitHub 사이트 가입부터 git 저장소 생성/제거, 깃허브 페이지를 이용한 웹 사이트 호스팅 하는 방법을 소개한다."
categories:
    - programming
tags:
    - Hosting
    - Github
header: no
image:
    title: "post/2018/10/github-pages/github_pages.jpeg"
    thumb: "post/2018/10/github-pages/github_pages-thumb.png"
    homepage: "post/2018/10/github-pages/github_pages.jpeg"
---
<!--more-->


## Github Pages란?

깃허브(Git Hub)는 깃(소프트웨어 개발에서 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 분산 버전 관리 시스템)을 좀 더 편하게 이용하도록 만든 
깃 서버 웹 호스팅 서비스이고 오픈소스 소프트웨어의 중심지(hub) 역할을 하면서 오픈소스 프로젝트가 널리 퍼지는 데 크게 기여하고 있는 서비스입니다.  
깃허브 페이지(GitHub Pages)는 이러한 깃허브에서 제공하는 정적 사이트 호스팅 서비스로 일반적인 HTML 콘텐츠를 지원하는 것 외에도 인기있는 정적 사이트 생성기인 Jekyll을 지원합니다.  



## Github 가입하기

| ![Github 가입창]({{ site.urlimg }}post/2018/10/github-pages/github-signup.png) |
| [http://github.com](http://github.com){:target="_blank"} 으로 접속하여 Username, Email, Password를 입력 후 Sign up for GitHub를 눌러 가입 한 후 이메일 인증을 거치면 가입이 끝이납니다. |  

여기서 사용자이름(Username)은 이후 생성되는 깃허브 페이지 사이트의 도메인이 됩니다. (***사용자이름***.github.io)


## GitHub 저장소 생성하기  

|![저장소 생성 메뉴]({{ site.urlimg }}post/2018/10/github-pages/github-menu.png)|
|우측 상단의 "+" 아이콘을 누른 후 "New repository"를 누릅니다.|

|![저장소 생성 폼]({{ site.urlimg }}post/2018/10/github-pages/github-createrepo.png)|
|Repository name에 원하는 저장소 이름을 누르고 Create repository 버튼을 눌러줍니다.|  

>특정 몇 명만 코드에 접근할 수 있는 프라이빗 저장소는 유료이며 무료로 만들경우 소스 코드가 모두 공개되니 개인정보가 보이지 않도록 주의 해야합니다.  


## 로컬 저장소에 깃허브 저장소 복제하기

프로젝트를 저장할 폴더로 이동하여 새 저장소를 복제하기
{% highlight sh %}
git clone git@github.com:사용자이름/저장소이름.git
{% endhighlight %}  
이제 해당 프로젝트 폴더에 index.html 파일을 추가하여 별도의 서버 없이 포트폴리오 사이트 같은 간단한 사이트를 만들 수 있다.
>로컬 저장소를 [Cloud9](https://c9.io/){:target="_blank"}, [구름IDE](https://ide.goorm.io/){:target="_blank"} 같은 클라우드 개발툴을 이용하면 특정 컴퓨터가 아닌 어디서든 사용할 수 있다.


## 깃허브 저장소 PUSH

변경사항 깃허브 저장소에 push하기
{% highlight sh %}
$ git add .
$ git commit -m "first commit"
$ git push
{% endhighlight %}  
>브라우저로 "https://github.com/***사용자이름***/***저장소이름***" 에 접속을 해보면 깃허브 저장소를 볼 수 있다.


## Github Pages 사용하기  

브라우저로 "https://github.com/***사용자이름***/***저장소이름***/settings" 에 접속을 하면 저장소 설정을 하실 수 있습니다.

|![깃허브 페이지 설정]({{ site.urlimg }}post/2018/10/github-pages/github-pagesetting.png)|
|하단에 있는 GitHub Pages > Source에 None으로 된 선택창을 master branch로 변경 후 Save|

깃 페이지 소스 설정을 하면 저장소에 올린 파일들로 정적 사이트를 생성합니다.  
https://***사용자이름***.github.io/***저장소이름***/ 으로 접속하면 사이트를 볼 수 있습니다.  

**※ 파일 위치에 따른 URL**  

|![파일 목록]({{ site.urlimg }}post/2018/10/github-pages/github-filelist.png)|

/index.html 파일은 https://***사용자이름***.github.io/***저장소이름***/  
/aaa/index.html 파일은 https://***사용자이름***.github.io/***저장소이름***/aaa  
/bbb.html 파일은 https://***사용자이름***.github.io/***저장소이름***/bbb

> git push 후 바로 반영이 되지 않고 어느정도 시간이 지나야 반영된다.  


## GitHub Pages URL 뒤에 저장소 이름없이 생성하기

repository생성후 page를 활성화하면  
"https://***사용자이름***.github.io/***저장소이름***/" 으로 사이트가 생성된다.  
"https://***사용자이름***.github.io/" 주소로 바로 연결되게 하고 싶으면
깃허브 저장소 생성 시 Repository name에 "***사용자이름***.github.io"로 생성을 하면 된다.
>"***사용자이름***.github.io"로 저장소를 생성할 경우 별도로 깃허브 페이지 활성 설정을 하지 않아도 사이트가 생성된다.


## GitHub Pages 의 제한 사항

- GitHub Pages source repositories have a recommended limit of 1GB .
- Published GitHub Pages sites may be no larger than 1 GB.
- GitHub Pages sites have a soft bandwidth limit of 100GB per month.
- GitHub Pages sites have a soft limit of 10 builds per hour.
> GitHub Pages 소스 저장소의 권장 제한은 1GB입니다.  
> 게시 된 GitHub 페이지 사이트는 1GB를 초과 할 수 없습니다.  
> GitHub 페이지 사이트의 대역폭 제한은 한 달에 100GB입니다.  
> GitHub 페이지 사이트의 builds 제한은 시간당 10회 입니다.  


## 기본적인 Git 명령어

{% highlight sh %}
# git 사용자 정보 설정
git config user.name "사용자 이름"
git config user.email 이메일주소
{% endhighlight %}

{% highlight sh %}
# 현재 디렉토리에 git 저장소를 생성
git init
{% endhighlight %}

{% highlight sh %}
# 수정한 파일들을 스테이징 영역에 올리기
git add .
{% endhighlight %}

{% highlight sh %}
# 스테이징 영역에 올라가 있는 파일들을 커밋
git commit -m "변경된 메시지 내용을 입력"
{% endhighlight %}

{% highlight sh %}
# 원격저장소에 푸시 (-u는 원격저장소로부터 업데이트를 받은 후 push를 한다는 의미, origin과 master는 각각 리모트 저장소와 브랜치를 의미합니다.)
git push -u origin master

# 강제 push(덮어쓰기)
git push -f
{% endhighlight %}

{% highlight sh %}
# 원격저장소를 복제하여 저장소를 생성
git clone 저장소주소
{% endhighlight %}

{% highlight sh %}
# 새로운 원격 저장소를 추가
git remote add 이름 저장소주소
{% endhighlight %}

{% highlight sh %}
# 원격 저장소를 제거
git remote rm 이름
{% endhighlight %}  

{% highlight sh %}
# 원격 저장소에 있는 .gitignore 파일들 제거
$ git rm -r --cached .
$ git add .
$ git commit -m "Apply .gitignore"
$ git push
{% endhighlight %}  



## GitHub 저장소 삭제하기

브라우저로 "https://github.com/***사용자이름***/***저장소이름***/settings" 에 접속을 해서  
하단에 있는 Danger Zone > Delete this repository > "Delete this repository" 버튼을 누른 후  
팝업창에 저장소이름을 입력 후 "I understand the consequences, delete this repository" 버튼을 누른다.



## TIP : git 설치 없이 사용하기  

깃허브 저장소를 생성하면 깃허브 주소와 함께  
"We recommend every repository include a README, LICENSE, and .gitignore." 라는 메세지를 볼 수 있다.  
여기서 README 버튼을 클릭하면 텍스트 입력창이 나오는데 

|![깃허브 저장소]({{ site.urlimg }}post/2018/10/github-pages/github_newrepo.png)|
|임의로 내용을 입력 후 하단에 "Commit new file"을 누른다.|

여기에 입력을 하여 저장소에 README 파일을 추가 할 수 있다.

|![깃허브 파일추가]({{ site.urlimg }}post/2018/10/github-pages/github_createfile.png)|

이 후 "Create new file" 버튼으로 직접 파일 내용을 입력해 생성하거나 "Upload files" 버튼으로 파일을 업로드 할 수도 있다.  

|![깃허브 파일쓰기]({{ site.urlimg }}post/2018/10/github-pages/github_writefile.png)|

파일 내용 입력 화면의 상단 파일명 입력칸에 "폴더명/파일명.확장자"를 입력하여 폴더를 생성할 수도 있다.  


|![깃허브 파일수정]({{ site.urlimg }}post/2018/10/github-pages/github_modfile.png)|

파일을 수정할 때는 깃허브 페이지에서 파일 내용을 조회 한 뒤 우측 상단 연필 모양의 아이콘을 눌러 수정할 수 있다.  



## 유사 서비스

깃허브 페이지와 같이 무료로 정적 웹 사이트 호스팅을 제공하는 서비스들이 많이 있다.

> - [Gitlab Pages](https://about.gitlab.com/stages-devops-lifecycle/pages/){:target="_blank"}  
> - [Netlify](https://www.netlify.com){:target="_blank"}  
> - [Neocities](https://neocities.org){:target="_blank"}  



## 요약

GitHub 저장소 생성  

{% highlight sh %}
# 로컬 저장소로 클론
git clone git@github.com:사용자이름/저장소이름.git
{% endhighlight %}  

로컬 저장소에 index.html 등(HTML, CSS, JS) 파일추가  

{% highlight sh %}
# 원격 저장소에 PUSH
git add .
git commit -m "commit comment"
git push
{% endhighlight %}  

"https://github.com/***사용자이름***/***저장소이름***/settings" 에 접속  
GitHub Pages > Source 항목에서 master branch로 선택 후 Save  

일정 시간이 지난 후  
"https://***사용자이름***.github.io/***저장소이름***/" 으로 사이트 접속  

※ 저장소 이름을 "***사용자이름***.github.io" 으로 생성했을 경우 "https://***사용자이름***.github.io/" 으로 사이트 접속  



## 참고 자료    

Git : [https://git-scm.com/](https://git-scm.com/){:target="_blank"}

GitHub : [https://github.com/](https://github.com/){:target="_blank"}

GitHub Help : [https://help.github.com/](https://help.github.com/){:target="_blank"}

GitHub Pages : [https://pages.github.com/](https://pages.github.com/){:target="_blank"}




### 관련글
{: .t60 }

{% include list-posts category='programming' %}