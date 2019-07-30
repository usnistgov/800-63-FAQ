---
layout: cover
title: "NIST SP 800-63 Digital Identity Guidelines-FAQ"
description: "NIST Special Publication 800-63 Digital Identity Guidelines-FAQ"
---
<section class="home home-title" markdown="1">

<div class="text-center" markdown="1">
## NIST Special Publication 800-63: Digital Identity Guidelines
## Frequently Asked Questions

#### June 21, 2019
<br>
</div>
</section>

<section class="home home-about" markdown="1">

The following list of FAQs for [Special Publication (SP) 800-63, Digital Identity Guidelines](https://pages.nist.gov/800-63-3/) addresses recurring inquiries to provide additional clarification to stakeholders. As new questions arise, we will update these FAQs.


Questions and comments can be submitted via [GitHub](https://github.com/usnistgov/800-63-FAQ/issues) or [email](mailto:dig-comments@nist.gov).
<br>


<div class="section-container" markdown="1">

<!-- Navigation -->

{% for section in site.sections %}

  {% assign c = site.collections | where: "label", section.collection | first %}

***{{ section.title }}***

{% assign items = site[c.label] | sort: "question" %}

  {% for item in items %}<a href="#q-{{item.question | downcase}}">Q-{{item.question}}: {{ item.title }}</a>  
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


</div>

</section>
