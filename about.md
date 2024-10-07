---
title: Jordan Bunke - About
---

<!-- TODO -->
# About

<img src="{{ site.baseurl }}/assets/img/portrait.png" alt="Portrait" class="portrait">

Here

## Experience

{% assign experience = site.experience | sort: 'index' %}
{% for job in experience %}
    <div>{{ job.organization }}</div>
    {{ job.content }}
{% endfor %}

## Skills

#### Languages
* **Native**: English, German
* **Working proficiency**: Portuguese
* **Conversational**: Spanish

## Technologies

<hr>

A full CV/resume can be produced upon request
