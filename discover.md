---
layout: default
title: Discover stories from the exhibition
---
{% assign rows = site.discover.size | divided_by: 2.0 | ceil %}
{% for i in (1..rows) %}
  {% assign offset = forloop.index0 | times: 2 %}
  <div class="row">
  {% assign sorted = site.discover | sort:"order" %}
  {% for author in sorted limit:2 offset:offset %}
     <div class="col-md-6 mt-3">

          <div class="card h-100">
              <div class="card-body h-100 ">
              <div class="cover-image">
                <img class="align-self-center mr-3 rounded-circle float-right thumb-post" src="/images/discover/{{ author.thumbnail }}"
                             alt="{{ page.title }}'s profile image" height="150" width="150">
              </div>
              <div class="contents-label">
                <h5 class="card-title">{{author.title}} </h5>
                                    {% if author.job-title %}
                                    <h6 class="text-muted">{{ author.job-title}} </h6>
                                    {% endif %}

                <p class="card-text">{{ author.content | strip_html | truncatewords: 20}}</p>
                </div>
                <a href="{{ author.url }}" class="btn btn-dark">Read more</a>
              </div>
          </div>

    </div>
    {% endfor %}
  </div>
{% endfor %}
