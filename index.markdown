---
layout: default
title: "Thomas Uhde's blog"
description: "Personal blog of Tom Ward, in which he writes about ruby, rails and web development, as well as other random ephemera"
---
{% for page in site.posts limit:5 %}
{% assign body = page.content %}
{% include post-div.html %}
{% endfor %}
<div class="container">
<div class="row">
<div class="twelvecol">
<h3>Older Posts:</h3>
</div>
</div>
{% for post in site.posts offset:5 %}
  <div class="row">
  <div class="twelvecol">
  <h3 class="title"><a href="{{ post.url }}">{{ post.title }}</a></h3>
  <div class="oldmeta">
  <span class="author"><a href="http://nxhelp.com">Thomas Uhde</a></span> &middot; 
  <span class="date"><a href="/{{ post.date | date: "%Y" }}/{{ post.date | date: "%m" }}">{{ post.date | date: "%e" | ordinalize }} {{ post.date | date: "%B"}} {{ post.date | date: "%Y"}}</a></span>
  <span class="tags">{% for tag in post.categories %} &middot; <a href="/tags/{{tag}}" rel="tag">{{tag}}</a>{% endfor %}</span> &middot; 
  <span class="comments"><a href="{{ post.url }}/#disqus_thread">Comments</a></span>
  </div>
  </div>
  </div>
{% unless forloop.last %}{% endunless %}{% endfor %}
</div>

<script type="text/javascript">
/* * * CONFIGURATION VARIABLES: EDIT BEFORE PASTING INTO YOUR WEBPAGE * * */
var disqus_shortname = 'nxhelp'; // required: replace example with your forum shortname

/* * * DON'T EDIT BELOW THIS LINE * * */
(function () {
    var s = document.createElement('script'); s.async = true;
    s.type = 'text/javascript';
    s.src = 'http://' + disqus_shortname + '.disqus.com/count.js';
    (document.getElementsByTagName('HEAD')[0] || document.getElementsByTagName('BODY')[0]).appendChild(s);
}());
</script>

