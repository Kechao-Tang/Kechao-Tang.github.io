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
## {{ year.name }}

{% for pub in year.items %}
**{{ pub.title }}**  
{{ pub.authors }}  
*{{ pub.venue }}*, {{ pub.year }}.  

{% if pub.doi %}
[DOI]({{ pub.doi }})
{% endif %}
{% if pub.pdf %}
[PDF]({{ pub.pdf }})
{% endif %}
# {% if pub.code %}
# [Code]({{ pub.code }})
# {% endif %}

<br>

{% endfor %}
{% endfor %}
