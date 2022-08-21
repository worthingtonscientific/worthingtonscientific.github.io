<ul>

{% assign sortedpages = site.pages | where: "type", page.title | sort: "sort" %}

{% for i in sortedpages %}

<li><a href="{{i.url}}">{{i.title | capitalize}}</a></li>

{% endfor %}

</ul>