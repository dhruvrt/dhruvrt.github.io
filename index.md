---
layout: 'page'
icon: fas fa-info-circle
# order: 1
# permalink: /
# redirect_from:
#   - /about
---
## Dhruv Rama Tiwari


Hey! I am pursuing my Bachelor's in Computer Science from University of Michigan, Ann Arbor.<br/> Currently, I've taken a break from college to launch a startup, Audion Technologies. We are working on Glimpz, a music discovery app that allows you to find music by matching your taste and mood. I will share more details about it as we get closer to the launch in Q1, 2023. 

I plan to chronicle my startup journey here and share my learnings on various aspects of building a company. 

<!-- When I'm not think of ways to revolutionize the Music Industry, you can find me .... -->

{% assign pinned = site.posts | where: "pin", "true" %}
{% assign default = site.posts | where_exp: "item", "item.pin != true and item.hidden != true" %}

{% assign posts = pinned | concat: default %}

<div id="post-list">

{% for post in posts %}

  <div class="post-preview">
    <h1>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h1>

    <div class="post-content">
      <p>
        {% include no-linenos.html content=post.content %}
        {{ content | markdownify | strip_html | truncate: 200 | escape }}
      </p>
    </div>

    <div class="post-meta text-muted d-flex">
      <div class="mr-auto">

        <!-- posted date -->
        <i class="far fa-calendar fa-fw"></i>
        {% include datetime.html date=post.date %}

        <!-- categories -->
        {% if post.categories.size > 0 %}
          <i class="far fa-folder-open fa-fw"></i>
          <span>
          {% for category in post.categories %}
            {{ category }}
            {%- unless forloop.last -%},{%- endunless -%}
          {% endfor %}
          </span>
        {% endif %}

      </div>

      {% if post.pin %}
      <div class="pin">
        <i class="fas fa-thumbtack fa-fw"></i>
        <span>{{ site.data.locales[site.lang].post.pin_prompt }}</span>
      </div>
      {% endif %}

    </div> <!-- .post-meta -->

  </div> <!-- .post-review -->

{% endfor %}

</div> <!-- #post-list -->