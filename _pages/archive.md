---
layout: default
title: "Archive"
order: 1
---
<div class="row overview">
    <div class="col-md-12">
        <ul class="post-list">
            {% for post in site.categories.article %}
            <li>
                <h4>
                    <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
                </h4><div class="post-meta">{{post.date | date: "%Y-%m-%d" }}</div>
            </li>
            {% endfor %}
        </ul>
    </div>
</div>