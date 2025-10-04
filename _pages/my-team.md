---
layout: archive
title: "My Team"
permalink: /my-team/
author_profile: true
---

{% include base_path %}

{% assign team = site.data.my-team %}

{% if team.overview %}
{{ team.overview }}
{% endif %}

{% if team.members.size > 0 %}
Team Members
======
{% for member in team.members %}
* **{{ member.name }}** - {{ member.role }}
  * {{ member.description }}
  {% if member.email %}
  * Email: [{{ member.email }}](mailto:{{ member.email }})
  {% endif %}
  {% if member.website %}
  * Website: [{{ member.website }}]({{ member.website }})
  {% endif %}
  {% if member.research_interests.size > 0 %}
  * Research Interests: {{ member.research_interests | join: ", " }}
  {% endif %}
{% endfor %}
{% endif %}

{% if team.alumni.size > 0 %}
Alumni
======
{% for alum in team.alumni %}
* **{{ alum.name }}** - {{ alum.role }} ({{ alum.period }})
  * {{ alum.description }}
  {% if alum.current_position %}
  * Current Position: {{ alum.current_position }}
  {% endif %}
{% endfor %}
{% endif %}

{% if team.openings %}
Openings
======
{{ team.openings }}
{% endif %}
