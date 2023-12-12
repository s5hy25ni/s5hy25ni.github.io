---
layout: page
title: Organized by Category
permalink: /categories/
content-type: eg
---

<style>
.category-content a {
    text-decoration: none;
    color: #4183c4;
}

.category-content a:hover {
    text-decoration: underline;
    color: #4183c4;
}
</style>

<main>
    {% for category in site.categories %}
        <div class="pure-u-1 tags">
        <h3 id="{{ category | first }}">{{ category | first  }}</h3>
        <ul>
            {% for post in category.last %}
                <li id="category-content"><a href="{{post.url}}">{{ post.title }}</a></li>
            {% endfor %}
        </ul>
        </div>
    {% endfor %}
    <br/>
    <br/>
</main>
