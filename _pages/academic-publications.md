---
title: Academic Publications
layout: home
author_profile: true
header:
    overlay_image: /assets/images/image_beach.jpeg
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
