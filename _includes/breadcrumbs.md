<nav aria-label="breadcrumb">
{% assign crumbs = page.url | remove: '/index.html' | split: '/' %}
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="/">Home</a></li>
    {% for c in crumbs offset: 1 %}
        {% if forloop.last %}
            <li class="breadcrumb-item active" aria-current="page">{{page.title | capitalize}}</li>
        {% else %}
            <li class="breadcrumb-item"><a href="{% assign crumblimit = forloop.index | plus: 1 %}{% for cc in crumbs limit: crumblimit %}{{cc | append: '/' }}{% endfor  %}">{{c | capitalize}}</a></li>
        {% endif %}
    {% endfor %}
  </ol>
</nav>