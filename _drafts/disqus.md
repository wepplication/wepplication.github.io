---
layout: page
subheadline:  "댓글 서비스"
title:  "무료 댓글 서비스 Disqus 사용하기"
teaser: "Disqus 서비스를 이용해 블로그에 댓글 달기"
categories:
    - programming
tags:
    - Blog
header: no
image:
    title: "post/2018/10/disqus/disqus.jpg"
    thumb: "post/2018/10/disqus/disqus-thumb.jpg"
    homepage: "post/2018/10/disqus/disqus.jpg"
---
<!--more-->

## Disqus란?





## Disqus 가입하기




## 내 사이트에 Disqus 적용하기




## 댓글창 한글 적용하기




## 최근 댓글 위젯

{% highlight html %}
<div id="recentcomments" class="level2" style="">
<strong>Recent Comments</strong>
<script type="text/javascript"
    src="//<사이트 아이디(shortname)>.disqus.com/recent_comments_widget.js?
    num_items=5&hide_avatars=0
    &avatar_size=24&excerpt_length=30"></script>
    <small>Powered by <a href="http://openwiki.kr/tech/disqus">Disqus</a></small>
</div>
{% endhighlight %}




## 우수 작성자 / 최근 댓글 / 인기 댓글

{% highlight html %}
<script type="text/javascript"
src="//<사이트 아이디(shortname)>.disqus.com/combination_widget.js?
num_items=25&hide_mods=0&color=grey
&default_tab=recent&excerpt_length=70"></script>
{% endhighlight %}


### 관련글
{: .t60 }

{% include list-posts %}