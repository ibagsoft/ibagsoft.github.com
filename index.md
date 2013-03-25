---
layout: default
---
<div> 
    <ul>
    {% for post in site.categories.courses %}
        <li>
            <h2>
              <a href="{{ post.url }}">{{ post.title }}</a>
            </h2>
            <span class="title-desc">{{ post.description }}</span>
        </li>
        <br/>
    {% endfor %}
    </ul>
</div>