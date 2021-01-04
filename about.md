---
layout: dark 
title: About
example: This is an example value. 
---

This page describes the amazing {{ site.title }} by {{site.author.name }}.
{{ page.example }}

{% include big-cat.html %}

Some Markdown content describing your site.

## About About Pages

The About page is a common convention found on websites.
It is your opportunity to let us know all the details "about" your project:

- I intend to make projects on analyzing data and providing insights in a variety of fields.
- I am still learning statistics and coding. 
- I have so many ideas on everyday contents I want to write, but not sure if it's wise to have so many topics. 

Will this table work? 

| Topics | Examples | How much I'm prepared |
| --- | --- | --- |
| Data Science Projects | Data analysis, Web crawling, Time-series data | Not really |
| Korean | The Korean alphabets, grammar, resources | Quite sure |
| Random Topics | cowboys, sharks, Titanic... | Many ideas, but have to research each time |

{{ % for animal in site.data.animals %}}
- The {{ animal.name }} is a {{ animal.size }} animal.
{% endfor %}

## Large animals are the best! 

{% for animal in site.data.animals %}
{% if animal.size == "large" %}- <strong style="color: {{ animal.color }};">{{ animal.name }}</strong>
{% else %}- <small>{{ animal.name }}</small>
{% endif %}
{% endfor %}

## Small animals only! 
{% assign small_animals = site.data.animals | where: "size", "small" %}
{% for animal in small_animals %}
- {{ animal.name | upcase }}
{% endfor %}
