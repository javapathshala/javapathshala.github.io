---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  #image_fullwidth: header_unsplash_12.jpg
  image_fullwidth: cam.jpg
widget1:
  title: "Pathshala Blog"
  url: '/blog/'
  image: blog.jpg
  text: 'Unique blog where visitors can read a topic with totally new perspective. Motive is <em>Write code which human can understand better, WORK HARD OR WORK SMART</em>'
widget2:
  title: "Meet Dimit Chadha"
  url: '/info/'
  text: '<em>TOGAF Certified</em> Solution Architect.
  <ul class="inline-list social-icons">
  <li><a href="http://twitter.com/javapathshala" target="_blank" class="icon-twitter" title="twitter"></a></li>
  <li><a href="http://facebook.com/pathshalajava" target="_blank" class="icon-facebook" title="facebook"></a></li>
  <li><a href="http://linkedin.com/in/dimitchadha" target="_blank" class="icon-linkedin" title="linkedin"></a></li>
  </ul>'  
  image: bio.png
widget3:
  title: "Interviews-Afraid ?"
  url: '/interviews/'
  image: interview.jpg
  text: '<em>Afraid of interviews! Why you know every thing, you do sincere work every day. Boost up! '

#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /home/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
callforaction:
  url: https://javapathshala.us9.list-manage.com/subscribe/post?u=6cf631858e875ad381c906230&amp;id=86c5e97300
  text: Inform me about new wisdoms ›
  style: alert
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---
