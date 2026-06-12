---
layout: archive
title: Publications
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
You can also find my articles on [my Google Scholar profile]({{ site.author.googlescholar }}).
{% endif %}

{% assign pubs_by_year = site.data.publications | group_by: "year" | sort: "name" | reverse %}

{% for year in pubs_by_year %}
<h2 style="margin-top: 1.8em; margin-bottom: 0.8em;">{{ year.name }}</h2>

{% for pub in year.items %}
<div class="publication-item" style="margin-bottom: 1.0em; line-height: 1.45;">

  <div style="font-weight: bold; margin-bottom: 0.15em;">
    {{ pub.title }}
  </div>

  <div style="margin-bottom: 0.15em;">
    {{ pub.authors }}
  </div>

  <div>
    <em>{{ pub.venue }}</em>, {{ pub.year }}.
    {% if pub.doi and pub.doi != "" %}
      <a href="{{ pub.doi }}">DOI</a>
    {% endif %}
    {% if pub.pdf and pub.pdf != "" %}
      {% if pub.doi and pub.doi != "" %}
        |
      {% endif %}
      <a href="{{ pub.pdf }}">PDF</a>
    {% endif %}
  </div>

</div>
{% endfor %}

{% endfor %}
