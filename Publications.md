---
layout: default
title: Publications
permalink: /publications/
---

# Publications

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
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
{% if pub.code %}
[Code]({{ pub.code }})
{% endif %}

<br>

{% endfor %}
{% endfor %}
