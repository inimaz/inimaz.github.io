---
title: Academic Publications
layout: home
author_profile: true
header:
  overlay_image: https://images.unsplash.com/photo-1578829806467-54e94c45d5a2?q=80&w=2662&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
permalink: /academic-publications/
collection: academic-publications
classes: wide
link-years:
  - 2020
  - 2019
  - 2016
---

![Wordcloud of all the abstracts of the papers](../assets/images/wordcloud/wordcloud_abstracts.png "Wordcloud of all the abstracts of the papers mentioned below")
{% comment %} Navigation shortcut. {% endcomment %}

<p>
Go to &nbsp;
{% for year in page.link-years %}
<a href="/academic-publications/#{{ year }}">{{ year }}</a>&nbsp;&nbsp;
{% endfor %}
</p><br>

  <ol reversed>
    {% for pub in site.data.academic-pub %}
      {% if year != pub.year %}
        {% assign year = pub.year %}
        <a class="anchor" id="{{ year }}"><h4>{{ year }}</h4></a>
      {% endif %}
      <li>
        {{ pub.author }} ({{ pub.year }}).<br>
		<i>{{ pub.title }}</i>.<br>
		{{ pub.ref }}.
        {% if pub.doi %}
          <br/>doi: <a href="http://dx.doi.org/{{ pub.doi }}">{{pub.doi}}</a>&nbsp;&nbsp; 
        {% endif %}
        
        {% if pub.link %}
          <br/>links: <a href="{{ pub.link }}">{{pub.text}}</a>&nbsp;&nbsp; 
        {% endif %}
      </li><br>
    {% endfor %}
  </ol>
