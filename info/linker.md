---
permalink: /
---

{% assign dict = site.pages | group_by_exp:"item", "item.url | remove_first: '/' | split: '/' | first" %}

{% for item in dict %}
  {% if item.name == 'info' %}
    {% for items in item.items %}
{% include {{item.name}}/{{items.name | url_escape}} %}
    {% endfor %}
  {% endif %}
{% endfor %}