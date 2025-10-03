---
layout: archive
title: "Personal Life"
permalink: /personal-life/
author_profile: true
---

{% include base_path %}

{% assign personal = site.data.personal-life %}

{% if personal.about %}
{{ personal.about.content }}
{% endif %}

{% if personal.hobbies.size > 0 %}
Hobbies & Interests
======
{% for hobby in personal.hobbies %}
* **{{ hobby.name }}**: {{ hobby.description }}
{% endfor %}
{% endif %}

{% if personal.experiences.size > 0 %}
Travel & Experiences
======
{% for experience in personal.experiences %}
* **{{ experience.year }}**: {{ experience.title }} - {{ experience.description }}{% if experience.location %} ({{ experience.location }}){% endif %}
{% endfor %}
{% endif %}

{% if personal.projects.size > 0 %}
Personal Projects
======
{% for project in personal.projects %}
* **{{ project.name }}** ({{ project.year }})
  * {{ project.description }}
  {% if project.technologies.size > 0 %}
  * Technologies: {{ project.technologies | join: ", " }}
  {% endif %}
  {% if project.url %}
  * [View Project]({{ project.url }})
  {% endif %}
{% endfor %}
{% endif %}

{% if personal.philosophy %}
{{ personal.philosophy.title }}
======
{{ personal.philosophy.content }}
{% endif %}

{% if personal.contact %}
Contact
======
{{ personal.contact.message }}
{% endif %}
