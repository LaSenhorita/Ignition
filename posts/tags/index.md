---
layout: default
title: "Tags"
---
<table><tr><td>Tag</td><td>Contains</td></tr>
{% for tag in site.tags %}<tr><td><a href="#{{ tag[0] | replace: ' ', '_' }}">{{ tag[0] | replace: '__', '\_\_' }}</a></td><td>{{ tag[1].size }} post(s)</td></tr>{% endfor %}
</table>
<br />
<hr>
<br />
{% for tag in site.tags %}
#### <span id="{{ tag[0] | replace: ' ', '_' }}">{{ tag[0] | replace: '__', '\_\_' }}<sup>{{ tag[1].size }}</sup></span>
{% for post in tag[1] %}
* {{ post.date | date: "%b %d, %Y" }}&nbsp;&#124;&nbsp;[{{ post.title | replace: '__', '\_\_' }}]({{ site.url }}{{ post.url }})&nbsp;\[{{ post.category }}\]
{% endfor %}
{% endfor %}
