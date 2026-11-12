---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

My academic work spans international political economy and comparative politics. This page brings together my peer-reviewed research, contributions to historical public engagement, and academic theses.

{% if site.author.googlescholar %}
<div class="wordwrap">
You can also find my academic publications on
<a href="{{ site.author.googlescholar }}">Google Scholar</a>.
</div>
{% endif %}

{% include base_path %}

{% if site.publication_category %}
{% for category in site.publication_category %}
{% assign title_shown = false %}
{% for post in site.publications reversed %}
{% if post.category != category[0] %}
{% continue %}
{% endif %}
{% unless title_shown %}
{% assign category_title = category[1].title %}
<h2>{{ category_title }}</h2>
{% case category[0] %}
{% when "articles" %}
<p class="archive__subtitle">Peer-reviewed research examining questions in international political economy, comparative politics, and related fields.</p>
{% when "history" %}
<p class="archive__subtitle">Contributions to historical research and public engagement, connecting academic work with broader audiences.</p>
{% when "theses" %}
<p class="archive__subtitle">Undergraduate, master's, and doctoral research developed throughout my academic training.</p>
{% endcase %}
<hr />
{% assign title_shown = true %}
{% endunless %}
{% include archive-single.html %}
{% endfor %}
{% endfor %}
{% else %}
{% for post in site.publications reversed %}
{% include archive-single.html %}
{% endfor %}
{% endif %}