---
layout: default
title: Events and public wonder
category: crockery
---

{% assign rows = site.events.size | divided_by: 2.0 | ceil %}
{% for i in (1..rows) %}
  {% assign offset = forloop.index0 | times: 2 %}
  <div class="row">
  {% assign sorted = site.events | sort:"date" %}
  {% for event in sorted limit:2 offset:offset %}
     <div class="col-md-6 mt-3">

          <div class="card h-100">
              <div class="card-body h-100 ">
              <h3>{{ event.title }}</h3>
              <div class="cover-image">
                <img class="align-self-center mr-3 rounded-circle float-right thumb-post" src="{{ site.baseurl }}/images/events/{{ event.thumbnail }}"
                             alt="{{page.title}}'s profile image" height="150" width="150">
              </div>
              <div class="contents-label">

                <p class="card-text">{{ event.content | strip_html | truncatewords: 20}}</p>

                <ul>
                  <li>Time: {{ event.time }}</li>
                  <li>Date: {{ event.date-live }}</li>
                  <li>Cost: {{ event.cost }}</li>
                  <li>Venue: {{ event.venue }}</li>
                </ul>
                </div>
                <a href="{{ site.baseurl }}{{ event.url }}" class="btn btn-dark">Read more</a>
              </div>
          </div>

    </div>
    {% endfor %}
  </div>
{% endfor %}
