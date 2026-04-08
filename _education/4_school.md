---
layout: single
title: "Education"
permalink: /education/
author_profile: true
---

<h1>Education</h1>

<div class="edu-timeline">

{% assign sorted_edu = site.education | sort: "order" %}

{% for edu in sorted_edu %}

  <div class="edu-entry">

    <!-- Timeline dot -->
    <div class="edu-dot"></div>

    <div class="edu-card">

      <!-- Header -->
      <div class="edu-header">

        <!-- Logo -->
        {% if edu.logo %}
        <img src="{{ edu.logo }}" class="edu-logo">
        {% endif %}

        <div class="edu-title">
          <strong>{{ edu.institution }}</strong><br>
          <span class="edu-location">
            {% if edu.location %}{{ edu.location }}{% endif %}
          </span>
        </div>

        <div class="edu-date">{{ edu.date }}</div>

      </div>

      <!-- Degree -->
      <div class="edu-degree">{{ edu.degree }}</div>

      <!-- Details -->
      <ul>

        {% if edu.gpa %}
        <li><strong>CGPA:</strong> {{ edu.gpa }}</li>
        {% endif %}

        {% if edu.courses %}
        <li><strong>Selected Courses:</strong> {{ edu.courses }}</li>
        {% endif %}

        {% if edu.details %}
        <li>{{ edu.details }}</li>
        {% endif %}

        {% if edu.awards %}
        <li><strong>Awards & Scholarships:</strong>
          <ul>
            {% for award in edu.awards %}
              <li>{{ award }}</li>
            {% endfor %}
          </ul>
        </li>
        {% endif %}

      </ul>

    </div>

  </div>

{% endfor %}

</div>
