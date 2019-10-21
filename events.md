---
layout: default
title: Events and public wonder
category: crockery
---

{% assign rows = site.events.size | divided_by: 2.0 | ceil %}
{% for i in (1..rows) %}
{% assign offset = forloop.index0 | times: 2 %}
<div class="row">
{% assign sorted = site.events | sort:"date-live" %}
{% for event in sorted limit:2 offset:offset %}
<div class="col-md-6 mb-3">
  <div class="card card-body h-100
  intro-card ">

  <div class="container h-100">
    <h3>
      <a href="{{ site.baseurl }}{{ event.url }}">{{ event.title }}</a>
    </h3>
    <!-- start image block -->

    <div class="cover-image">
      <img class="align-self-center mr-3 rounded-circle float-right thumb-post" src="{{ site.baseurl }}/images/events/{{ event.thumbnail }}"
                   alt="{{page.title}}'s profile image" height="150" width="150">
    </div>

    <!-- end image block -->

    <div class="contents-label">
      <p class="card-text">{{ event.content | strip_html | truncatewords: 20}}</p>

      <ul>
        <li>Time: {{ event.time }}</li>
        <li>Date: {{ event.date-live | date: "%A %-d of %B, %Y"  }}</li>
        <li>Cost: {{ event.cost }}</li>
        <li>Venue: {{ event.venue }}</li>
      </ul>
    </div>
  </div>
  <a href="{{ site.baseurl }}{{ event.url }}" class="btn btn-dark">Read more</a>
</div>

</div>
{% endfor %}
</div>
{% endfor %}
