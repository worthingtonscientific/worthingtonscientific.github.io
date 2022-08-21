{% assign crumbs = page.url | remove: '/index.html' | split: '/' %}
{% assign result = site.title %}
{% for c in crumbs offset: 1 %}
{% if forloop.last %}
{% assign result = page.title | capitalize | append: ' | ' | append: result %}
{% else %}
{% capture head %}{{c | replace: '-', ' ' | remove: '.html' | capatalize}}{% endcapture %}
{% assign result = head | append: ' | ' | append: result %}
{% endif %}
{% endfor %}
{{result}}