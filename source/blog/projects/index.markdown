---
layout: page
title: "projects"
date: 2013-12-04 11:30
comments: true
sharing: true
footer: true
---
<ul style="list-style-type: none;">
{% for item in site.categories %}
   {% if item[0] != "Monologin" %}
    <li style="font-size:1.8em;"><i class="icon-eye-open" style="margin-right:10px; color:green;"></i><a class="github" href="/blog/projects/{{ item[0] }}/">{{ item[0] | capitalize }}</a> [ {{ item[1].size }} ] </li>
    {% endif %}

{% endfor %}
</ul>
