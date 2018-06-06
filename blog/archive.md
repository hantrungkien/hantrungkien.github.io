---
layout: page
title: Archive
---

<!-- archive page code from http://chris.house/blog/building-a-simple-archive-page-with-jekyll -->

<div class="tags-expo">
    <div class="tags-expo-list">
    </div>
    <hr/>
    <div class="tags-expo-section">
        {% for post in site.posts %}
            {% assign currentDate = post.date | date: "%B %Y" %}
            {% if currentDate != myDate %}
                {% unless forloop.first %}</ul>{% endunless %}
                <h2>{{ currentDate }}</h2>
                <ul class="tags-expo-posts">
                {% assign myDate = currentDate %}
            {% endif %}
            <li>
                <small class="post-date">{{ post.date | date_to_string }} - </small>
                <a class="post-title" href="{{ site.baseurl }}{{ post.url }}">
                        {{ post.title }}
                </a>
            </li>
            {% if forloop.last %}</ul>{% endif %}
        {% endfor %}
    </div>
</div>