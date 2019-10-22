---
layout: objects
title: Discover the objects
category: pavilion
---


{% assign rows = site.data.objects.size | divided_by: 2.0 | ceil %}
{% for i in (1..rows) %}
  {% assign offset = forloop.index0 | times: 2 %}
  <div class="row">
  {% assign sorted = site.data.objects | sort:"exhibition_area" %}
  {% for object in sorted limit:2 offset:offset %}
  <div class="col-md-6 mb-3">
    <div class="card card-body h-100
    intro-card ">

    <div class="container h-100">

      <!-- start image block -->

      <div class="cover-image ">
        <img class="align-self-center ml-1 mr-3 rounded-circle float-right thumb-post" src="{{ site.baseurl }}/images/discover/placeholder.svg"
                     alt="{{ object.label }}'s  image" height="150" width="150">
      </div>

      <!-- end image block -->

      <div class="contents-label mb-3">
      <h3>
        <a href="{{ site.baseurl }}/objects/{{ object.exhibition_number }}">{{ object.label | truncate: 100 }}</a>
      </h3>

      <ul>
        {% if object.exhibition_number != blank %}
          <li>Exhibition number: {{ object.exhibition_number }}</li>
        {% endif %}
        {% if object.exhibition_location != blank %}
          <li>Exhibition gallery: {{ object.exhibition_location }}</li>
        {% endif %}
        {% if object.artist_info != blank %}
          <li>Artist: {{ object.artist_info }}</li>
        {% endif %}
        {% if object.exhibition_area != blank %}
          <li>Exhibition Area: {{ object.exhibition_area }}</li>
        {% endif %}
        {% if object.gallery_location != blank %}
          <li>Gallery Location: {{ object.gallery_location }}</li>
        {% endif %}
      </ul>

      </div>
    </div>
    <a href="{{ site.baseurl }}/objects/{{ object.exhibition_number }}" class="btn btn-dark">Read more</a>
  </div>

  </div>
  {% endfor %}
  </div>
  {% endfor %}
