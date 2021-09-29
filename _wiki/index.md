---
layout  : wikiindex
title   : Index
toc     : true
public  : true
comment : false
updated : 2021-09-24 21:58:47 +0900
regenerate: true
---

## 생각의 창
<div>
    <ul>
{% for post in site.posts %}
    {% if post.public == true %}
        <li>
            <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
                {{ post.date | date: '%Y, %D'}} - {{ post.title }}
            </a>
        </li>
    {% endif %}
{% endfor %}
    </ul>
</div>

---

## [[/project/index]]

* [[/project/1_vimwiki]]
* [[/project/2_dotfiles]]
* [[/project/3_taskwiki]]
* [[/project/4_multiple_git]]

## [[/pattern-language/index]]

* [[/pattern-language/oop/index]]
* [[/pattern-language/kubernetes/index]]
* [[/pattern-language/messaging/index]]
* [[/pattern-language/refactoring/index]]
* [[/pattern-language/xUnit/index]]


## [[/tech-knowlogy/index]]

* [[tech-knowlogy/rabbitmq_kafka]]

<!--

## [[/algorithm/index]]

* [[/algorithm/dijkstra]]

-->

---

