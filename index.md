Hi
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> <small>{{post.tag}}</small>
    </li>
  {% endfor %}
</ul>
