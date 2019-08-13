<!-- Navigation -->

{% for section in site.sections %}

  {% assign c = site.collections | where: "label", section.collection | first %}

***{{ section.title }}***

{% assign items = site[c.label] | sort: "question" %}

  {% for item in items %}[**Q-{{item.question}}**: {{ item.title }}](#q-{{item.question | downcase}})  
{% endfor %}

{% endfor %}
  
<!-- Content -->

{% for section in site.sections %}

  {% assign c = site.collections | where: "label", section.collection | first %}

## {{ section.title }}

{% assign items = site[c.label] | sort: "question" %}

<dl>
  {% for item in items %}

<dt><a name="q-{{item.question | downcase}}"></a>Q-{{item.question}}:</dt>
<dd>{{ item.title }}</dd>

<dt>A-{{item.question}}:</dt>
<dd>{{item.content}}</dd>

&nbsp;

  {% endfor %}
</dl>

{% endfor %}
