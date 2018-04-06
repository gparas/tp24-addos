---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---

{% for i in (1..2) %}
  <a href="/case-study-{{ i }}">case-study-{{ i }}</a>
{% endfor %}
