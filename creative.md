---
layout: default
title: Food, Glorious Food! Creative Writing Workshops
category: crockery
---

Helen Taylor ran 3 bespoke creative writing workshops at the Fitzwilliam Museum on 30 January 2020, 8 February 2020, and 15 February 2020.
As Helen’s introduction explains, these explored our complicated relationship with food using the Feast & Fast exhibition as inspiration.
Thirteen new creative works resulted and are published here as texts together with images of the exhibits from Feast & Fast that acted as visual sources of inspiration. In most cases the authors also provided audio files of themselves reading their new works out loud.

{% assign rows = site.creative.size | divided_by: 2.0 | ceil %}
{% for i in (1..rows) %}
{% assign offset = forloop.index0 | times: 2 %}
<div class="row">
{% assign sorted = site.creative | sort: "order" %}
{% for event in sorted limit:2 offset:offset %}
<div class="col-md-6 mb-3">
  <div class="card card-body h-100
  intro-card ">

  <div class="container h-100">

    <h3>
      <a href="{{ site.baseurl }}{{ event.url }}">{{ event.title }}</a>
    </h3>

    <h4>{{ event.author }}</h4>

    <div class="contents-label mb-3">
      <p class="card-text">{{ event.content | strip_html | truncatewords: 20}}</p>
    </div>
  </div>
  <a href="{{ site.baseurl }}{{ event.url }}" class="btn btn-dark">Read more</a>
</div>

</div>
{% endfor %}
</div>
{% endfor %}
