---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: header/home.jpg
widget1:
  title: "Online Tools"
  url: 'http://wepplication.github.io/tools/'
  image: "widget/tools.png"
  text: '온라인 도구모음 바로가기'
widget2:
  title: "Links"
  url: 'http://wepplication.github.io/links/'
  image: "widget/links.jpg"
  text: '모르면 손해보는 유용한 사이트 모음'
widget3:
  title: "GitHubs"
  url: 'https://github.com/wepplication/'
  image: "widget/github.jpg"
  text: '깃허브 바로가기'
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#

permalink: /index.html

#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---

